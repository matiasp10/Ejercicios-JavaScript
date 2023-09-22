# Romanos a enteros

Los números romanos se representan con siete símbolos diferentes: I, V, X, L, C, D y M.

```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```

Por ejemplo, 2 se escribe como II en número romano, simplemente dos unos sumados. El 12 se escribe como XII, que es simplemente X + II. El número 27 se escribe XXVII, que es XX + V + II.

Los números romanos suelen escribirse de mayor a menor, de izquierda a derecha. Sin embargo, el número cuatro no es `IIII`. En su lugar, el número cuatro se escribe IV. Como el uno está antes del cinco, lo restamos haciendo cuatro. El mismo principio se aplica al número nueve, que se escribe IX. Hay seis casos en los que se utiliza la resta:

- **I** puede colocarse antes de **V** (5) y **X** (10) para formar 4 y 9.
- **X** puede anteponerse a **L** (50) y **C** (100) para formar 40 y 90.
- **C** puede colocarse antes de **D** (500) y **M** (1000) para formar 400 y 900.

Dado un número romano, conviértelo en un número entero.

## Ejemplos

### Ejemplo 1

```bash
Input: s = "III"
Output: 3
Explanation: III = 3.
```

### Ejemplo 2

```bash
Input: s = "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.
```

### Ejemplo 3

```bash
Input: s = "MCMXCIV"
Output: 1994
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
```

## Limitaciones

-   1 ≤ `s.length` ≤ 15
-   **s** solo contiene los caracteres (‘I’, ‘V’, ‘X’, ‘L’, ‘C’, ‘D’, ‘M’).
-   Se **garantiza** que **s** es un número romano válido en el intervalo `[1, 3999]`.

## Link al problema

[https://leetcode.com/problems/roman-to-integer/description/](https://leetcode.com/problems/roman-to-integer/description/)

## Mi solución

```js
/**
 * @param {string} s
 * @return {number}
 */
function romanToInt(s) {
  let romanNumbers = new Map();
  let integer = 0;

  romanNumbers.set('I', 1);
  romanNumbers.set('V', 5);
  romanNumbers.set('X', 10);
  romanNumbers.set('L', 50);
  romanNumbers.set('C', 100);
  romanNumbers.set('D', 500);
  romanNumbers.set('M', 1000);

  s = s.replace('IV', 'IIII').replace('IX', 'VIIII');
  s = s.replace('XL', 'XXXX').replace('XC', 'LXXXX');
  s = s.replace('CD', 'CCCC').replace('CM', 'DCCCC');

  for (let char of s) {
    integer += romanNumbers.get(char);
  }

  return integer;
};
```

Declaro una variable donde voy a almacenar un `Map` de pares claves:valor, donde la clave es el número romano y el valor el número entero correspondiente al número romano, y otra variable donde colocaré el número romano ingresado en entero.

Mediante el método `.set(clave, valor)` ingreso cada número romano con su valor entero en el `Map`.

Teniendo en cuenta los casos de resta, reemplazo los casos de: **"IV", "IX", "XL", "XC", "CD" y "CM",** por **"IIII", "VIIII", "XXXX", "LXXXX", "CCCC" y "DCCCC"** respectivamente.

Mediante un bucle `for...of` recorro el `string` del número romano y voy obteniendo el valor de cada carácter del número romano y lo voy sumando a la variable `integer`.

Al final devuelvo la variable `integer` donde tengo el número romano convertido a **entero**.

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]