#6kyu 
___
Dada una matriz de números enteros, encuentra el que aparece un número impar de veces.  

Siempre habrá un único número entero que aparezca un número impar de veces.
## Ejemplo

```
[7] debería devolver 7, porque aparece 1 vez (que es impar).
[0] debería devolver 0, porque ocurre 1 vez (lo cual es impar).
[1,1,2] debería devolver 2, porque ocurre 1 vez (lo cual es impar).
[0,1,0,1,0] debería devolver 0, porque ocurre 3 veces (lo cual es impar).
[1,2,2,3,3,3,4,3,3,3,2,2,1] debería devolver 4, porque aparece 1 vez (lo cual es impar).
```
## Link del problema

https://www.codewars.com/kata/54da5a58ea159efa38000836/train/javascript
## Mi solución

```js
function findOdd(A) {
  let nums = {}
  for(let num of A){
    nums[num] =  nums[num] + 1 || 0
  }
  nums = Object.entries(nums)
  for(let num of nums){
    if(num[1] % 2 === 0){
      return +num[0]
    }
  }
}
```