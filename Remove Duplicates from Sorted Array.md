#Easy 
____
Dada una matriz de números enteros ordenada en orden no decreciente, elimine los duplicados en su lugar de forma que cada elemento único aparezca una sola vez. El orden relativo de los elementos debe ser el mismo. A continuación, devuelve el número de elementos únicos en `nums`.  
  
Considere que el número de elementos únicos de `nums` es k, para ser aceptado, necesita hacer lo siguiente:  
  
- Cambiar el array `nums` de forma que los primeros k elementos de `nums` contengan los elementos únicos en el orden en que estaban presentes en nums inicialmente. Los elementos restantes de `nums` no son importantes, así como el tamaño de nums.  
- Devuelve k.

## Juez a medida:  

El juez probará tu solución con el siguiente código:

```js
int[] nums = [...]; // Input array
int[] expectedNums = [...]; // The expected answer with correct length

int k = removeDuplicates(nums); // Calls your implementation

assert k == expectedNums.length;
for (int i = 0; i < k; i++) {
    assert nums[i] == expectedNums[i];
}
```

Si todas las afirmaciones son correctas, su solución será aceptada.
## Ejemplos
### 1

```
Input: nums = [1,1,2]
Output: 2, nums = [1,2,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```
### 2

```
Input: nums = [0,0,1,1,1,2,2,3,3,4]
Output: 5, nums = [0,1,2,3,4,_,_,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums being 0, 1, 2, 3, and 4 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```
## Restricciones 

- `1 <= nums.length <= 3 * 104`
- `-100 <= nums[i] <= 100`
- `nums` is sorted in **non-decreasing** order.
## Link del problema

https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/
## Mi solución

```js
/**
 * @param {number[]} nums
 * @return {number}
 */
let removeDuplicates = function(nums) {
  let set = new Set(nums)
  nums.unshift(...set)
  return Array.from(set).length
};
```
