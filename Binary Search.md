# Búsqueda binaria

Dada una matriz de números enteros `nums` ordenados de forma ascendente y un `target` entero, escriba una función que busque el objetivo en números enteros. Si el objetivo existe, devuelve su índice. En caso contrario, devuelve -1.

Debe escribir un algoritmo con complejidad de tiempo de ejecución **O(log n)**.

## Ejemplos

### Ejemplo 1

```bash
Input: nums = [-1,0,3,5,9,12], target = 9
Output: 4
Explanation: 9 exists in nums and its index is 4
```

### Ejemplo 2

```bash
Input: nums = [-1,0,3,5,9,12], target = 2
Output: -1
Explanation: 2 does not exist in nums so return -1
```

## Limitaciones

-   `1 <= nums.length <= 10<sup>4</sup>`
-   `-10<sup>4</sup> < nums[i], target < 10<sup>4</sup>`
-   Todos los enteros en `nums` son únicos.
-   `nums` está ordenado en orden ascendente.

## Link al problema

[https://leetcode.com/problems/binary-search/description/](https://leetcode.com/problems/binary-search/description/)

## Mi solución

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var search = function(nums, target) {
  return nums.includes(target) ? nums.indexOf(target) : -1
};
```

Simplemente, devuelvo con el operador ternario, si la condición de que el arreglo `nums` incluye el número `target`, entonces devuelvo el índice que contiene a target, si no devuelvo -1.

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]