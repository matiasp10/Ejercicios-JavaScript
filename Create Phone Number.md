#6kyu 
____
# Crear número de teléfono

Escribe una función que acepte una matriz de 10 números enteros (entre 0 y 9), que devuelva una cadena de esos números en forma de número de teléfono.

## Ejemplo

```javascript
createPhoneNumber([1, 2, 3, 4, 5, 6, 7, 8, 9, 0]) 
// => returns "(123) 456-7890"
```

El formato devuelto debe ser correcto para completar este reto.  
  
No olvide el espacio después del paréntesis de cierre.
## Link del problema

https://www.codewars.com/kata/525f50e3b73515a6db000b83
## Mi solución

```js
function createPhoneNumber(numbers){
  const caracteristica = numbers.splice(0, 3).join("")
  const firstNumbers = numbers.splice(0,3).join("")
  const secondNumbers = numbers.splice(0,4).join("")
  return `(${caracteristica}) ${firstNumbers}-${secondNumbers}`
}
```

- [[Array]]
- [[Array.prototype.splice()]]

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]