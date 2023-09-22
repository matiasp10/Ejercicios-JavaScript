# Latín de los cerdos

Mueve la primera letra de cada palabra al final de la misma y añade "ay" al final de la palabra. Deja intactos los signos de puntuación.

## Ejemplo

```js
pigIt('Pig latin is cool'); // igPay atinlay siay oolcay
pigIt('Hello world !');     // elloHay orldway !
```

## Link del problema

[Problema](https://www.codewars.com/kata/520b9d2ad5c005041100000f/train/javascript)
## Mi solución

```js
function pigIt(str) {
  let phraseLatinPig = [];
  let splitedPhrase = str.split(' ');
  for (let word of splitedPhrase) {
    if (word === '!' || word === '?' || word === '.') {
      phraseLatinPig.push(word);
    } else {
      let wordLatinPig = word.slice(1) + word[0] + 'ay';
      phraseLatinPig.push(wordLatinPig);
    }
  }
  return phraseLatinPig.join(' ');
}
```

Primero inicialice una **variable** `phraseLatinPig` como un **array vacio**, el cual sera el que va a contener todas las palabras modificadas.  
Luego dividi la frase en palabras (mediante el metodo `.split()`) para poder modificarlas una por una mediante un **bucle**.

Recorri el **array** donde estaban contenidas las palabras divididas (`splitedPhrase`) mediante un **bucle** `for...of`.  
Dentro del **bucle** utilice un **condicional** (`if...else`) para verificar si la palabra en cuestion era un signo de puntuacion, el cual debia ser devuelto sin ningun cambio, por ende si se cumple la condicion hago un `.push()` del signo de puntuacion al array que inicialice al comienzo.  
Si la palabra no era un signo de puntuacion devuelvo el **resto de la palabra sin la primer letra** = `word.slice(1)`, la **primer letra** = `word[0]` y le agrego al final `"ay"`, finalmente hago un `.push()` al array que inicialice al comienzo.

Finalmente devuelvo mediante un metodo `.join(" ")` del array que inicialice al comienzo la frase convertida en **latín de los cerdos**.

-   [.slice()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String/slice)
-   [.split()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/String/split)
-   [for...of](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/for...of)
-   [if...else](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/if...else)
-   [Latín de los cerdos](https://es.wikipedia.org/wiki/Pig_Latin)

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]