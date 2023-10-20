#7kyu 
___
Contar el número de divisores de un número entero positivo n.  
  
Las pruebas aleatorias llegan hasta n = 500000.

## Ejemplos (entrada --> salida)

```
4 --> 3 // we have 3 divisors - 1, 2 and 4
5 --> 2 // we have 2 divisors - 1 and 5
12 --> 6 // we have 6 divisors - 1, 2, 3, 4, 6 and 12
30 --> 8 // we have 8 divisors - 1, 2, 3, 5, 6, 10, 15 and 30
```

Tenga en cuenta que sólo debe devolver un número, el recuento de divisores. Los números entre paréntesis se muestran sólo para que veas qué números se cuentan en cada caso.

## Link del problema

https://www.codewars.com/kata/542c0f198e077084c0000c2e/train/javascript

## Mi solución 

```js
function getDivisorsCnt(n){
  let count = 0
  
  if(n % Math.sqrt(n) === 0) count++
  
  for(let i = 0; i < Math.sqrt(n); i++){
    if (n % i === 0){
      count += 2
    }
  }
  
  return count
}
```
