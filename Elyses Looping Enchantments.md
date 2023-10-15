#Learning 
___
## Instrucciones 

Como maga en ciernes, Elyse necesita analizar su baraja de muchas formas distintas. Para simplificar las cosas, solo utiliza cartas con valores del 1 al 10.
## 1. Determinar cuántas cartas de un determinado tipo hay en la baraja  

Elyse quiere saber cuántas cartas de un determinado tipo tiene en su baraja.  
  
Escribe una función `cardTypeCheck` que tome dos parámetros: un array de cartas (la baraja de Elyse) y el tipo de carta a contar. La función debe usar `forEach` y devolver el número de cartas del mazo del tipo especificado.

```js
const cardType = 3;
cardTypeCheck([1, 2, 3, 4], cardType);
// => 1
```
### Mi solución

```js
export function cardTypeCheck(stack, card) {
  let count = 0
  stack.forEach((num)=>{
    if(num === card){
      count++
    }
  })
  return count
}
```
## 2. Determinar cuántas cartas pares o impares hay

Para otro truco, Elyse necesita saber cuántas cartas pares o impares hay en su baraja.  
  
Implementa una función `determineOddEvenCards` que reciba dos parámetros: un array de cartas (la baraja de Elyse), y un booleano (verdadero es análogo a "par", y falso es análogo a "impar").  
  
Esta función debería devolver un único número: el número de cartas pares o impares que hay (dependiendo del valor del segundo argumento) en la baraja. Para practicar, utiliza esta vez un bucle `for...of` en la implementación de la función.

```js
determineOddEvenCards([1, 2, 3, 1, 5, 6], true);
// => 2

determineOddEvenCards([1, 2, 3, 1, 5, 6], false);
// => 4
```
### Mi solución

```js
export function determineOddEvenCards(stack, type) {
  let odd = 0
  let even = 0
  stack.forEach((num)=>{
    if(num % 2 === 0){
      even++
    } else {
      odd++
    }
  })
  if(type === false) return odd
  if(type === true) return even
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/elyses-looping-enchantments