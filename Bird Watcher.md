El bucle `for` es una de las sentencias más utilizadas para ejecutar repetidamente alguna lógica. En JavaScript, consta de la palabra clave `for`, una cabecera entre corchetes y un bloque de código que contiene el cuerpo del bucle entre llaves.

```js
for (initialization; condition; step) {
  // code that is executed repeatedly as long as the condition is true
}
```

La inicialización suele establecer una variable contador, la condición comprueba si el bucle debe continuar o detenerse y el paso incrementa el contador al final de cada repetición. Las partes individuales de la cabecera están separadas por punto y coma.

```js
const list = ['a', 'b', 'c'];
for (let i = 0; i < list.length; i++) {
  // code that should be executed for each item list[i]
}
```

La definición del paso suele realizarse mediante el operador de incremento o decremento de JavaScript, como se muestra en el ejemplo anterior. Estos operadores modifican una variable en su lugar. `++` suma uno a un número, `--` resta uno a un número.

```js
let i = 3;
i++;
// i is now 4

let j = 0;
j--;
// j is now -1
```
## Instrucción 

Usted es un ávido observador de aves que lleva la cuenta de cuántos pájaros han visitado su jardín. Normalmente, utiliza un recuento en un cuaderno para contar los pájaros, pero quiere trabajar mejor con sus datos. Ya has digitalizado los recuentos diarios de aves de las últimas semanas que guardabas en el cuaderno.  
  
Ahora quiere determinar el número total de aves que ha contado, calcular el recuento de aves de una semana concreta y corregir un error de recuento.

>[!note] Nota
>Para practicar, utiliza un bucle for para resolver cada una de las tareas siguientes.

## Link del problema 

https://exercism.org/tracks/javascript/exercises/bird-watcher
## 1. Determina el número total de aves que has contado hasta ahora

Empecemos a analizar los datos obteniendo una visión de alto nivel. Averigua cuántas aves has contado en total desde que comenzaste tus registros.  
  
Implemente una función `totalBirdCount` que acepte una matriz que contenga el recuento de aves por día. Debería devolver el número total de aves que has contado.

```js
birdsPerDay = [2, 5, 0, 7, 4, 1, 3, 0, 2, 5, 0, 1, 3, 1];
totalBirdCount(birdsPerDay);
// => 34
```
### Mi solución 

```js
export function totalBirdCount(birdsPerDay) {
	let total = 0
	for(let bird of birdsPerDay){
	    total += bird
	}
	return total
}
```
## 2. Calcular el número de aves visitantes en una semana determinada

Ahora que ya tiene una idea general de las cifras de su recuento de aves, querrá hacer un análisis más detallado.  
  
Implemente una función `birdsInWeek` que acepte una matriz de recuentos de aves por día y un número de semana. Devuelve el número total de aves contadas en esa semana específica. Puede asumir que las semanas siempre se contabilizan por completo.

```js
birdsPerDay = [2, 5, 0, 7, 4, 1, 3, 0, 2, 5, 0, 1, 3, 1];
birdsInWeek(birdsPerDay, 2);
// => 12
```
### Mi solución

```js
export function birdsInWeek(birdsPerDay, week) {
    let total = 0
  for(let i = ((week - 1) * 7); i < week * 7; i++){
    total += birdsPerDay[i]
  }
  return total
}
```

## 3. Corregir un error de recuento

Te diste cuenta de que todo el tiempo que intentabas seguir la pista de los pájaros, había uno escondido en un rincón alejado del jardín. Te diste cuenta de que este pájaro siempre pasaba uno de cada dos días en tu jardín. No sabes exactamente dónde estaba entre esos días, pero desde luego no en tu jardín. Tu intuición de observador de aves también te dice que el pájaro estuvo en tu jardín el primer día que rastreaste en tu lista.  
  
Dada esta nueva información, escriba una función `fixBirdCountLog` que tome como argumento un array de pájaros contados por día. Debería corregir el error de recuento y devolver el array modificado.

```js
birdsPerDay = [2, 5, 0, 7, 4, 1];
fixBirdCountLog(birdsPerDay);
// => [3, 5, 1, 7, 5, 1]
```
### Mi solución

```js
export function fixBirdCountLog(birdsPerDay) {
  birdsPerDay.forEach((bird, index)=>{
    if(index % 2 === 0){
      birdsPerDay[index] = bird + 1 
    } 
  })
  return birdsPerDay
}
```