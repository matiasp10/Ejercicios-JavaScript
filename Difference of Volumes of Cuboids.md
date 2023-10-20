#8kyu 
___
En este sencillo ejercicio, crearás un programa que tomará dos listas de enteros, `a` y `b`. Cada lista constará de 3 enteros positivos mayores que 0, que representan las dimensiones de los cuboides `a` y `b`. Deberás hallar la diferencia de los volúmenes de los cuboides independientemente de cuál sea mayor.  
  
Por ejemplo, si los parámetros pasados son `([2, 2, 3], [5, 4, 1])`, el volumen de `a` es 12 y el de `b` es 20. Por tanto, la función debe devolver 8. Por lo tanto, la función debe devolver 8.  
  
Tu función se probará con ejemplos prefabricados y con ejemplos aleatorios.  
## Link del problema

https://www.codewars.com/kata/58cb43f4256836ed95000f97/train/javascript
## Mi solución

```js
function findDifference(a, b) {
  return Math.abs((a[0] * a[1] * a[2]) - (b[0] * b[1] * b[2]))
}
```