#Learning 
____
## Instrucciones 

En este ejercicio, proporcionará un TranslationService que ofrece servicios de traducción básica a los miembros gratuitos y traducción avanzada a los miembros premium con garantías de calidad.
### API

Has encontrado una API de traducción en el espacio exterior que satisface cualquier solicitud de traducción en un tiempo razonable. Quieres sacar provecho de ello. Los traductores espaciales son extremadamente volubles y odian la redundancia, por lo que también proporcionan satélites de almacenamiento de la API donde puedes recuperar traducciones anteriores sin molestarles.
### Obtener una traducción

`api.fetch(text)` obtiene una traducción de `text` del almacenamiento de la API y devuelve una `promise` que proporciona dos valores:  
  
- `translation`: la traducción actual  
- `quality`: la calidad expresada como un número  

Si no se encuentra una traducción en el almacén de la API, ésta lanza un error `NotAvailable`. Las traducciones pueden añadirse utilizando el método `api.request`. Si '`text`' no es traducible, la API arroja un error `Untranslatable`.

```js
api.fetch('jIyaj');
// => Promise({ resolved: 'I understand' })
```
### Solicitar una traducción

Algunas traducciones existen con seguridad, pero aún no se han añadido al almacenamiento de la API. Ésa es la diferencia entre `NotAvailable` ( no está almacenada, pero puede solicitarse ) e `Untranslatable` ( no puede traducirse ).  
  
`api.request(text, callback)` solicita que se realice una traducción del `text` y se añada al almacenamiento de la API. Al finalizar, se llama a la función `callback`.  
  
- En caso de éxito, el `callback` pasa como `undefined`: esto indica que la traducción se ha realizado correctamente y que se puede acceder a ella mediante el método `api.fetch`.  
- En caso de fallo, se pasa un error al `callback`: esto indica que algo ha ido mal. La API de `outspace` es inestable, lo que significa que falla a menudo. Si eso sucede, está bien `api.request` de nuevo.

```js
api.request('majQa’', callback);
// => undefined
//
// later: the passed callback is called with undefined
//        because it was successful.
```

>[!warning] Advertencia!
>La API hace su magia teletransportando a los distintos traductores cuando llega una `request`. Se trata de una acción muy costosa, por lo que no debería ejecutarse cuando hay una traducción disponible. Por desgracia, no todo el mundo lee el manual, por lo que existe un sistema para expulsar a los malos actores.  
>
>Si se llama a `api.request` cuando hay `text` disponible, la API lanza un `AbusiveClientError` para esta llamada, y **para cada llamada posterior**. Asegúrese de que nunca solicita una traducción si algo ya ha sido traducido.
## 1. Obtener una traducción, ignorando la calidad  

El servicio gratuito sólo proporciona las traducciones que se encuentran actualmente en el almacenamiento de la API.  
  
Implemente un método free(text) que proporcione a los miembros free traducciones que ya existan en el almacenamiento de la API. Ignore la calidad y reenvíe cualquier error lanzado por la API.  
  
Devuelve la traducción si puede recuperarse, independientemente de su calidad.  
Reenvía cualquier error de la API de traducción  
Utiliza el método api.fetch (api.fetch devuelve una promesa)

```js
service.free('jIyaj');
// => Promise<...> resolves "I understand."

service.free("jIyajbe'");
// => Promise<...> rejects Error("Not yet translated")
```
### Mi solución

```js
  free(text) {
    return this.api.fetch(text).then((result)=> result.translation)
  }
```
## 2. Obtener un lote de traducciones, todo o nada  

Implementar un método `batch([text, text, ...])` para miembros libres que traduzca un array de texto utilizando el servicio libre, devolviendo todas las traducciones, o un único error.  
  
- Resuelve con todas las traducciones (en el mismo orden), si están todas disponibles  
- Rechaza con el primer error que se encuentre  
- Rechaza con un error `BatchIsEmpty` si no se dan textos

```js
service.batch(['jIyaj', "majQa'"]);
// => Promise<...> resolves ["I understand.", "Well done!"]

service.batch(['jIyaj', "jIyajbe'"]);
// => Promise<...> rejects new Error("Not yet translated")

service.batch([]);
// => Promise<...> rejects BatchIsEmpty()
```
### Mi solución

```js
batch(texts) {
    if (texts.length === 0) return Promise.reject(new BatchIsEmpty());
    return Promise.all(texts.map(text =>this.free(text)))
  }
```
## 3. Solicitar una traducción, reintentando como máximo 2 veces  

Implemente un método de usuario premium `request(text)`, que solicite que se añada una traducción al almacenamiento de la API. La solicitud debe reintentarse automáticamente si se produce un fallo. No debería realizar más de 3 llamadas para la misma solicitud (¡¡¡no moleste a los traductores espaciales!!!).  
  
- Si `api.request` no devuelve un error, resolver con `undefined`.
- Si `api.request` devuelve un error, reintentar como máximo dos veces.  
- Si te quedas sin reintentos, rechaza con el último error recibido.

```js
service.request("jIyajbe'");
// => Promise<...> resolves (with nothing), can now be retrieved using the fetch API
```
### Mi solución

```js
request(text) {
    const promReq = (text) => new Promise((resolve, reject) => {
      this.api.request(text, err => {
        if (err) reject(err);
        resolve();
      });
    });
    return new Promise((resolve, reject) => {
      this.api.request(text, err => {
        if (err) reject(err);
        resolve();
      })
    })
    .then(success => Promise.resolve(), failure => promReq(text))
    .then(success => Promise.resolve(), failure => promReq(text))
    .then(success => Promise.resolve(), failure => Promise.reject(failure))
  }
```
## 4. Obtener una traducción, comprobar su calidad o solicitarla  

Implemente un método de usuario premium `premium(text, quality)` para obtener una traducción. Si una traducción `NotAvailable`, solicítela y recupérela una vez que se haya añadido al almacenamiento de la API. El método sólo debe devolver la traducción si cumple un determinado umbral de `quality`.  
  
- Si `api.fetch` resuelve, comprueba la calidad antes de resolver.  
- Si `api.fetch` rechaza, solicitar la traducción en su lugar.  
- Si `api.request` rechaza, reenviar el error.

```js
service.premium("jIyajbe'", 100);
// => Promise<...> resolves "I don't understand."

service.premium("'arlogh Qoylu'pu'?", 100);
// => Promise<...> rejects QualityThresholdNotMet()

service.premium("'arlogh Qoylu'pu'?", 40);
// => Promise<...> resolves "What time is it?"
```
### Mi solución

```js
premium(text, minimumQuality) {
      return this.api.fetch(text)
      .then(result => new Promise((resolve, reject) => {
        if (result.quality >= minimumQuality)
          resolve(result.translation);
        else
          reject( new QualityThresholdNotMet() );
      }))
      .catch(err => {
        if (err.constructor.name === 'Untranslatable')
          return Promise.reject(err);
        if (err instanceof QualityThresholdNotMet)
          throw err;
        if (err.constructor.name === 'NotAvailable')
          return this.request(text)
                  .then(t => this.premium(text, minimumQuality));
      })
  }
```

> [!note] Nota
> La traducción correcta de 'arlogh Qoylu'pu'? es ¿Cuántas veces se ha oído?
## Link del problema

https://exercism.org/tracks/javascript/exercises/translation-service