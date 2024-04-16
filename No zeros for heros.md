#8kyu 
___
Los números que acaban en ceros son aburridos.
Pueden ser divertidos en tu mundo, pero no aquí.
Deshazte de ellos. Sólo los que terminan en uno.

## Ejemplo

```
1450 -> 145
960000 -> 96
1050 -> 105
-1050 -> -105
```

Cero solo está bien, no te preocupes. Pobre tipo de todos modos.

## Link del problema

https://www.codewars.com/kata/570a6a46455d08ff8d001002/train/javascript

## Mi solución

```js
function noBoringZeros(n) {
  n = String(n);
  while (n[n.length - 1] === "0") {
    n = n.slice(0, n.length - 1);
  }
  return Number(n);
}
```
