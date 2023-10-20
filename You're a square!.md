#7kyu 
___
# Un cuadrado de cuadrados

Te gustan los bloques de construcción. Te gustan especialmente los bloques de construcción cuadrados. Y lo que aún te gusta más es colocarlos en un cuadrado de bloques de construcción cuadrados.

Sin embargo, a veces no puedes colocarlos en un cuadrado. En vez de eso, acabas con un rectángulo normal y corriente. ¡Maldición! Si tuvieras una forma de saber si estás trabajando en vano... ¡Espera! ¡Eso es! Sólo tienes que comprobar si tu número de bloques de construcción es un cuadrado perfecto.

## Tarea

Dado un número entero, determina si es un número cuadrado:

> [!note] Nota
> En matemáticas, un número cuadrado o cuadrado perfecto es un número entero que es el cuadrado de un número entero; en otras palabras, es el producto de algún número entero por sí mismo.

Las pruebas siempre utilizarán algún número entero, así que no te preocupes por eso en lenguajes de tipado dinámico.

## Link del problema

[Problema](https://www.codewars.com/kata/54c27a33fb7da0db0100040e/train/javascript)

## Mi solución

```js
let isSquare = function (n) {
  // Ya que los cuadrados perfectos son los numeros que poseen raices cuadradas exactas, le calculo la raiz cuadrada de cada numero y devuelvo con el metodo isInteger() true si es un entero exacto o false si es con punto flotante.
  let raizCuadrada = Math.sqrt(n);
  return Number.isInteger(raizCuadrada);
};
```

-   [Math.sqrt()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt)
-   [Number.isInteger()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger)

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]