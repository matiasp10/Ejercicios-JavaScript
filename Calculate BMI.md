# Calculo del BMI

Escribe la función bmi que calcula el índice de masa corporal (bmi = peso / altura2).

- si el bmi <= 18.5 devuelve "Bajo peso"
- si el bmi <= 25.0 devuelve "Normal"
- si el bmi <= 30,0 devuelve "Sobrepeso".
- si el bmi > 30 devuelve "Obeso".

## Mi solución

```js
function bmi(weight, height) {
// Almaceno en una variable la división entre el peso y la altura elevada al cuadrado
  let bodyMass = weight / (Math.pow(height, 2));
// Con un condicional evaluó el resultado de la variable y devuelvo su correspondiente clasificación
  if (bodyMass <= 18.5) {
    return "Underweight"
  } else if (bodyMass <= 25) {
    return "Normal"
  } else if(bodyMass <=30){
    return "Overweight"
  } else {
    return "Obese"
  }
}
```

[**Link del problema**](https://www.codewars.com/kata/57a429e253ba3381850000fb/train/javascript)