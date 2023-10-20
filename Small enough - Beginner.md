#7kyu 
___
Se le dará una matriz y un valor límite. Debe comprobar que todos los valores de la matriz son inferiores o iguales al valor límite. Si es así, devuelve true. Si no, devuelve false.  
  
Puedes asumir que todos los valores del array son números.
## Link del problema

https://www.codewars.com/kata/57cc981a58da9e302a000214/train/javascript
## Mi solución

```js
function smallEnough(a, limit){
  return a.every(value => value <= limit)
}
```