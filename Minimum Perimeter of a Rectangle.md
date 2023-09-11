Un rectángulo puede definirse mediante dos factores: altura y anchura.  

Su área se define como la multiplicación de ambos: alto * ancho.  
  
Su perímetro es la suma de sus cuatro aristas: altura + altura + anchura + anchura.

Es posible crear rectángulos de la misma área pero de perímetros diferentes. Por ejemplo, dada un área de 45, las posibles alturas, anchuras y perímetros resultantes serían:

(1, 45) = 92

(9, 5) = 28

(15, 3) = 36

Obsérvese que (6, 7,5) también tiene un área de 45, pero se descarta en esta kata porque su anchura no es integral.  
  
La tarea consiste en escribir una función que, dada un área como entero positivo, devuelva el menor perímetro posible de un rectángulo con longitudes laterales integrales.

## Link al problema

[Link](https://www.codewars.com/kata/5826f54cc60c7e5266000baf/train/javascript)

## Mi solución

```js
function minimumPerimeter(area) {
  for (let i = Math.floor(Math.sqrt(area)); i > 0; i--) {
    if (area % i === 0) {
      return (i + area / i) * 2;
    }
  }
}
```
