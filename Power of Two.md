#Easy 
___
Dado un número entero `n`, devuelve `true` si es una potencia de dos. En caso contrario, devuelve `false`.  
  
Un número entero `n` es una potencia de dos, si existe un número entero `x` tal que `n == 2x`.
## Ejemplos
### 1

```
Input: n = 1
Output: true
Explanation: 20 = 1
```
### 2

```
Input: n = 16
Output: true
Explanation: 24 = 16
```
### 3

```
Input: n = 3
Output: false
```
## Restricciones 

- `-231 <= n <= 231 - 1`
## Link del problema

https://leetcode.com/problems/power-of-two/
## Mi solución

```js
/**
 * @param {number} n
 * @return {boolean}
 */
var isPowerOfTwo = function(n) {
    return Number.isInteger(Math.sqrt(n))
};
```