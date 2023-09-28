Toma una matriz y elimina uno de cada dos elementos de la matriz. Mantén siempre el primer elemento y empieza a eliminar con el siguiente.
### Ejemplo

```
["Keep", "Remove", "Keep", "Remove", "Keep", ...] --> ["Keep", "Keep", "Keep", ...]
```

Ninguna de las matrices estará vacía, así que no tienes que preocuparte por eso.
## Link del problema

https://www.codewars.com/kata/5769b3802ae6f8e4890009d2/train/javascript
## Mi solución

```js
function removeEveryOther(arr){
  let stack = []
  for(let i = 0; i < arr.length; i++){
    if(i % 2 === 0){
      stack.push(arr[i])
    }
  }
  return stack
}
```