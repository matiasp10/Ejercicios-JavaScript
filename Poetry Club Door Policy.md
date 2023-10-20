#Learning 
___
# Política de puertas del Club de Poesía

Se ha abierto un nuevo club de poesía en la ciudad y estás pensando en ir. Como ha habido incidentes en el pasado, el club tiene una política de puertas muy específica que tendrás que dominar antes de intentar entrar.

Hay dos puertas en el club de poesía, una delantera y otra trasera, y ambas están vigiladas. Para entrar, tendrás que averiguar la contraseña del día.

La contraseña siempre se basa en un poema y puede obtenerse en un proceso de dos pasos.

1.  El guardia recitará el poema, verso a verso, y tú tendrás que responder con la letra adecuada de ese verso.
    
2.  A continuación, el guardia te dirá todas las letras con las que has respondido a la vez y tienes que escribirlas en un papel con un formato específico. Los detalles del proceso dependen de la puerta por la que intentes entrar.
    

## Link del problema

[https://exercism.org/tracks/javascript/exercises/poetry-club-door-policy](https://exercism.org/tracks/javascript/exercises/poetry-club-door-policy)

## Paso 1: Obtener la primera letra de una frase

Para determinar las letras de la contraseña de la puerta principal, tienes que responder con la primera letra del verso del poema que te recite el vigilante.

Para conseguir una buena contraseña, a los miembros del club de poesía les gusta utilizar poemas acrósticos. Esto significa que la primera letra de cada frase forma una palabra. He aquí un ejemplo de uno de sus escritores favoritos, Michael Lockwood.

> [!info] 
> Stands so high
> Huge hooves too  
> Impatiently waits for  
> Reins and harness  
> Eager to leave

Así que cuando el guardia recite `Stands so high`, responderás `S`, cuando el guardia recite `Huge hooves too`, responderás `H`.

Implementa la función `frontDoorResponse` que toma una línea del poema como argumento y devuelve la primera letra de esa línea.

```js
frontDoorResponse('Stands so high'); // => "S"
```

### Mi solución

```js
function frontDoorResponse(line) {
  return line[0]
}
```

Puedo acceder al primer elemento de un `string` con `[]`.

## Paso 2: Escribir una palabra en mayúsculas

Ahora que tienes todas las letras correctas, todo lo que necesitas hacer para obtener la contraseña de la puerta principal es escribir correctamente la palabra en mayúsculas.

Implementa la función `frontDoorPassword` que acepta una cadena (las letras combinadas que encontraste en la tarea 1) y la devuelve correctamente en mayúsculas.

```js
frontDoorPassword('SHIRE');
// => "Shire"

frontDoorPassword('shire');
// => "Shire"
```

### Mi solución

```js
function frontDoorPassword(word) {
  let capitalizedWord = []
  for (let letter of word) {
    if(letter == word[0]){
      capitalizedWord.push(letter.toUpperCase())
    } else {
      capitalizedWord.push(letter.toLowerCase())
    }
  }
  return capitalizedWord.join("")
}
```

Recorrí el `string` que recibo de la función mediante un `for...of`, si era la primera letra la convierto en mayúscula y le hago un `push` a una variable que contendrá la palabra, las demás letras les hago un `push` en minúsculas.

## Paso 3: Obtener la última letra de una frase

Para determinar las letras de la contraseña de la puerta trasera, tienes que responder con la última letra del verso del poema que te recite el guardia.

Los miembros del club de poesía son muy listos. El poema antes mencionado también es teléstico, lo que significa que la última letra de cada frase también forma una palabra:

> [!info] 
> Stands so high  
> Huge hooves too  
> Impatiently waits for  
> Reins and harness  
> Eager to leave

Cuando el guardia recite `Stands so high`, responderás `h`, cuando el guardia recite `Huge hooves too`, responderás `o`.

Tenga en cuenta que a veces el guardia hace pausas estilísticas (en forma de espacios en blanco) al principio o al final de una línea. Tendrás que ignorar esas pausas para obtener la letra correcta.

Implemente la función `backDoorResponse` que toma una línea del poema como argumento y devuelve la última letra de esa línea que no sea un carácter de espacio en blanco.

```js
backDoorResponse('Stands so high');
// => "h"

backDoorResponse('Stands so high   ');
// => "h"
```

### Mi solución

```js
function backDoorResponse(line) {
  line = line.trim()
  return line[line.length - 1]
}
```

El método `.trim()` elimina los espacios en blanco al comienzo y final de un `string` para evitar devolver un `string` vacío y devuelvo el último elemento del `string`.

## Paso 4: Sé educado

Para entrar en el club de poesía por la puerta de atrás, hay que ser muy educado. Así que para obtener la contraseña, esta vez tienes que escribir correctamente la palabra en mayúsculas y añadir `', please'` al final.

Implementa la función `backDoorPassword` que acepta una cadena (las letras combinadas que encontraste en la tarea 3) y devuelve la versión educada de la contraseña en mayúsculas.

### Mi solución

```js
function backDoorPassword(word) {
  return frontDoorPassword(word) + ", please"
}
```

Utilizo la función que hice en el paso 2 para escribir correctamente la palabra, y solamente devuelvo ese `string` y agregado el `string` `", please"`.

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]