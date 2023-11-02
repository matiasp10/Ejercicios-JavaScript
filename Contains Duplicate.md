#Easy 
___
Dada una matriz de enteros nums, devuelve verdadero si algún valor aparece al menos dos veces en la matriz, y devuelve falso si cada elemento es distinto.
## Ejemplos
### 1

```
Input: nums = [1,2,3,1]
Output: true
```
### 2

```
Input: nums = [1,2,3,4]
Output: false
```
### 3

```
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true
```
## Restricciones

- `1 <= nums.length <= 105`
- `-109 <= nums[i] <= 109`
## Link del problema

https://leetcode.com/problems/contains-duplicate/description/
## Mi solución

```js
/**
 * @param {number[]} nums
 * @return {boolean}
 */
var containsDuplicate = function(nums) {
    for(num of nums){
        if(nums.filter(n=> n === num).length > 1) return true
    }
    return false
};
```
