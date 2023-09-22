Le preguntas a una niña pequeña: "¿Cuántos años tienes?". Ella siempre responde: "x años", donde x es un número aleatorio entre 0 y 9.  
  
Escribe un programa que devuelva la edad de la niña (0-9) como un número entero.  
  
Suponga que la cadena de entrada de prueba es siempre una cadena válida. Por ejemplo, la entrada de prueba puede ser "1 año" o "5 años". El primer carácter de la cadena es siempre un número.

## Link del problema

https://www.codewars.com/kata/557cd6882bfa3c8a9f0000c1/train/javascript

## Mi solución

```js
function getAge(inputString){
  return Number(inputString.split(" ")[0])
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]