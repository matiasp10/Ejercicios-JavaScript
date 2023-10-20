#6kyu 
___
La idea principal es contar todos los caracteres que aparecen en una cadena. Si tienes una cadena como aba, entonces el resultado debería ser `{'a': 2, 'b': 1}`.  
  
¿Y si la cadena está vacía? Entonces el resultado debería ser un objeto literal vacío, `{}`.

## Link del problema

https://www.codewars.com/kata/52efefcbcdf57161d4000091/train/javascript
## Mi solución

```js
function count(string) {
  let stack = {}
  for(let word of string){
    if (!stack[word]){
      stack[word] =+ 1
    } else {
      stack[word]++
    }
  }
  return stack
}
```
