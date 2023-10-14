#Learning 
___
## Introducción 

Los cierres son un patrón de programación de JavaScript que permite utilizar variables de un ámbito léxico externo dentro de un bloque de código anidado. JavaScript admite cierres de forma transparente, y a menudo se utilizan sin saber lo que son.

```js
// Top-level declarations are global-scope
const dozen = 12;

{
  // Braces create a new block-scope
  // Referencing the outer variable is a closure.
  const twoDozen = dozen * 2;
}

// Functions create a new function-scope and block-scope.
// Referencing the outer variable here is a closure.
function nDozen(n) {
  return dozen * n;
}
```
### Closures para guardar el estado y transmitir valores

El uso de una declaración de variable mutable (como `let` o `var`) permite preservar cierto estado:

```js
let counter = 0;

// This function closure increments the counter's state in the outer lexical context.
// This way the counter can be shared between many calling contexts.
export function increment() {
  counter += 1;
  return counter;
}
```
___
## Instrucciones 

Su empresa de diseño ha estado trabajando principalmente con transformaciones CSS para construir páginas web. Después de algunas discusiones, se toma la decisión de empezar a utilizar JavaScript para realizar algunos cálculos de forma dinámica. Algunos de tus compañeros de equipo tienen menos experiencia con JavaScript, así que decidís utilizar un cierre de función para crear transformaciones reutilizables para pares de coordenadas `{x, y}`.
## 1. Traducir las coordenadas  

Implementa la función `translate2d` que devuelve una función que hace uso de un `closure` para realizar una traslación 2d repetible de un par de coordenadas.

```js
const moveCoordinatesRight2Px = translate2d(2, 0);
const result = moveCoordinatesRight2Px(4, 8);
// result => [6, 8]
```
### Mi solución

```js
export function translate2d(dx, dy) {
  return function moveCoordinatesRight2Px(x,y) {
    return [x+dx, y+dy]
  }
}
```
## 2. Escalar las coordenadas  

Implementa la función scale2d que devuelve una función que hace uso de un `closure` para realizar una escala 2d repetible de un par de coordenadas.  
  
>[!note] Nota
> Para este ejercicio, asume sólo valores de escala positivos.

```js
const doubleScale = scale2d(2, 2);
const result = doubleScale(6, -3);
// result => [12, -6]
```
### Mi solución

```js
export function scale2d(sx, sy) {
  return function doubleScale(x,y) {
    return [x*sx,y*sy]
  }
}
```
## 3. Componer funciones de transformación  

Combina dos funciones de transformación para realizar una transformación repetible. Esto suele denominarse composición de funciones, en la que el resultado de la primera función 'f(x)' se utiliza como entrada de la segunda función 'g(x)'.

```js
const moveCoordinatesRight2Px = translate2d(2, 0);
const doubleCoordinates = scale2d(2, 2);
const composedTransformations = composeTransform(
  moveCoordinatesRight2Px,
  doubleCoordinates,
);
const result = composedTransformations(0, 1);
// result => [4, 2]
```
### Mi solución

```js
export function composeTransform(f, g) {
  return function composedTransformations(x, y){
    let moved = f(x,y)
    return g(moved[0],moved[1])
  }
}
```
## 4. Guardar los resultados de las funciones  

Implementa la función `memoizeTransform`. Toma una función para memorizar, luego devuelve una nueva función que recuerda las entradas a la función suministrada para que el último valor de retorno pueda ser "recordado" y sólo calculado una vez si se llama de nuevo con los mismos argumentos.  
  
> [!note] Nota
> La memorización se utiliza a veces en programación dinámica. Permite realizar operaciones costosas sólo una vez, ya que sus resultados son recordados. Observe que en este ejercicio sólo se recuerda el último resultado, a diferencia de algunas soluciones en programación dinámica que memorizan todos los resultados.

```js
const tripleScale = scale2d(3, 3);
const memoizedScale = memoizeTransform(tripleScale);

memoizedScale(4, 3); // => [12, 9], this is computed since it hasn't been computed before for the arguments
memoizedScale(4, 3); // => [12, 9], this is remembered, since it was computed already
```
### Mi solución

```js
export function memoizeTransform(f) {
  let prevX, prevY, prevResult;
  return function memoized(x, y) {
    if (prevX === x && prevY === y) {
      return prevResult;
    } else {
      prevX = x;
      prevY = y;
      return (prevResult = f(x, y));
    }
  };
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/coordinate-transformation