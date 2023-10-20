#8kyu 
___
En esta Kata estamos pasando un número (n) a una función.  
  
Tu código determinará si el número pasado es par (o no).  
  
La función debe devolver verdadero o falso.  
  
Los números pueden ser positivos o negativos, enteros o flotantes.  
  
Los flotantes con parte decimal distinta de cero se consideran desiguales para este kata.
## Link del problema

https://www.codewars.com/kata/555a67db74814aa4ee0001b5/train/javascript
## Mi solución

```js
function testEven(n) {
    if(n % 2 === 0){
      return true
    } else {
      return false
    }
}
```
