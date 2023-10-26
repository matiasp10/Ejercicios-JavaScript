#Easy 
___
Dada una cadena `s` formada por palabras y espacios, devuelve la _longitud_ de la **última** palabra de la cadena.  
  
Una palabra es una _subcadena_ formada únicamente por caracteres sin espacios.
## Ejemplo
### 1

```
Input: s = "Hello World"
Output: 5
Explanation: The last word is "World" with length 5.
```
### 2

```
Input: s = "   fly me   to   the moon  "
Output: 4
Explanation: The last word is "moon" with length 4.
```
### 3

```
Input: s = "luffy is still joyboy"
Output: 6
Explanation: The last word is "joyboy" with length 6.
```
## Restricciones

- `1 <= s.length <= 104`
- `s` consists of only English letters and spaces `' '`.
- There will be at least one word in `s`.
## Link del problema

https://leetcode.com/problems/length-of-last-word/
## Mi solución

```js
/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLastWord = function(s) {
    let split = s.trim().split(" ")
    return split[split.length - 1].length
};
```
