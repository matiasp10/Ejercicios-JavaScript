# Recuento de vocales

Devuelve el número (cuenta) de vocales en la cadena dada.

Consideraremos a, e, i, o, u como vocales para esta Kata (pero no y).

La cadena de entrada solo constará de minúsculas y/o espacios.

## Link al problema

[Problema](https://www.codewars.com/kata/54ff3102c1bad923760001f3/train/javascript)

## Mi solución

```js
function getCount(str) {
  let splitedWord = str.split('');
  let count = 0;
  for (let word of splitedWord) {
    if (
      word === 'a' ||
      word === 'e' ||
      word === 'i' ||
      word === 'o' ||
      word === 'u'
    ) {
      count += 1;
    }
  }
  return count;
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]