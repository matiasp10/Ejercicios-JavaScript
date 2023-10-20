#7kyu 
___
Se le da una matriz de enteros de longitud impar, en la que todos son iguales, excepto un único número.  
  
Completa el método que acepta dicha matriz y devuelve ese único número diferente.  

¡La matriz de entrada siempre será válida! (longitud impar >= 3)
## Ejemplos

```js
[1, 1, 2] ==> 2
[17, 17, 3, 17, 17, 17, 17] ==> 3
```
## Link del problema

https://www.codewars.com/kata/57f609022f4d534f05000024/train/javascript
## Mi solución

```js
function stray(numbers) {
  let ref = numbers[0]
  let arr1 = []
  let arr2 = []
  for(num of numbers){
    if(num === ref){
      arr1.push(num)
    } else if (num !== ref){
      arr2.push(num)
    }
  }
  return arr1.length < arr2.length ? arr1[0] : arr2[0]
}
```
