# Múltiplos de 3 o 5

Si enumeramos todos los números naturales menores que 10 que son múltiplos de 3 o 5, obtenemos 3, 5, 6 y 9. La suma de estos múltiplos es 23. La suma de estos múltiplos es 23.

Terminar la solución para que devuelva la **suma** de todos los múltiplos de **3** o **5** por debajo del número introducido. Además, si el número es negativo, devuelve 0 (para los idiomas que los tienen).

> [!note] Nota
> Si el número es múltiplo de 3 y de 5, solo se cuenta una vez.

## Link al problema

[Problema](https://www.codewars.com/kata/514b92a657cdc65150000006/train/javascript)

## Mi solución

```js
function solution(number){
  let result = 0
  if (number < 0) {
    return 0
  }
  for(let i = 0; i < number; i++){
    if(i % 3 === 0 || i % 5 === 0){
     result += i
    }
  }
  return result
}
```

Inicializo una variable en la cual voy a colocar la suma de los múltiplos.

Luego verifico si el número ingresado a la función es negativo en un condicional, preguntándome si es menor a 0 y devolviendo 0.

En un bucle `for` voy recorriendo desde 0 al número ingresado a la función, y con un condicional voy encontrando todos aquellos valores que resto 3 o resto 5 den como resultado 0, lo cual verificaría que sea múltiplo de 3 o 5, si se da la condición le sumo ese número a la variable que inicialice al comienzo de la función y por último devuelvo esa variable que contiene la suma de los múltiplos.