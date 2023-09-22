# La cola del supermercado

En el supermercado hay una cola de espera para las cajas automáticas. Tu tarea es escribir una función que calcule el tiempo total que necesitan todos los clientes para pasar por caja.

## Entrada

- _Clientes_: un array de enteros positivos que representan la cola. Cada entero representa a un cliente, y su valor es la cantidad de tiempo que necesitan para pasar por caja. 
- _n_: un entero positivo, el número de cajas.

## Salida

La función debe devolver un entero, el tiempo total requerido.

## Ejemplos

```js
queueTime([5,3,4], 1)
// debe devolver 12
// porque cuando hay 1 caja, el tiempo total es sólo la suma de los tiempos

queueTime([10,2,3,3], 2)
// debe devolver 10
// porque aquí n=2 y las personas 2ª, 3ª y 4ª de la 
// cola termina antes de que la 1ª persona haya terminado.

queueTime([2,3,10], 2)
// debe devolver 12
```

## Aclaración

- Sólo hay UNA cola que sirve a muchas cajas, y
- El orden de la cola NUNCA cambia, y
- El primero de la cola (es decir, el primer elemento de la matriz/lista) pasa a una caja tan pronto como queda libre.

## Mi solución

```js
function queueTime(customers, n) {
  // Creo un array nuevo de longitud n (cajas) y lo lleno de 0s
  let arr = new Array(n).fill(0);  
  // En un bucle recorro el array de clientes ingresandolos por orden de llegada a las cajas
  for (let i = 0; i < customers.length; i++) {
    // Por cada ciclo inicializo la variable index que contiene el indice del valor mas bajo
    let index = arr.indexOf(Math.min(...arr));
    // en el arreglo que cree al inicio con el indice que tome en el ciclo le agrego en esa posicion al cliente i.
    arr[index] += customers[i];
  }
  // devuelvo el valor maximo del array, osea el tiempo de espera maximo de la cola.
  return Math.max(...arr);
}
```

[**Link del problema**](https://www.codewars.com/kata/57b06f90e298a7b53d000a86/train/javascript)

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]