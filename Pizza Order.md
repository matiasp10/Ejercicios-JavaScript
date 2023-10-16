#Learning 
___
## Instrucciones

Tienes una pizzería y ofreces tres tipos de pizzas:  
  
- Margherita: 7  
- Caprese: 9  
- Formaggio: 10  

Si los clientes lo desean, pueden añadir un número ilimitado de opciones extra: "ExtraSauce" por 1$ o "ExtraToppings" por 2$.  
  
Tu tarea consiste en escribir un código que ayude al cliente a calcular el coste que le supone.
## Calcular el precio de una pizza  

Proporcionando el nombre de la pizza como primer argumento, y un número ilimitado de opciones añadidas, calcula el precio de la pizza en dólares.

```js
pizzaPrice('Margherita');
// => 7

pizzaPrice('Caprese', 'ExtraSauce', 'ExtraToppings');
// => 12

pizzaPrice(
  'Caprese',
  'ExtraToppings',
  'ExtraToppings',
  'ExtraToppings',
  'ExtraToppings',
);
// => 17
```
### Mi solución

```js
export function pizzaPrice(pizza, ...extras) {
  let price = pizza === "Margherita" ? 7 : pizza === "Caprese" ? 9 : 10;
  for (let extra of extras) {
    price += extra === "ExtraToppings" ? 2 : extra === "ExtraSauce" ? 1 : 0;
  }
  return price;
}

```
## Calcular el precio total de un pedido  

Su función es llamada con una lista de `PizzaOrders` y debe devolver el precio total del pedido en dólares. Cada `PizzaOrder` tiene una propiedad pizza - el nombre de la pizza, y una propiedad `extras` - la lista de opciones extra.

```js
const margherita = new PizzaOrder('Margherita');
const caprese = new PizzaOrder('Caprese', 'ExtraToppings');
orderPrice([margherita, caprese]);
// => 18
```

Te darás cuenta de que no puedes escribir esto usando recursividad, ya que una prueba con una tremenda cantidad de órdenes levantará un `Maximum call stack size exceeded`. No te preocupes, esto es intencionado - ¡intenta implementar esta función usando un bucle imperativo! Tienes muchas opciones, tales como, pero no limitadas a usar `reduce` o un bucle `for`.

>[!info] Avanzado
>Cuando el intérprete de JavaScript está ejecutando el código JavaScript, llevará la cuenta de las funciones que ha introducido (empezado a llamar) en una estructura de datos llamada "pila". Cuando la función regresa (finaliza), se elimina de la pila.  
>
>Sin embargo, esta pila tiene un tamaño limitado. El error más común que se comete es una función recursiva que nunca termina. Cada llamada se coloca en la pila, pero antes de que regrese, otra llamada se coloca en la pila.
>```js
>function kaboom() {
  kaboom()
}
kaboom()
// => RangeError: Maximum call stack size exceeded
>```
>El stacktrace de este error muestra la misma línea una y otra vez, lo que tiene sentido, porque la función se llama a sí misma. Aunque no tiene una aplicación práctica real en la mayoría de los casos, puedes averiguar lo alta que puede llegar a ser esa pila.
>````js
>let calls = 0;
function kaboom() {
  calls +=1 ;
  kaboom()
}
kaboom()
// => RangeError: Maximum call stack size exceeded
console.log(calls)
// => a number, generally higher than 10.000
>````
>Sólo hay dos soluciones viables para un error de pila de llamadas causado por una función recursiva síncrona:  
>- asegurarse de que las funciones retornan antes de que se alcance el límite de la pila, normalmente añadiendo o arreglando un caso base.  
>- reescribir la función recursiva a un bucle imperativo, que ejecutará el cuerpo del bucle, sin tener que entrar en una función, por lo tanto sin aumentar la pila.
### Mi solución

```js
export function orderPrice(pizzaOrders) {
  let total = 0;
  for (let order of pizzaOrders) {
    total += pizzaPrice(order.pizza, ...order.extras);
  }
  return total;
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/pizza-order