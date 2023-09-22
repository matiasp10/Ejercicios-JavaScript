Estabas de acampada con tus amigos lejos de casa, pero cuando llega la hora de volver, te das cuenta de que se te está acabando el combustible y de que el surtidor más cercano está a 80 kilómetros. Sabes que, de media, tu coche recorre unos 25 kilómetros por litro. Quedan 2 galones.  
  
Teniendo en cuenta estos factores, escribe una función que te diga si es posible llegar al surtidor o no.  
  
La función debe devolver verdadero si es posible y falso si no lo es.

## Link del problema

https://www.codewars.com/kata/5861d28f124b35723e00005e/train/javascript

## Mi solución 

```js
const zeroFuel = (distanceToPump, mpg, fuelLeft) => {
  if (distanceToPump <= (mpg * fuelLeft)){
    return true
  } else {
    return false
  }
};
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]