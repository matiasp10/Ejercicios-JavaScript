Implementar una función que acepte 3 valores enteros a, b, c. La función debe devolver verdadero si se puede construir un triángulo con los lados de longitud dada y falso en cualquier otro caso.  
  
(En este caso, todos los triángulos deben tener superficie mayor que 0 para ser aceptados).

## Link del problema

https://www.codewars.com/kata/56606694ec01347ce800001b/train/javascript

## Mi solución

```js
function isTriangle(a,b,c){
    let lados = [a, b, c]
    lados.sort((a,z)=>z-a)
    if(lados[0] < lados[1] + lados[2]){
      return true
    } else {
      return false
    }
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]