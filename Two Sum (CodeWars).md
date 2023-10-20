#6kyu 
___
Escriba una función que tome una matriz de números (enteros para las pruebas) y un número objetivo. Debe encontrar dos elementos diferentes en la matriz que, cuando se suman, dan el valor objetivo. Los índices de estos elementos deben ser devueltos en una tupla / lista (dependiendo de su idioma) así: (índice1, índice2).  
  
Para los propósitos de esta kata, algunas pruebas pueden tener múltiples respuestas; cualquier solución válida será aceptada.  
  
La entrada siempre será válida (los números serán una matriz de longitud 2 o superior, y todos los elementos serán números; el objetivo siempre será la suma de dos elementos diferentes de esa matriz).

```javascript
twoSum([1, 2, 3], 4) // returns [0, 2] or [2, 0]
```

## Link del problema

https://www.codewars.com/kata/52c31f8e6605bcc646000082/train/javascript

## Mi solución

```js
function twoSum(numbers, target) {
    for(let i = 0; i < numbers.length; i++){
      for(let j = 0; j < numbers.length; j++){
        if(numbers[i] + numbers[j] === target && i !== j){
          return [i, j]
        }
      }
    }
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]