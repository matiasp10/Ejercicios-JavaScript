En una pequeña ciudad la población es `p0 = 1000` al principio de un año. La población aumenta regularmente un `2 por ciento` al año y, además, 50 nuevos habitantes al año vienen a vivir a la ciudad. ¿Cuántos años necesita la ciudad para que su población sea mayor o igual a `p = 1200` habitantes?

```
At the end of the first year there will be: 
1000 + 1000 * 0.02 + 50 => 1070 inhabitants

At the end of the 2nd year there will be: 
1070 + 1070 * 0.02 + 50 => 1141 inhabitants (** number of inhabitants is an integer **)

At the end of the 3rd year there will be:
1141 + 1141 * 0.02 + 50 => 1213

It will need 3 entire years.
```

### Parámetros más generales:  
  
p0, percent, aug (habitantes que entran o salen cada año), p (población a igualar o superar). 

la función `nb_year` debe devolver `n` número de años enteros necesarios para obtener una población mayor o igual a `p`.  
  
**aug** es un _entero_, **percent** un _número flotante positivo o nulo_, **p0** y **p** son _enteros positivos_ (> 0).

## Ejemplos

```js
nb_year(1500, 5, 100, 5000) -> 15
nb_year(1500000, 2.5, 10000, 2000000) -> 10
```

## Nota

No olvides convertir el parámetro porcentaje en porcentaje en el cuerpo de tu función: si el parámetro porcentaje es 2 tienes que convertirlo a 0,02.

## Link del problema

https://www.codewars.com/kata/563b662a59afc2b5120000c6/train/javascript

## Mi solucion

```js
function nbYear(p0, percent, aug, p) {
    
  for (var years = 0; p0 < p; years++) {
    p0 = Math.floor(p0 + p0 * percent / 100 + aug);
  }
  return years
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]