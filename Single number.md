#Easy 
___
Dada una matriz no vacía de números enteros, cada elemento aparece dos veces excepto uno. Encuentra ese único elemento.  
  
Debe implementar una solución con una complejidad de tiempo de ejecución lineal y utilizar sólo un espacio extra constante.
## Ejemplos
### 1

```
Input: nums = [2,2,1]
Output: 1
```
### 2

```
Input: nums = [4,1,2,1,2]
Output: 4
```
### 3

```
Input: nums = [1]
Output: 1
```
## Restricciones

- `1 <= nums.length <= 3 * 104`
- `-3 * 104 <= nums[i] <= 3 * 104`
- Each element in the array appears twice except for one element which appears only once.
## Link del problema

https://leetcode.com/problems/single-number/description/
## Mi solución 

```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var singleNumber = function(nums) {
    if(nums.length === 1) return nums[0]
    let n = {}
    for(let num of nums){
      n[num] = n[num] + 1 || 0
    }
  let values = Object.entries(n)
  let single = values.find(n=> n[1] === 0)
  return +single[0]
};
```
