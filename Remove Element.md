#Easy 
_____
Dada una matriz de enteros `nums` y un entero `val`, eliminar todas las apariciones de `val` en `nums` en su lugar. Se puede cambiar el orden de los elementos. Devuelve el número de elementos de `nums` que no son iguales a `val`.  
  
Considere el número de elementos en `nums` que no son iguales a `val` ser `k`, para obtener aceptado, usted necesita hacer las siguientes cosas:  
  
- Cambiar la matriz `nums` de tal manera que los primeros `k` elementos de nums contengan los elementos que no son iguales a `val`. El resto de elementos de `nums` no son importantes así como el tamaño de `nums`.  
- Devuelve `k`.
## Juez a medida

El juez probará tu solución con el siguiente código:

```js
int[] nums = [...]; // Input array
int val = ...; // Value to remove
int[] expectedNums = [...]; // The expected answer with correct length.
                            // It is sorted with no values equaling val.

int k = removeElement(nums, val); // Calls your implementation

assert k == expectedNums.length;
sort(nums, 0, k); // Sort the first k elements of nums
for (int i = 0; i < actualLength; i++) {
    assert nums[i] == expectedNums[i];
}
```

Si todas las afirmaciones son correctas, su solución será aceptada.
## Ejemplos
### 1

```
Input: nums = [3,2,2,3], val = 3
Output: 2, nums = [2,2,_,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 2.
It does not matter what you leave beyond the returned k (hence they are underscores).
```
### 2

```
Input: nums = [0,1,2,2,3,0,4,2], val = 2
Output: 5, nums = [0,1,4,0,3,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums containing 0, 0, 1, 3, and 4.
Note that the five elements can be returned in any order.
It does not matter what you leave beyond the returned k (hence they are underscores).
```
## Restricciones 

- `0 <= nums.length <= 100`
- `0 <= nums[i] <= 50`
- `0 <= val <= 100`
## Link del problema

https://leetcode.com/problems/remove-element/description/
## Mi solución

```js
/**
 * @param {number[]} nums
 * @param {number} val
 * @return {number}
 */
var removeElement = function(nums, val) {
    let len = nums.filter(num => num === val).length
    for(let i = 0; i < len; i++){
        nums.splice(nums.indexOf(val), 1)
    }
    return nums.length
};
```
