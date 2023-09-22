Tu tarea consiste en encontrar el primer elemento de una matriz que no sea consecutivo.  
  
Por no consecutivo entendemos que no sea exactamente 1 mayor que el elemento anterior de la matriz.  
  
Por ejemplo, si tenemos una matriz `[1,2,3,4,6,7,8]`, el 1, el 2, el 3 y el 4 son todos consecutivos, pero el 6 no lo es, así que ése es el primer número no consecutivo.  
  
Si todo el array es consecutivo entonces devuelve `null`$^2$.  
  
La matriz siempre tendrá al menos 2 elementos y todos los elementos serán números. Además, todos los números serán únicos y estarán en orden ascendente. Los números pueden ser positivos o negativos y el primero no consecutivo puede ser cualquiera de los dos.

## Link del problema

https://www.codewars.com/kata/58f8a3a27a5c28d92e000144/train/javascript

## Mi solución 

```js
function firstNonConsecutive(arr) {
  let nonConsecutive = []
  for(let i = 0; i < arr.length; i++){
    if(!(arr[i] - 1 === arr[i - 1]) && i !== 0){
      nonConsecutive.push(arr[i])
    } 
  }
  if(nonConsecutive.length === 0) return null
  return nonConsecutive[0]
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]