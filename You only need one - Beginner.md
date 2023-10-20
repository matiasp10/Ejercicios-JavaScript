#8kyu 
___
Se le dará una matriz a y un valor x. Todo lo que tiene que hacer es comprobar si la matriz proporcionada contiene el valor.  
  
La matriz puede contener números o cadenas. X puede ser cualquiera de los dos.  
  
Devuelve true si el array contiene el valor, false en caso contrario.

## Link del problema

https://www.codewars.com/kata/57cc975ed542d3148f00015b/train/javascript

## Mi solución

```js
function check(a, x) {
  if(a.includes(x)){
    return true
  } else {
    return false
  }
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]