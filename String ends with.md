#7kyu 
___
# ¿La cadena termina en?

Completa la solución para que devuelva verdadero si el primer argumento (cadena) pasado termina con el 2º argumento (también una cadena).

## Ejemplos

```javascript
solution('abc', 'bc') // returns true
solution('abc', 'd') // returns false
```

## Link del problema

https://www.codewars.com/kata/51f2d1cafc9c0f745c00037d

## Mi solución

```js
function solution(str, ending){
  return str.endsWith(ending) ? true : false 
}
```

- [[Programación Web/JavaScript/String/String|String]]
- [[String.prototype.endsWith()]]

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]