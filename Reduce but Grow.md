#8kyu 
___
Dada una matriz no vacía de enteros, devuelve el resultado de multiplicar los valores juntos en orden. 

## Ejemplo

```js
[1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24
```

## Link del problema

https://www.codewars.com/kata/57f780909f7e8e3183000078/train/javascript

## Mi solución 

```js
function grow(x){
  let m = 0
  for(let num of x){
    if (m === 0){
      m = num
    } else {
      m = num * m
    }
  }
  return m
}
```
