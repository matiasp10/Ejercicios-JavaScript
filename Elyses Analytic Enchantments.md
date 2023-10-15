#Learning 
___
## Instrucciones

Elyse, futura maga, continúa su entrenamiento. Se le darán varios montones de cartas que necesitará para realizar sus trucos. Para facilitarle las cosas, sólo utiliza las cartas del 1 al 10.  
  
En este ejercicio, utiliza métodos integrados para analizar el contenido de una matriz.
## 1. Encontrar la posición de una carta  

Elyse quiere saber la posición (índice) de una carta en la pila.

```js
const card = 2;
getCardPosition([9, 7, 3, 2], card);
// => 3
```
### Mi solución

```js
export function getCardPosition(stack, card) {
  return stack.indexOf(card)
}
```
## 2. Determinar si una carta está presente  

Elyse quiere determinar si una carta está presente en la pila -- en otras palabras, si la pila contiene un número específico.

```js
const card = 3;
doesStackIncludeCard([2, 3, 4, 5], card);
// => true
```
### Mi solución

```js
export function doesStackIncludeCard(stack, card) {
  return stack.includes(card)
}
```
## 3. Determinar si cada carta es par  

Elyse quiere saber si todas las cartas son pares, es decir, si cada número de la pila es par.

```js
isEachCardEven([2, 4, 6, 7]); // => false
```
### Mi solución

```js
export function isEachCardEven(stack) {
  return stack.every(num => num % 2 === 0)
}
```
## 4. Comprobar si la pila contiene una carta impar  

Elyse quiere saber si hay un número impar en la pila.

```js
doesStackIncludeOddCard([3, 2, 6, 4, 8]);
// => true
```
### Mi solución

```js
export function doesStackIncludeOddCard(stack) {
  return stack.some(num => num % 2 !== 0)
}
```
## 5. Obtener la primera carta impar de la pila  

Elyse quiere saber el valor de la primera carta que es impar.

```js
getFirstOddCard([4, 2, 8, 7, 9]);
// => 7
```
### Mi solución

```js
export function getFirstOddCard(stack) {
  return stack.find(num => num % 2 !== 0)
}
```
## 6. Determinar la posición de la primera carta par 

Elyse quiere saber la posición de la primera carta par.

```js
getFirstEvenCardPosition([5, 2, 3, 1]);
// => 1
```
### Mi solución

```js
export function getFirstEvenCardPosition(stack) {
  return stack.findIndex(num => num % 2 === 0)
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/elyses-analytic-enchantments