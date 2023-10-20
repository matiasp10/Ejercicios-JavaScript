#Learning 
____
# Tarifas freelance

En este ejercicio escribirás código para ayudar a un autónomo a comunicarse con sus clientes sobre los precios de ciertos proyectos. Escribirás algunas funciones de utilidad para calcular rápidamente los costes para los clientes.

## Link al problema

[https://exercism.org/tracks/javascript/exercises/freelancer-rates](https://exercism.org/tracks/javascript/exercises/freelancer-rates)

## Paso 1: Calcular la tarifa diaria a partir de una tarifa horaria

Un cliente se pone en contacto con el autónomo para preguntarle por sus tarifas. El autónomo explica que trabaja **8 horas al día**. Sin embargo, el autónomo solo conoce su tarifa por hora para el proyecto. Ayúdele a calcular una tarifa por día a partir de una tarifa por hora.

```js
dayRate(89);
// => 712
```

No es necesario redondear la tarifa diaria ni cambiarla a una precisión “fija”.

### Mi solución

```js
function dayRate(ratePerHour) {
  return ratePerHour * 8
}
```

Devuelvo la tarifa por hora multiplicada 8 que son las horas que trabaja por día.

## Paso 2: Calcular el número de días laborables a partir de un presupuesto fijo

Otro día, un jefe de proyecto ofrece al autónomo trabajar en un proyecto con un presupuesto fijo. Dado el presupuesto fijo y la tarifa horaria del autónomo, ayúdele a calcular el número de días que trabajaría hasta agotar el presupuesto. El resultado debe redondearse al número entero inferior más próximo.

```js
daysInBudget(20000, 89);
// => 28
```

### Mi solución

```js
function daysInBudget(budget, ratePerHour) {
  return Math.floor(budget / dayRate(ratePerHour))
}
```

Devuelvo el presupuesto dividido, la tarifa diaria (gracias a la función que cree en el primer paso), todo eso redondeado hacia abajo mediante el objeto `Math` y el método `.floor()`.

## Paso 3: Calcular la tasa de descuento para grandes proyectos

A menudo, los clientes del autónomo le contratan para proyectos que abarcan varios meses. En estos casos, el autónomo decide ofrecer un descuento por cada mes completo, y los días restantes se facturan a precio de día. Cada mes tiene **22 días facturables**. Ayúdele a estimar el coste de este tipo de proyectos, dada una tarifa por hora, el número de días que abarca el proyecto y una tasa de descuento mensual. El descuento se transmite siempre como un número, donde `42%` se convierte en `0,42`. El resultado debe redondearse al número entero más próximo hacia arriba.

```js
priceWithMonthlyDiscount(89, 230, 0.42);
// => 97972
```

### Mi solución

```js
function priceWithMonthlyDiscount(ratePerHour, numDays, discount) {
  let months = Math.floor(numDays / 22);
  let perMonth = dayRate(ratePerHour) * 22;
  let monthsWithDiscount = perMonth * months - perMonth * months * discount;
  let restDays = dayRate(ratePerHour) * (numDays % 22);

  if (discount === 0) {
    return Math.round(dayRate(ratePerHour) * numDays);
  } else {
    return Math.ceil(monthsWithDiscount + restDays);
  }
}
```

Calculo los meses, cuanto sale por mes, cuanto cuesta todos los meses con descuento y cuanto sale el resto de días que quedan sin descuento.

Una vez teniendo esos datos, con un condicional verifico si hay descuento, si no lo hay directamente devuelvo lo que sale por día por la cantidad de días que voy a trabajar, si hay descuento entonces devuelvo el entero hacia arriba más cercano de los meses con el descuento más los días que quedan de resto sin el descuento.

# Temas relacionados

[[Number]]
[[Operadores]]

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]