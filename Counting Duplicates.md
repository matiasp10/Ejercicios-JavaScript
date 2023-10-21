#6kyu 
___
Escriba una función que devuelva el recuento de caracteres alfabéticos y dígitos numéricos distintos sin distinción entre mayúsculas y minúsculas que aparecen más de una vez en la cadena de entrada. Se puede suponer que la cadena de entrada sólo contiene caracteres alfabéticos (tanto mayúsculas como minúsculas) y dígitos numéricos.
## Ejemplos

```js
"abcde" -> 0 # no characters repeats more than once
"aabbcde" -> 2 # 'a' and 'b'
"aabBcde" -> 2 # 'a' occurs twice and 'b' twice (`b` and `B`)
"indivisibility" -> 1 # 'i' occurs six times
"Indivisibilities" -> 2 # 'i' occurs seven times and 's' occurs twice
"aA11" -> 2 # 'a' and '1'
"ABBA" -> 2 # 'A' and 'B' each occur twice
```
## Link del problema

https://www.codewars.com/kata/54bf1c2cd5b56cc47f0007a1/train/javascript
## Mi solución

```js
function duplicateCount(text){
  text = text.toLowerCase()
  console.log(text)
  let count = {}
  for(let word of text){
    if(count[word]){
      count[word] += 1
    } else{
      count[word] = 1
    }
  }
  console.log(count)
  return Object.values(count).filter(word => word > 1).length
}
```