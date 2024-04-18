#7kyu 
___
Un isograma es una palabra que no tiene letras repetidas, consecutivas o no consecutivas. Implementa una función que determine si una cadena que sólo contiene letras es un isograma. Suponga que la cadena vacía es un isograma. Ignore las mayúsculas y minúsculas.

## Ejemplo

```js
isIsogram "Dermatoglyphics" = true
isIsogram "moose" = false
isIsogram "aba" = false
```

## Link del problema

https://www.codewars.com/kata/54ba84be607a92aa900000f1/train/javascript

## Mi solución

```js
function isIsogram(str){
  const string = str.toLowerCase()
  let aux = []
  for(let s of string){
    if(aux.includes(s)) return false
    aux.push(s)
  }
  return true
}
```
