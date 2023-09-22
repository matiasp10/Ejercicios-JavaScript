# Número palíndromo

Dado un número entero x, devuelve true si x es un palíndromo y falso en caso contrario.

> [!hint] 
> Un número natural es un [**palíndromo**](http://es.wikipedia.org/wiki/Pal%C3%ADndromo) si se lee igual de izquierda a derecha y de derecha a izquierda.
> 
> Por ejemplo, 14941 es un palíndromo, mientras que 81924 no lo es.

## Ejemplos

### Ejemplo 1:

```bash
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

### Ejemplo 2:

```bash
Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```

### Ejemplo 3:

```bash
Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
```

## Limitaciones

-   `-2^31 <= x <= 2^31 - 1`

## Link del problema

[https://leetcode.com/problems/palindrome-number/description/](https://leetcode.com/problems/palindrome-number/description/)

## Mi solución

```js
/**
 * @param {number} x
 * @return {boolean}
 */
let isPalindrome = function(x) {
    let reversedNumber = Number(x.toString().split("").reverse().join(""))
    return x === reversedNumber ? true : false
};
```

En una variable voy a almacenar una copia del número pero dada vuelta.  
Para dar vuelta el número lo que hago es igual a:

```js
// Por ejemplo el numero ingresado es 123
let n = x.toString() // "123"
n = n.split("") // ["1","2","3"]
n = n.reverse() // ["3","2","1"]
n = n.join("") // "321"
n = Number(n) // 321
```

Puedo concatenar métodos gracias a que los tipos de datos primitivos son objetos en JS, para entender más esto, pueden ayudar las siguientes lecturas:

[https://es.javascript.info/primitives-methods](https://es.javascript.info/primitives-methods)

[https://es.javascript.info/prototype-inheritance](https://es.javascript.info/prototype-inheritance)

Al final de la función mediante el operador ternario `?` devuelvo `true` si el número ingresado es igual al número dada vuelta, si no `false`.

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]