#7kyu 
___
Se da una matriz `arr` de índice cero formada por n enteros. El dominador de la matriz `arr` es el valor que aparece en más de la mitad de los elementos de `arr`.  
Por ejemplo, consideremos una matriz `arr` tal que `arr = [3,4,3,2,3,1,3,3]`.  
El dominador de `arr` es **3** porque aparece en 5 de los 8 elementos de `arr` y 5 es más de la mitad de 8.  
Escriba una función `dominator(arr)` que, dada una matriz de índice cero `arr` formada por n enteros, devuelva el dominador de `arr`. La función debe devolver **-1** si `arr` _no tiene dominador_. Todos los valores de `arr` serán >=0.

## Link del problema

[Link](https://www.codewars.com/kata/559e10e2e162b69f750000b4/train/javascript)

## Mi solución 

```js file:dominator.js
function dominator(arr) {
  let stack = {};
  for (let num of arr) {
    if (num < 0) return -1;
    stack[num] = stack[num] ? stack[num] + 1 : 1;
  }
  const result = Object.entries(stack).sort(([, a], [, z]) => z - a);
  if (result[0][1] === result[1][1] || result[0][1] < arr.length / 2) return -1;

  return Number(result[0][0]);
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]