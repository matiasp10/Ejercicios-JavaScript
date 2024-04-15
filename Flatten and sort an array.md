#7kyu 
___
Dada una matriz bidimensional de enteros, devuelva la versión aplanada de la matriz con todos los enteros en orden ordenado (ascendente).

## Ejemplo

```
Dado [[3, 2, 1], [4, 6, 5], [], [9, 7, 8]], su función debe devolver [1, 2, 3, 4, 5, 6, 7, 8, 9].
```

## Link del problema

## Mi solución 

```ts
function flattenAndSort(array) {
  array = array.flat(Infinity)
  return array.sort((a,z)=> a - z)
}
```

