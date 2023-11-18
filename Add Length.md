#8kyu 
___
¿Y si necesitamos que la longitud de las palabras separadas por un espacio se añada al final de esa misma palabra y se devuelva como un array?
## Ejemplo

```js
"apple ban" --> ["apple 5", "ban 3"]
"you will win" -->["you 3", "will 4", "win 3"]
```

Su tarea consiste en escribir una función que tome una cadena y devuelva un array/lista con la longitud de cada palabra añadida a cada elemento.  
  
>[!note] Nota
>La cadena tendrá al menos un elemento; las palabras siempre estarán separadas por un espacio.
## Link del problema

https://www.codewars.com/kata/559d2284b5bb6799e9000047/train/javascript
## Mi solución

```js
function addLength(str) {
  str = str.split(" ")
  let stack = []
  for (let word of str){
    stack.push(word + " " + word.length)
  }
  return stack
}
```