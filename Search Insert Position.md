#Easy 
___
Dada una matriz ordenada de enteros distintos y un valor objetivo, devuelve el índice si se encuentra el objetivo. Si no, devuelve el índice donde estaría si se insertara ordenado.  
  
Debe escribir un algoritmo con complejidad de ejecución O(log n).
## Ejemplos
### 1

```js
Input nums = [1,3,5,6], target = 5
Output: 2
```
### 2

```js
Input: nums = [1,3,5,6], target = 2
Output: 1
```
### 3

```js
Input: nums = [1,3,5,6], target = 7
Output: 4
```
## Restricciones

- `1 <= nums.length <= 104`
- `-104 <= nums[i] <= 104`
- `nums` contiene valores distintos ordenados de forma ascendente.
- `-104 <= target <= 104`
## Link del problema

https://leetcode.com/problems/search-insert-position/
## Mi solución

```js
var searchInsert = function(nums, target) {
  if(nums.indexOf(target) !== -1) return nums.indexOf(target)
  if(target === 0 && nums[0] >= 0 || nums.length === 1 && nums[0] > target) return 0
  if(nums.length === 1 && nums[0] < target) return 1
  let max = Math.min(...nums.filter(num => num > target))
  let min = Math.max(...nums.filter(num => num < target))
  console.log(nums.indexOf(max),nums.indexOf(min))
  let result = Math.abs(nums.indexOf(max)-nums.indexOf(min))
  if(result === 1) return nums.indexOf(max)
  return result
};
```
