#Easy 
____
# Prefijo común más largo

Escriba una función para encontrar la cadena de prefijo común más larga entre una matriz de cadenas.

Si no hay prefijo común, devuelve una cadena vacía `""`.

## Ejemplos

### Ejemplo 1

```bash
Input: strs = ["flower","flow","flight"]
Output: "fl"
```

### Ejemplo 2

```bash
Input: strs = ["dog","racecar","car"]
Output: ""
// Explicación: No hay prefijo común entre los strings de entrada.
```

## Limitaciones

-   `1 <= strs.length <= 200`
-   `0 <= strs[i].length <= 200`
-   `strs[i]` consta únicamente de letras minúsculas inglesas.

## Link al problema

[https://leetcode.com/problems/longest-common-prefix/](https://leetcode.com/problems/longest-common-prefix/)

## Mi solución

```js
/**
 * @param {string[]} strs
 * @return {string}
 */
var longestCommonPrefix = function(strs) {
    if (!strs.length) return '';
    for (let i = 0; i <= strs[0].length; i++) {
        for (let j = 1; j < strs.length; j++) {
            if (strs[0][i] !== strs[j][i]) {
                return strs[0].slice(0, i);
            }
        }
    }
    return strs[0];
};
```

Primero verifico si hay elementos en el arreglo `strs` y si no hay devuelvo un `string` vacío `""`.

Mediante un bucle itero sobre las letras de la primera palabra, y con un bucle anidado voy iterando sobre las demás palabras, por eso el bucle se inicializa `j = 1` (el segundo elemento), para comprobar el prefijo común más largo, voy comprobando con un `if` si la letra en la posición de la primera letra coincide con la letra en la misma posición, pero de las otras palabras, **si coinciden** el bucle sigue iterando, **si no coincide** quiere decir que las letras son distintas, entonces devuelvo mediante el método `.slice()` el `string` correspondiente al prefijo que es común entre todos los `strings` (si lo hay).

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1673824135545/18893023-776a-4efd-949e-0484aa128c13.png?auto=compress,format&format=webp)

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]