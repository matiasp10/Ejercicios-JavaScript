Dado un conjunto de números, devuelve la inversa aditiva de cada uno. Cada positivo se convierte en negativo, y los negativos en positivos.

## Ejemplo

```js
invert([1,2,3,4,5]) == [-1,-2,-3,-4,-5]
invert([1,-2,3,-4,5]) == [-1,2,-3,4,-5]
invert([]) == []
```

Puede asumir que todos los valores son enteros. No mute la matriz/lista de entrada.

## Link del problema

https://www.codewars.com/kata/5899dc03bc95b1bf1b0000ad/train/javascript

## Mi solución

```js
function invert(array) {
   let invert = []
   for(num of array){
     invert.push(-num)
   }
  return invert
}
```

