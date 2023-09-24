Simple, dada una cadena de palabras, devuelve la longitud de la(s) palabra(s) más corta(s).  
  
La cadena nunca estará vacía y no es necesario tener en cuenta los diferentes tipos de datos.

## Link del problema

https://www.codewars.com/kata/57cebe1dc6fdc20c57000ac9/train/javascript

## Mi solución

```js
function findShort(s){
  let arr = s.split(" ")
  return arr.sort((a,z)=> a.length-z.length)[0].length
}
```
