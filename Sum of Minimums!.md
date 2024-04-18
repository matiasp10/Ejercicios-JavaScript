#7kyu 
___
Dada una lista 2D ( anidada ) ( array, vector, .. ) de tamaño `m * n`, tu tarea es encontrar la suma de los valores mínimos de cada fila.

## Ejemplo

```js
[ [ 1, 2, 3, 4, 5 ]       #  minimum value of row is 1
, [ 5, 6, 7, 8, 9 ]       #  minimum value of row is 5
, [ 20, 21, 34, 56, 100 ] #  minimum value of row is 20
]
```

Así que la función debería devolver `26` porque la suma de los mínimos es `1 + 5 + 20 = 26`.  

> [!note] Nota
> Siempre se le dará una lista no vacía que contenga valores positivos.

## Link del problema

https://www.codewars.com/kata/5d5ee4c35162d9001af7d699/train/javascript

## Mi solución

```js
function sumOfMinimums(arr) {
  let sum = 0
  for(let arreglo of arr){
    sum += Math.min(...arreglo)
  }
  return sum
}
```
