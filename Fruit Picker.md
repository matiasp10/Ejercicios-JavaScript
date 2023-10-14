#Learning 
___
## Introducción 
### Funciones callbacks

Las funciones callback son funciones que se pasan como argumentos. Este patrón de programación crea una secuencia de llamadas a funciones tanto en programación síncrona como asíncrona. Escribir una función de llamada de retorno no difiere de escribir una función; sin embargo, la función de llamada de retorno debe coincidir con la firma definida por la función de llamada.

```js
const squareLength = 5;

// Caller function takes a callback function
function applyToSquare(callback) {
  return callback(squareLength);
}

// Callback must expect the possible argument from the calling function
function areaOfSquare(number) {
  return number * number;
}

applyToSquare(areaOfSquare); // => 25
```

También puede escribir callbacks como una expresión de función:

```js
applyToSquare(function squarePerimeter(side) {
  return side * 4;
});
```
___
## Instrucciones 

Está creando un nuevo portal en línea para que sus clientes puedan pedir fruta fresca al tendero. El ultramarinos tiene una API que usted puede utilizar para ver si tienen el inventario deseado por sus clientes. Usted necesita crear una pequeña biblioteca de funciones para interactuar con la API de la tienda de comestibles.
## 1. Crear una llamada de retorno para ser llamada cuando la orden es exitosa.  

Escriba una función de llamada de retorno llamada `onSuccess` para que sea llamada cuando la orden sea exitosa. Debería invocar la función importada `notify` pasándole un mensaje de éxito.

```js
onSuccess();
// => `notify` called with `{ message: 'SUCCESS' }`
```
### Mi solución

```js
export function onSuccess() {
  return notify({message: "SUCCESS"})
}
```
## 2. Crear una función callback para ser llamada cuando la orden falle con un error.  

Escribe una función `callback` llamada `onError` para ser llamada cuando la orden encuentre un error. Debería invocar la función importada `notify` pasándole un mensaje de error.

```js
onError();
// => `notify` called with `{ message: 'ERROR' }`
```
### Mi solución

```js
export function onError() {
  return notify({message: "ERROR"})
}
```
## 3. Crear un wrapper para envolver la función api externa  

La API del supermercado proporciona una función para realizar pedidos de su inventario llamada `order`. Recibe tres argumentos: una consulta, una función callback que se invoca cuando el pedido se realiza correctamente y una función callback que se invoca cuando el pedido encuentra un error. Usted decide envolver la llamada a la función api en una función recién definida `orderFromGrocer` para aislar su código base de cambios externos. Su función debe reenviar los argumentos (que coinciden con la función api proporcionada) a la función api.  
  
La consulta toma la forma de un objeto:

```js
const query = {
  variety: string,
  quantity: number,
};
```

```js
orderFromGrocer(
  { variety: 'pear', quantity: 12 },
  exampleSuccessCallback,
  exampleErrorCallback,
);
// => `order` was called with the query and the callbacks
```
### Mi solución

```js
export function orderFromGrocer(query, onSuccessCallback, onErrorCallback) {
  return order(query, onSuccessCallback, onErrorCallback)
}
```
## 4. Crear una función corta conveniente  

Te das cuenta de que estás llamando a esta función desde muchos lugares diferentes con las mismas funciones. Viendo una oportunidad para refactorizar su código, quiere crear una función en la que pueda suministrar la variedad y la cantidad a pedir como argumentos.

```js
postOrder('peach', 100);
// => order submitted for 100 peaches
```
### Mi solución

```js
export function postOrder(variety, quantity) {
  return orderFromGrocer({variety:variety, quantity:quantity}, onSuccess, onError )
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/fruit-picker