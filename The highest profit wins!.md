Ben tiene una idea muy sencilla para obtener beneficios: compra algo y lo vuelve a vender. Por supuesto, esto no le daría ningún beneficio si se limitara a comprarlo y venderlo al mismo precio. En lugar de eso, va a comprarlo al precio más bajo posible y venderlo al más alto.

Escribe una función que devuelva tanto el número mínimo como el máximo de la lista/matriz dada.

## Ejemplos

```
[1,2,3,4,5] --> [1,5]
[2334454,5] --> [5,2334454]
[1]         --> [1,1]
```

Todas las matrices o listas siempre tendrán al menos un elemento, por lo que no es necesario comprobar la longitud. Además, tu función siempre obtendrá un array o una lista, no tienes que comprobar si es nulo, indefinido o similar.

## Link del problema

https://www.codewars.com/kata/559590633066759614000063/train/javascript

## Mi solución

```js
function minMax(arr){
 return [Math.min(...arr),Math.max(...arr)]
}
```
