# Giga segundos

Dado un momento, determina el momento en que transcurriría un giga segundo.

Un giga segundo son 10^9 (1.000.000.000) segundos.

## Notas

La entrada y salida de la función `gigasecond` es de tipo Fecha.

Es posible devolver un valor correcto para este ejercicio mutando el argumento de la función solución. Aunque hay casos de uso legítimos para mutar argumentos de función, esto es normalmente indeseable, y en el caso de este ejercicio, claramente inesperado. Por esta razón, el conjunto de pruebas tiene una prueba que falla en caso de que el argumento haya sido modificado después de la ejecución de la función.

## Link al problema

[https://exercism.org/tracks/javascript/exercises/gigasecond](https://exercism.org/tracks/javascript/exercises/gigasecond)

## Mi solución

```js
const GIGASECOND = 1e12

export const gigasecond = (date) => {
  return new Date(date.getTime() + GIGASECOND);
};
```

En una constante almacené el valor de lo que sería un giga segundo pasado a milisegundos para poder sumarlo posteriormente al objeto `Date`.

Al final devuelvo una nueva fecha de la fecha que recibo en la función sumado un giga segundo.