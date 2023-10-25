#Easy 
___
Dadas dos cadenas `needle` y `haystack`, devuelve el índice de la primera aparición de `needle` en `haystack`, o `-1` si `needle` no forma parte de `haystack`.
## Ejemplos
### 1

```
Input: haystack = "sadbutsad", needle = "sad"
Output: 0
Explanation: "sad" occurs at index 0 and 6.
The first occurrence is at index 0, so we return 0.
```
### 2

```
Input: haystack = "leetcode", needle = "leeto"
Output: -1
Explanation: "leeto" did not occur in "leetcode", so we return -1.
```
## Restricciones 

- `1 <= haystack.length, needle.length <= 104`
- `haystack` and `needle` consist of only lowercase English characters.
## Link del problema

https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/
## Mi solución 

```js
/**
 * @param {string} haystack
 * @param {string} needle
 * @return {number}
 */
var strStr = function(haystack, needle) {
    return haystack.indexOf(needle)
};
```
