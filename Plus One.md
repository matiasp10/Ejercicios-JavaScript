#Easy 
___
Se le da un número entero grande representado como una matriz entera `dígitos`, donde cada `dígitos[i]` es el _i-ésimo dígito_ del número entero. Los dígitos están ordenados de mayor a menor importancia de izquierda a derecha. El entero grande no contiene ningún `0` a la izquierda.  
  
Incrementa el entero grande en uno y devuelve la matriz de dígitos resultante.
## Ejemplos
### 1

```
Input: digits = [1,2,3]
Output: [1,2,4]
Explanation: The array represents the integer 123.
Incrementing by one gives 123 + 1 = 124.
Thus, the result should be [1,2,4].
```
### 2

```
Input: digits = [4,3,2,1]
Output: [4,3,2,2]
Explanation: The array represents the integer 4321.
Incrementing by one gives 4321 + 1 = 4322.
Thus, the result should be [4,3,2,2].
```
### 3

```
Input: digits = [9]
Output: [1,0]
Explanation: The array represents the integer 9.
Incrementing by one gives 9 + 1 = 10.
Thus, the result should be [1,0].
```
## Restricciones 

- `1 <= digits.length <= 100`
- `0 <= digits[i] <= 9`
- `digits` does not contain any leading `0`'s.
## Link del problema

https://leetcode.com/problems/plus-one/description/
## Mi solución

```js
/**
 * @param {number[]} digits
 * @return {number[]}
 */
var plusOne = function(digits) {
    let num = ""+(BigInt(digits.join(""))+1n)
    let splited = num.split("")
  return splited.map(num => +num)
};
```