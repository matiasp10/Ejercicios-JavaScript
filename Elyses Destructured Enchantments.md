#Learning 
___
## Introducción 
### Desestructuración de arrays

La sintaxis de desestructuración de arrays de JavaScript es una forma concisa de extraer valores de un array y asignarlos a variables distintas.  
  
En este ejemplo, cada valor de la matriz `numberOfMoons` se asigna a su planeta correspondiente:

```js
const numberOfMoons = [0, 2, 14];
const [venus, mars, neptune] = numberOfMoons;

neptune;
// => 14
```
### Rest y Spread

JavaScript tiene un operador `...` incorporado que facilita el trabajo con números indefinidos de elementos. Dependiendo del contexto, se denomina operador de resto u operador de dispersión.
#### Elementos Rest

Cuando `...` aparece en el lado izquierdo de una asignación, esos tres puntos se conocen como operador `rest`. Los tres puntos junto con un nombre de variable se denomina elemento resto. Recoge cero o más valores y los almacena en un único array.

```js
const [a, b, ...everythingElse] = [0, 1, 1, 2, 3, 5, 8];

everythingElse;
// => [1, 2, 3, 5, 8]
```

Tenga en cuenta que en JavaScript, a diferencia de otros lenguajes, un elemento `rest` no puede tener una coma al final. Debe ser el último elemento de una asignación de desestructuración.
#### Elementos Spread

Cuando `...` aparece a la derecha de una asignación, se conoce como operador `spread`. Expande un array en una lista de elementos. A diferencia del elemento resto, puede aparecer en cualquier parte de una expresión literal de matriz, y puede haber más de uno.

```js
const oneToFive = [1, 2, 3, 4, 5];
const oneToTen = [...oneToFive, 6, 7, 8, 9, 10];

oneToTen;
// => [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
___
## Instrucciones

Elyse, futura maga, continúa su entrenamiento. Tiene una baraja de cartas que quiere manipular.  
  
Para facilitarle las cosas, suele empezar sólo con las cartas numeradas del 1 al 10, aunque algunos trucos pueden incluir cartas adicionales.
## 1. Obtener la primera carta  

Elyse invocará la primera carta del mazo sin usar el `array[índice]` o `.shift()`. Es igual que la magia.

```js
const deck = [5, 9, 7, 1, 8];

getFirstCard(deck);
// => 5
```
### Mi solución

```js
export function getFirstCard(deck) {
  const [first] = deck
  return first
}
```
## 2. Obtener la segunda carta  

Elyse realiza un juego de manos e invoca la segunda carta de la baraja sin utilizar la `array[índice]`.

```js
const deck = [3, 2, 10, 6, 7];

getSecondCard(deck);
// => 2
```
### Mi solución

```js
export function getSecondCard(deck) {
  const [first, second] = deck
  return second
}
```
## 3. Intercambia las dos primeras cartas  

Elyse hará que las dos primeras cartas de la baraja cambien de lugar. No necesita llamar a ninguna función.

```js
const deck = [10, 7, 3, 8, 5];

swapTopTwoCards(deck);
// => [7, 10, 3, 8, 5]
```
### Mi solución

```js
export function swapTopTwoCards(deck) {
  const [first, second, ...everythingElse] = deck
  return [second, first, ...everythingElse]
}
```
## 4. Descartar la carta superior  

Elyse separará la baraja en dos montones. El primer montón contendrá sólo la carta superior del mazo original, mientras que el segundo montón contendrá todas las demás cartas.

```js
const deck = [2, 5, 4, 9, 3];

discardTopCard(deck);
// => [2, [5, 4, 9, 3]]
```
### Mi solución

```js
export function discardTopCard(deck) {
  const [topCard, ...everythingElse] = deck
  return [topCard, everythingElse]
}
```
## 5. Insertar cartas descubiertas 

Elyse introducirá en su baraja un grupo de cartas con la cara descubierta (es decir, sota, reina y rey) de forma que se conviertan en la segunda, tercera y cuarta carta, respectivamente.

```js
const deck = [5, 4, 7, 10];

insertFaceCards(deck);
// => [5, 'jack', 'queen', 'king', 4, 7, 10]
```
### Mi solución

```js
export function insertFaceCards(deck) {
  const [first, ...everythingElse] = deck
  return [first, ...FACE_CARDS, ...everythingElse]
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/elyses-destructured-enchantments