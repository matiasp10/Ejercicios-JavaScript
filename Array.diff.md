Tu objetivo en esta kata es implementar una función diferencia, que resta una lista de otra y devuelve el resultado.  
  
Debe eliminar todos los valores de la lista `a`, que están presentes en la lista `b` manteniendo su orden.

```javascript
arrayDiff([1,2],[1]) == [2]
```

Si un valor está presente en `b`, todas sus apariciones deben eliminarse del otro:

```javascript
arrayDiff([1,2,2,2,3],[2]) == [1,3]
```

## Link del problema

https://www.codewars.com/kata/523f5d21c841566fde000009/train/javascript

## Mi solución

```js
function arrayDiff(a, b) {
  let stack = [];
  for (let i = 0; i < a.length; i++) {
    if (!b.includes(a[i])) {
      stack.push(a[i]);
    }
  }
  return stack;
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]