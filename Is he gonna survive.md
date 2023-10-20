#8kyu 
____
# Sobrevivirá?

Un héroe se dirige al castillo para completar su misión. Sin embargo, le han dicho que el castillo está rodeado de un par de poderosos dragones! cada dragón necesita 2 balas para ser derrotado, nuestro héroe no tiene ni idea de cuántas balas debe llevar.. Suponiendo que va a coger un número determinado de balas y avanzar para luchar contra otro número determinado de dragones, ¿sobrevivirá?

Devuelve True si es así, False en caso contrario :)
## Mi solución

```js
function hero(bullets, dragons){
// En un condicional verifico si la cantidad de balas / 2 es menor que la cant. de dragones entonces el héroe morirá, de lo contrario sobrevivirá.
  if (Math.floor(bullets / 2) < dragons) {
    return false
  } else {
    return true
  }
}
```

[**Link del problema**](https://www.codewars.com/kata/59ca8246d751df55cc00014c/train/javascript)

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]