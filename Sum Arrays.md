#8kyu 
___
Escribe una función que tome una matriz de números y devuelva la suma de los números. Los números pueden ser negativos o no enteros. Si la matriz no contiene ningún número entonces debe devolver 0.

## Ejemplo

```js
Input: [1, 5.2, 4, 0, -1]
Output: 9.2

Input: []
Output: 0

Input: [-2.398]
Output: -2.398
```

## Link del problema

https://www.codewars.com/kata/53dc54212259ed3d4f00071c/train/javascript
## Mi solución

```js
function sum (numbers) {
  if(numbers.length === 0) return 0
  let aux = 0  
  for(let num of numbers){
      aux += num
    }
   return aux
};
```
