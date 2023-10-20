#7kyu 
___
En la ciudad circula un autobús que lleva y deja a algunas personas en cada parada.  

Se le proporciona una lista (o matriz) de pares de números enteros. Los elementos de cada par representan el número de personas que suben al autobús (el primer elemento) y el número de personas que bajan del autobús (el segundo elemento) en una parada de autobús.  
  
Tu tarea es devolver el número de personas que siguen en el autobús después de la última parada (después de la última matriz). Aunque sea la última parada, es posible que el autobús no esté vacío y que todavía haya gente dentro, probablemente durmiendo :D  
  
Echa un vistazo a los casos de prueba.  
  
Por favor, ten en cuenta que los casos de prueba aseguran que el número de personas en el autobús es siempre >= 0. Así que el entero devuelto no puede ser negativo.  
  
El segundo valor del primer par de la matriz es 0, ya que el autobús está vacío en la primera parada.

## Link del problema

https://www.codewars.com/kata/5648b12ce68d9daa6b000099/train/javascript

## Mi solución

```js
function number(busStops){
  let onBus = 0
  let offBus = 0
  for (stops of busStops){
    console.log(stops)
    onBus += stops[0]
    offBus += stops[1]
  }
  return onBus - offBus
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]