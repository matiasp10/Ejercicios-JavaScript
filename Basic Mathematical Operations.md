#8kyu 
___
Tu tarea consiste en crear una función que realice cuatro operaciones matemáticas básicas.  
  
La función debe tomar tres argumentos - operación(cadena/carácter), valor1(número), valor2(número).  
La función debe devolver el resultado de los números después de aplicar la operación elegida.
## Ejemplos

```js
('+', 4, 7) --> 11
('-', 15, 18) --> -3
('*', 5, 5) --> 25
('/', 49, 7) --> 7
```
## Link del problema

https://www.codewars.com/kata/57356c55867b9b7a60000bd7/train/javascript
## Mi solución

```js
function basicOp(op, v1, v2){
  return op === "+" ? v1 + v2 : 
		    op === "-" ? v1 - v2 : 
		      op === "*" ? v1 * v2 : 
		        op === "/" ? v1 / v2 : null
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]