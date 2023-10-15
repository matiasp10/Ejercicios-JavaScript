#Learning 
___
## Instrucciones

Elyse, futura maga, continúa su entrenamiento. Le darán una baraja de cartas e intentará transformarla. Hará que algunas cartas aparezcan, desaparezcan, cambien de valor o se reorganicen por completo. Para facilitar las cosas, suele empezar sólo con cartas numeradas del 1 al 10, aunque algunos de los trucos pueden dar lugar a la creación de cartas más grandes.
## 1. Doblar todas las cartas  

Elyse quiere doblar el número de cada carta de la baraja. Esto puede dar como resultado cartas más altas que 1-10.

```js
const deck = [1, 2, 3, 4, 10];
seeingDouble(deck);
// => [2, 4, 6, 8, 20]
```
### Mi solución

```js
export function seeingDouble(deck) {
  return deck.map((num)=> num * 2)
}
```
## 2. Crear múltiples copias de cada 3 encontrados en la baraja  

Elyse quiere triplicar cada 3 encontrado en la baraja. Si la baraja empezara con un solo 3, después del truco la baraja tendría tres 3 en lugar del original.

```js
const deck = [1, 3, 9, 3, 7];
threeOfEachThree(deck);
// => [1, 3, 3, 3, 9, 3, 3, 3, 7]
```
### Mi solución

```js
export function threeOfEachThree(deck) {
  let result = []
  for(let num of deck){
    if(num === 3){
      result.push(3,3,3)
    } else {
      result.push(num)
    }
  }
  return result
}
```
## 3. Encuentra dos cartas del centro exacto de la baraja  

Elyse cogerá una baraja de diez cartas y hará desaparecer todas las cartas excepto las dos del medio.

```js
const deck = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
middleTwo(deck);
// => [5, 6]
```
### Mi solución

```js
export function middleTwo(deck) {
  let middle = Math.floor(deck.length / 2)
  return [deck[middle-1], deck[middle]]
}
```
## 4. Las dos cartas exteriores reaparecerán en el centro de la baraja.  

Elyse quiere mover las cartas superior e inferior de la baraja al centro, en orden inverso.  
  
Puedes suponer que la baraja tiene un número par de cartas.

```js
const deck = [1, 2, 3, 5, 6, 10];
sandwichTrick(deck);
// => [2, 3, 10, 1, 5, 6]
```
### Mi solución

```js
export function sandwichTrick(deck) {
  let first = deck.shift()
  let last = deck.pop()
  let middleDown = deck.slice(0, deck.length / 2)
  let middleUp = deck.slice( (deck.length / 2), deck.length)
  return [...middleDown,last, first ,...middleUp]
}
```
## 5. Toda carta que no sea un 2 desaparece  

El número favorito de Elyse hoy es el 2. En este truco, todas las cartas que no sean un 2 desaparecerán de la baraja.

```js
const deck = [1, 2, 3, 4, 10, 2];
twoIsSpecial(deck);
// => [2, 2]
```
### Mi solución

```js
export function twoIsSpecial(deck) {
  return deck.filter(num=> num ===2)
}
```
## 6. Convertir una baraja barajada en una baraja perfectamente ordenada  

Elyse desea demostrar su maestría a la hora de reordenar perfectamente las cartas, por muy bien barajadas que estén.

```js
const deck = [10, 1, 5, 3, 2, 8, 7];
perfectlyOrdered(deck);
// => [1, 2, 3, 5, 7, 8, 10]
```
### Mi solución

```js
export function perfectlyOrdered(deck) {
  return deck.sort((a,z)=> a - z)
}
```
## 7. Reordenar la baraja  

Elyse quiere cambiar el orden de las cartas de la baraja. Después del truco, la carta que actualmente está en la parte superior debe terminar en la parte inferior de la baraja. La segunda carta debe acabar en penúltimo lugar, etc.

```js
const deck = [10, 1, 5, 3, 2];
reorder(deck);
// => [2, 3, 5, 1, 10]
```
### Mi solución

```js
export function reorder(deck) {
  return deck.reverse()
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/elyses-transformative-enchantments
