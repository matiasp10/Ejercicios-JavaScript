#6kyu 
____
Hay una matriz con algunos números. Todos los números son iguales excepto uno. Intenta encontrarlo.

```javascript
findUniq([ 1, 1, 1, 2, 1, 1 ]) === 2
findUniq([ 0, 0, 0.55, 0, 0 ]) === 0.55
```

Se garantiza que el array contiene al menos 3 números.  
  
Las pruebas contienen algunas matrices muy grandes, así que piensa en el rendimiento.
## Link del problema

https://www.codewars.com/kata/585d7d5adb20cf33cb000235/train/javascript
## Mi solución

```js
function findUniq(arr) {
  let sorted = arr.sort()
  if (sorted[0] === sorted[1]) return sorted[arr.length - 1]
  else return sorted[0]
}
```