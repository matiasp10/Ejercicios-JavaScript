#7kyu 
___

Dada una lista de dígitos, devuelve el menor número que podría formarse a partir de estos dígitos, utilizando los dígitos una sola vez (ignora los duplicados).

### Notas

- Sólo se pasarán enteros positivos a la función (> 0 ), no negativos ni ceros.

## Ejemplos

```js
minValue ({1, 3, 1})  ==> return (13)
```

- **(13)** es el número mínimo que podría formarse a partir de **{1, 3, 1}**, Sin duplicaciones

```js
minValue({5, 7, 5, 9, 7})  ==> return (579)
```

- **(579)** es el número mínimo que podría formarse a partir de **{5, 7, 5, 9, 7}**, Sin duplicaciones

```js
minValue({1, 9, 3, 1, 7, 4, 6, 6, 7}) return  ==> (134679)
```

- **(134679)** es el número mínimo que podría formarse a partir de **{1, 9, 3, 1, 7, 4, 6, 6, 7}**, Sin duplicaciones

## Link del problema

https://www.codewars.com/kata/5ac6932b2f317b96980000ca/train/javascript

## Mi solución

```js
function minValue(values){
  let set = Array.from(new Set(values))
  
  if(set.length === 1) return set[0]
  
  let sortedSet = set.sort((a,z)=> a-z)
  
  return Number(sortedSet.join(""))
}
```
