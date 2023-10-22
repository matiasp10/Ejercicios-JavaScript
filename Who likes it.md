#6kyu 
____
Probablemente conozcas el sistema de "me gusta" de Facebook y otras páginas. La gente puede dar "me gusta" a entradas de blog, fotos u otros elementos. Queremos crear el texto que debe aparecer junto a un elemento de este tipo.  
  
Implementar la función que toma una matriz que contiene los nombres de las personas que como un elemento. Debe devolver el texto que se muestra en los ejemplos:

```js
[]                                -->  "no one likes this"
["Peter"]                         -->  "Peter likes this"
["Jacob", "Alex"]                 -->  "Jacob and Alex like this"
["Max", "John", "Mark"]           -->  "Max, John and Mark like this"
["Alex", "Jacob", "Mark", "Max"]  -->  "Alex, Jacob and 2 others like this"
```

Nota: Para 4 o más nombres, el número en "y otros 2" simplemente aumenta.
## Link del problema

https://www.codewars.com/kata/5266876b8f4bf2da9b000362/train/javascript
## Mi solución

```js
function likes(names) {
  let l = names.length
  if(l === 0) return "no one likes this"
  if(l === 1) return `${names[0]} likes this`
  if(l === 2) return `${names[0]} and ${names[1]} like this`
  if(l === 3) return `${names[0]}, ${names[1]} and ${names[2]} like this`
  if(l > 3) return `${names[0]}, ${names[1]} and ${l - 2} others like this`
}
```
