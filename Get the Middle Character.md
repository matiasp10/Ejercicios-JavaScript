# **Encontrar el carácter del medio**

Te van a dar una palabra. Tu trabajo es devolver el carácter central de la palabra. Si la longitud de la palabra es impar, devuelve el carácter del medio. Si la longitud de la palabra es par, devuelve los 2 caracteres del medio.

## Ejemplo

```js
Kata.getMiddle("test") should return "es"

Kata.getMiddle("testing") should return "t"

Kata.getMiddle("middle") should return "dd"

Kata.getMiddle("A") should return "A"
```

## Input

Una palabra (cadena) de longitud 0 < str < 1000 (En JavaScript puede obtener un poco más de 1000 en algunos casos de prueba debido a un error en los casos de prueba). No es necesario probar esto. Esto es sólo para decirle que usted no necesita preocuparse por su solución de tiempo de espera.

## Output

El(los) carácter(es) central(es) de la palabra representado(s) como una cadena.

## Mi solución

```js
function getMiddle(s)
{
// Almaceno en una variable el índice del carácter del medio
 let middle = s.length / 2
// Si la palabra tiene una cantidad de caracteres pares devuelvo los dos 
// caracteres del medio, de lo contrario devuelvo el del medio.
  if (s.length % 2 == 0) {
    return (s.charAt(middle - 1) + (s.charAt(middle)))
  } else {
    return s.charAt(middle)
  }
}
```

[**Link del problema**](https://www.codewars.com/kata/56747fd5cb988479af000028/train/javascript)

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]