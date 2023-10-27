#Easy 
____
Dado un entero no negativo x, devuelve la raíz cuadrada de x redondeada al entero más cercano. El entero devuelto también debe ser no negativo.  
  
No debe utilizar ninguna función u operador de exponente incorporado.  

- Por ejemplo, no utilice `pow(x, 0.5)` en **c++** o `x ** 0.5` en **python**.
## Ejemplo
### 1

```
Input: x = 4
Output: 2
Explanation: The square root of 4 is 2, so we return 2.
```
### 2

```
Input: x = 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since we round it down to the nearest integer, 2 is returned.
```
## Restricciones

- `0 <= x <= 231 - 1`
## Link del problema

https://leetcode.com/problems/sqrtx/description/
## Mi solución

```js
/**
 * @param {number} x
 * @return {number}
 */
var mySqrt = function(x) {
    return Math.floor(Math.sqrt(x))
};
```
