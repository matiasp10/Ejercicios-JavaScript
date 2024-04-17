#7kyu 
___
Escribe una función llamada sumaDígitos que tome un número como entrada y devuelva la suma del valor absoluto de cada uno de los dígitos decimales del número.

## Ejemplos (Entrada --> Salida)

```js
10 --> 1
99 --> 18
-32 --> 5
```

Supongamos que todos los números de la entrada serán valores enteros.

## Link del problema

https://www.codewars.com/kata/52f3149496de55aded000410/train/javascript

## Mi solución

```js
function sumDigits(number) {
  let sum = 0;

  number = String(Math.abs(number));

  for (let num of number) {
    sum += Number(num);
  }

  return sum;
}
```
