# ¡Deja de ralih mis sarbalap!

Escriba una función que reciba una cadena de una o más palabras y devuelva la misma cadena, pero con todas las palabras de cinco o más letras invertidas (como el nombre de esta Kata). Las cadenas introducidas constarán solo de letras y espacios. Los espacios se incluirán solo cuando haya más de una palabra.

## Link al problema

[Problema](https://www.codewars.com/kata/5264d2b162488dc400000001/train/javascript)

## Mi solución

```js
function spinWords(string) {
  let words = string.split(" ")
  let spinWords = []
  for (let word of words){
    if (word.length >= 5){
      let wordSplit = word.split("")
      let reversedWord = wordSplit.reverse()
      let wordJoin = reversedWord.join("")
      spinWords.push(wordJoin)
    } else {
      spinWords.push(word)
    }
  }
  return spinWords.join(" ")
}
```