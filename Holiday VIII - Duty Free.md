#8kyu 
___
El objetivo de esta kata es calcular cuántas botellas de whisky libre de impuestos tendría que comprar para que el ahorro sobre el precio normal en la calle cubriera el coste de sus vacaciones.

Se le dará el precio en la calle (`normPrice`, en £ (Libras)), el descuento libre de impuestos (`discount`, en porcentaje) y el coste de las vacaciones (en £).

Por ejemplo, si una botella cuesta normalmente 10 £ y el descuento libre de impuestos es del 10%, te ahorrarías 1 £ por botella. Si tus vacaciones van a costar 500 £, tendrías que comprar 500 botellas para ahorrar 500 £, así que la respuesta que devuelvas debe ser 500.

Otro ejemplo: si una botella cuesta normalmente 12 £ y el descuento libre de impuestos es del 50%, te ahorrarías 6 £ por botella. Si sus vacaciones cuestan 1.000 ¤, tendrá que comprar 166,66 botellas para ahorrarse 1.000 ¤, por lo que la respuesta será 166 botellas.

Todas las entradas serán números enteros. Devuelva un número entero. Redondear por defecto

## Link del problema

https://www.codewars.com/kata/57e92e91b63b6cbac20001e5/train/javascript

## Mi solución

```js
function dutyFree(normPrice, discount, hol){
  const priceDiscount = normPrice * (discount / 100)
  return Math.floor(hol / priceDiscount)
}
```
