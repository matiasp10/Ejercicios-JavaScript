Defina `String.prototype.toAlternatingCase` (o una función/método similar como `to_alternating_case`/`toAlternatingCase`/`ToAlternatingCase` en el idioma seleccionado; consulte la solución inicial para obtener más detalles) de forma que cada letra minúscula se convierta en mayúscula y cada letra mayúscula se convierta en minúscula. Por ejemplo:

```javascript
"hello world".toAlternatingCase() === "HELLO WORLD"
"HELLO WORLD".toAlternatingCase() === "hello world"
"hello WORLD".toAlternatingCase() === "HELLO world"
"HeLLo WoRLD".toAlternatingCase() === "hEllO wOrld"
"12345".toAlternatingCase()       === "12345"                   // Non-alphabetical characters are unaffected
"1a2b3c4d5e".toAlternatingCase()  === "1A2B3C4D5E"
"String.prototype.toAlternatingCase".toAlternatingCase() === "sTRING.PROTOTYPE.TOaLTERNATINGcASE"
```

Como siempre, tu función/método debe ser puro, es decir, no debe mutar la cadena original.
## Link del problema

https://www.codewars.com/kata/56efc695740d30f963000557/train/javascript
## Mi solución

```js
String.prototype.toAlternatingCase = function () {
  let stack = []
  for(let word of this){
    if(word === word.toUpperCase()){
      stack.push(word.toLowerCase())
    } else {
      stack.push(word.toUpperCase())
    }
  }
  return stack.join("")
}
```