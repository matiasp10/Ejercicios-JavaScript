# Dos sumas

Dado un `array` **de enteros** `nums` y **un entero** `target`, devuelva los índices de los dos números tales que **sumen target**.

Puede suponer que cada entrada tendría exactamente una solución, y **no puede utilizar el mismo elemento dos veces**.

Puede devolver la respuesta en cualquier orden.

## Ejemplos

### Ejemplo 1

```bash
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

### Ejemplo 2

```bash
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

### Ejemplo 3

```bash
Input: nums = [3,3], target = 6
Output: [0,1]
```

## Limitaciones

-   `2 <= nums.length <= 10^4`
-   `-10^9 <= nums[i] <= 10^9`
-   `-10^9 <= target <= 10^9`
-   Solo existe una respuesta válida.

## Link al problema

[https://leetcode.com/problems/two-sum/description/](https://leetcode.com/problems/two-sum/description/)

## Mi solución

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */

let twoSum = function (nums, target) {
  for (let i = 0; i < nums.length; i++) {
    for (let j = 0; j < nums.length; j++) {
      if (i === j) {
      } else if (nums[i] + nums[j] === target) {
        return [i, j];
      }
    }
  }
};
```

Recorro el `array` `nums` con un bucle `for`, para obtener el primer número que quiero sumar, y anido otro bucle `for` para obtener el segundo número que voy a sumar.

Dentro de ambos bucles, con un condicional, `if` verifico que la posición del número exterior y la posición del número interior no sean la misma, ya que no puedo usar el mismo elemento dos veces, si no, verifico que la suma de ambos números coincida con el target y devuelvo un `array` con sus posiciones.