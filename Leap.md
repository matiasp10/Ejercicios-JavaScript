# Salto

Dado un año, informa si es bisiesto.

Lo complicado aquí es que se produzca un año bisiesto en el calendario gregoriano:

> [!note] 
> - En cada año que sea divisible por 4
>   - Excepto cada año que sea divisible en partes iguales por 100
>   - A menos que el año también sea divisible por 400.

Por ejemplo, 1997 no es bisiesto, pero 1996 sí. 1900 no es bisiesto, pero 2000 sí.

## Nota

Aunque nuestro ejercicio adopta algunas reglas muy sencillas, ¡hay mucho más que aprender!

En este vídeo de YouTube encontrarás una deliciosa explicación de cuatro minutos sobre el fenómeno del año bisiesto.

## Link al problema

[https://exercism.org/tracks/javascript/exercises/leap](https://exercism.org/tracks/javascript/exercises/leap)

## Mi solución

```js
export const isLeap = (year) => {
  if(year % 4 === 0){
    if(year % 100 === 0 && year % 400 === 0){
      return true
    } else if (year % 100 === 0){
      return false
    }
    return true
  }
  return false
};
```

Primero compruebo si el año es divisible por 4, si lo es, entonces vuelvo a comprobar si también es divisible por 100 y por 400, entonces es bisiesto, pero si solo es divisible por 100 y no por 400, no es bisiesto, si no es divisible por 100 ni por 400, pero si es divisible por 4 entonces si es bisiesto, si no es divisible por 4 entonces no es bisiesto.