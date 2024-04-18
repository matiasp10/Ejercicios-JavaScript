#7kyu 
___
Dado un número entero como entrada, ¿puedes redondearlo al siguiente (es decir, "mayor o igual") múltiplo de 5?

```
input:    output:
0    ->   0
2    ->   5
3    ->   5
12   ->   15
21   ->   25
30   ->   30
-2   ->   0
-5   ->   -5
etc.
```

La entrada puede ser cualquier número entero positivo o negativo (incluido 0).

Puede asumir que todas las entradas son enteros válidos.
## Link del problema

https://www.codewars.com/kata/55d1d6d5955ec6365400006d/train/javascript

## Mi solución

```js
function roundToNext5(n) {
  return Math.ceil(n / 5) * 5;
}
```