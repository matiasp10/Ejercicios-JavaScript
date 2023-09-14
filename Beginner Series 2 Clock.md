El reloj muestra `h` horas, `m` minutos y `s` segundos después de medianoche.  
  
Tu tarea es escribir una función que devuelva el tiempo transcurrido desde medianoche en milisegundos.

## Link del problema

https://www.codewars.com/kata/55f9bca8ecaa9eac7100004a/train/javascript

## Mi solución

```js
function past(h, m, s){
  return h * 3600000 + m * 60000 + s * 1000
}
```
