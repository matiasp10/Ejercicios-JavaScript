#7kyu 
___
Escriba una función que tome como argumento una única cadena no vacía de sólo letras ascii minúsculas y mayúsculas(`word`), y devuelva una lista ordenada que contenga los índices de todas las letras mayúsculas de la cadena.

## Ejemplo

```js
"CodEWaRs" --> [0,3,4,6]
```

## Link del problema

https://www.codewars.com/kata/539ee3b6757843632d00026b/train/javascript

## Mi solución 

```js
var capitals = function (word) {
  let length = word.length
  let capitals = []
	for (let i = 0; i < length; i++) {
    if(word[i] === word[i].toUpperCase()){
      capitals.push(i)
    }
  }
  return capitals
};
```
