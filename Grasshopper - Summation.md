Escribe un programa que encuentre la suma de cada número de 1 a num. El número siempre será un entero positivo mayor que 0.

## Ejemplo

```
2 -> 3 (1 + 2)
8 -> 36 (1 + 2 + 3 + 4 + 5 + 6 + 7 + 8)
```

## Link del problema

https://www.codewars.com/kata/55d24f55d7dd296eb9000030/train/javascript

## Mi solución

```js
function summation(num) {
  if(num > 0){
    return num + summation(num - 1)
  } else {
    return num
  }
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]