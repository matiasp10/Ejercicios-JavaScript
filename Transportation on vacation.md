Después de un duro trimestre en la oficina decides descansar un poco en vacaciones. Así que reservarás un vuelo para ti y tu novia e intentarás dejar atrás todo el desorden.  
  
Necesitarás un coche de alquiler para desplazarte durante tus vacaciones. El encargado del alquiler de coches te hace unas buenas ofertas.  
  
Cada día que alquiles el coche cuesta 40$. Si alquilas el coche 7 días o más, te descuentan 50 $. Si alquilas el coche 3 días o más, te descuentan 20 $.  
  
Escribe un código que dé el importe total para los diferentes días(d).

## Link del problema

https://www.codewars.com/kata/568d0dd208ee69389d000016/train/javascript

## Mi solución

```js
function rentalCarCost(d) {
  if(d >= 7){
    return (d * 40) - 50
  } else if(d >= 3){
    return (d * 40) - 20
  } else {
    return d * 40
  }
}

// O

function rentalCarCost(d) {
  return d >= 7 ? (d * 40) - 50 : d >= 3 ? (d * 40) - 20 : (d * 40)
}
```
