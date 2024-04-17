#7kyu 
____

Se dan dos matrices `a1y` `a2de`cadenas. Cada cadena está compuesta por letras de `la a a la` `z`. `Seax` cualquier cadena de la primera matriz e `y`cualquier cadena de la segunda matriz.  

Hallar `max(abs(longitud(x) - longitud(y)))`  

Si `a1` y/o `a2` están vacíos devuelve `-1` en cada lenguaje excepto en Haskell (F#) donde devolverás `Nothing`(None).

## Ejemplos

```js
a1 = ["hoqq", "bbllkw", "oox", "ejjuyyy", "plmiis", "xxxzgpsssa", "xxwwkktt", "znnnnfqknaz", "qqquuhii", "dvvvwz"]
a2 = ["cccooommaaqqoxii", "gggqaffhhh", "tttoowwwmmww"]
mxdiflg(a1, a2) --> 13
```

#### **Nota Bash:**  

- entrada : 2 cadenas con subcadenas separadas por `,`  
- salida: número como cadena

## Link del problema

https://www.codewars.com/kata/5663f5305102699bad000056/train/javascript

## Mi solución

```js
function mxdiflg(a1, a2) {
  if(a1.length === 0 || a2.length === 0) return -1
  let strings1 = []  
  let strings2 = []
  
  for  (s1 of a1){
    strings1.push(s1.length)    
  }
  for  (s2 of a2){
    strings2.push(s2.length)    
  }
  strings1.sort((a,z)=> a - z)
  strings2.sort((a,z)=> a - z)
  
  let minA1 = Math.min(...strings1)
  let minA2 = Math.min(...strings2)
  let maxA1 = Math.max(...strings1)
  let maxA2 = Math.max(...strings2)
  console.log(minA1, strings1, minA2, strings2)
  console.log(maxA1, strings1, maxA2, strings2)
  let test1 = Math.abs(minA1 - maxA2)
  let test2 = Math.abs(minA2 - maxA1)
  
  return Math.max(test1, test2)
}
```
