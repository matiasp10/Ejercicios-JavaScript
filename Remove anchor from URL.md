#7kyu 
___
Completa la función/método para que devuelva la url sin nada después del ancla (#).
## Ejemplos

```js
"www.codewars.com#about" --> "www.codewars.com"
"www.codewars.com?page=1" -->"www.codewars.com?page=1"
```
## Link del problema

https://www.codewars.com/kata/51f2b4448cadf20ed0000386/train/javascript
## Mi solución

```js
function removeUrlAnchor(url){
  return url.split("#")[0]
}
```
