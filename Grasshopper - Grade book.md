Completa la función para que encuentre la media de las tres puntuaciones que se le han pasado y devuelva el valor de la letra asociado a esa calificación.

|Numerical Score|Letter Grade|
|---|---|
|90 <= score <= 100|'A'|
|80 <= score < 90|'B'|
|70 <= score < 80|'C'|
|60 <= score < 70|'D'|
|0 <= score < 60|'F'|

Los valores comprobados están todos entre 0 y 100. No es necesario comprobar valores negativos o superiores a 100.

## Link del problema

https://www.codewars.com/kata/55cbd4ba903825f7970000f5/train/javascript

## Mi solución

```js
function getGrade (s1, s2, s3) {
  let average = (s1 + s2 + s3) / 3
  if(average < 60) return "F"
  if(average < 70) return "D"
  if(average < 80) return "C"
  if(average < 90) return "B"
  if(average <= 100) return "A"
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]