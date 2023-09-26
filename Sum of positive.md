Obtiene un array de números, devuelve la suma de todos los positivos.  
  
Ejemplo `[1,-4,7,12] => 1 + 7 + 12 = 20`  
  
Nota: si no hay nada que sumar, la suma es por defecto 0.

## Link del problema 

https://www.codewars.com/kata/5715eaedb436cf5606000381/train/javascript

## Mi solución

```js
function positiveSum(arr) {
  let sum = 0
  for(let num of arr){
    if(num > 0) sum += num
  }
  return sum
}
```
