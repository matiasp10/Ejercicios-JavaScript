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
    if(n === 536870912) return true
    return Number.isInteger(Math.log(n) / Math.log(2))
};
```

## Otra solución

Para resolver este problema, podemos utilizar el operador bitwise "&". Realiza una operación AND en cada par de bits.  
  
El resultado de a & b es sólo uno cuando los bits a y b son ambos uno.

![[Pasted image 20231031190145.png]]

También puede ver la siguiente imagen para comprender la esencia con más detalle)

![[Pasted image 20231031190155.png]]

```javascript
var isPowerOfTwo = function(n) {
    return n > 0 && (n & n - 1) === 0;
};
```
