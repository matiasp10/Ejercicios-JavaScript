Crea una función con dos argumentos que devuelva una matriz con los n primeros múltiplos de x.  

Asume que tanto el número dado como el número de veces a contar serán números positivos mayores que 0.  
  
Devuelve los resultados como una matriz o lista ( dependiendo del lenguaje ).

## Ejemplos

```javascript
countBy(1,10) === [1,2,3,4,5,6,7,8,9,10]
countBy(2,5) === [2,4,6,8,10]
```

## Link del problema

https://www.codewars.com/kata/5513795bd3fafb56c200049e/train/javascript
## Mi solución

```js
function countBy(x, n) {
  let z = [];
  
    for (let i = 1; i <= n; i++) {
    z.push(x * i);
  }

  return z;
}
```

