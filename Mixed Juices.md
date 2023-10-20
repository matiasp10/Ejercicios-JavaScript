#Learning 
____
### While Loops

Con un bucle `while`, puede ejecutar código repetidamente mientras se cumpla una determinada condición. Se escribe con la palabra clave `while` seguida de una condición entre corchetes y un bloque de código que contiene el cuerpo del bucle entre llaves.

```js
while (condition) {
  // code that is executed repeatedly as long as the condition is true
}
```

JavaScript también tiene un bucle `do-while`. Aquí la condición se comprueba después de que se haya ejecutado el cuerpo del bucle. Esto es útil cuando la condición depende de evaluaciones realizadas en el cuerpo.

```js
do {
  // The code here will always be executed once and then
  // repeatedly while the condition is true.
} while (condition);
```

Dentro del cuerpo de un bucle, puedes utilizar la palabra clave `break` para detener la ejecución del bucle por completo. Por el contrario, la palabra clave `continue` sólo detiene la ejecución de la iteración actual y continúa con la siguiente. Con `continue` puedes evitar a menudo envolver grandes partes del cuerpo del bucle en una sentencia `if`.

```js
let i = 0;

while (i < 100) {
  i = i + 2;

  if (i % 3 === 0) {
    continue;
  }

  // The code here will only be executed when i was not divisible
  // by 3 in the check above.
}
```
### Switch Statements

Además de la sentencia `if`, JavaScript también dispone de una sentencia `switch` para ejecutar la lógica de forma condicional. Se utiliza cuando es necesario comparar una única variable con múltiples variantes. La comparación se realiza comprobando la igualdad estricta ` === `. Para una variable x, la sentencia `switch` en JavaScript tiene la siguiente sintaxis.

```js
switch (x) {
  case option1:
    // code that is executed when "x === option1" is true
    break;
  case option2:
    // code that is executed when "x === option2" is true
    break;
  default:
    // code that is executed when x does not equal any of the options
}
```

El caso `default` es opcional y se utiliza en caso de que desee ejecutar algún código si ninguna de las otras opciones coincide con la variable.  
  
Las sentencias `break` son necesarias porque por defecto todos los casos son **"fallthrough"** en JavaScript. Esto significa que sin ninguna sentencia `break` todo el código en los casos por debajo de la primera opción coincidente se ejecutaría aunque `x` no coincidiera con esas opciones. Este comportamiento **"fallthrough por defecto"** es una trampa común cuando se utiliza `switch` en JavaScript. Dentro de una función, también se puede utilizar `return` en lugar de `break` para evitar este problema.
___
Tu amiga Li Mei regenta un bar de zumos donde vende deliciosos zumos de frutas variadas. Eres un cliente habitual de su tienda y te has dado cuenta de que podrías hacerle la vida más fácil a tu amiga. Decides utilizar tus conocimientos de programación para ayudar a Li Mei en su trabajo.
## 1. Determina cuánto tiempo se tarda en mezclar un zumo

A Li Mei le gusta decir a sus clientes por adelantado cuánto tiempo tienen que esperar para tomar un zumo del menú que hayan pedido. Le cuesta recordar las cifras exactas porque el tiempo que se tarda en mezclar los zumos varía. El `"Pure Strawberry Joy"` tarda 0,5 minutos, el `"Energizer"` y el `"Green Garden"` tardan 1,5 minutos cada uno, el `"Tropical Island"` tarda 3 minutos y el `"All or Nothing"` tarda 5 minutos. Para todas las demás bebidas (por ejemplo, las ofertas especiales) puede suponer un tiempo de preparación de 2,5 minutos.  
  
Para ayudar a tu amigo, escribe una función `timeToMixJuice` que tome un zumo del menú como argumento y devuelva el número de minutos que se tarda en mezclar esa bebida.

```js
timeToMixJuice('Tropical Island');
// => 3

timeToMixJuice('Berries & Lime');
// => 2.5
```
### Mi solución

```js
export function timeToMixJuice(name) {
  switch(name){
    case "Pure Strawberry Joy": 
      return 0.5
      break;
    case "Energizer":
      return 1.5
      break
    case "Green Garden":
      return 1.5
      break
    case "Tropical Island":
      return 3
      break
    case "All or Nothing":
      return 5
      break
    default:
      return 2.5
  }
}
```
## 2. Reponer el suministro de gajos de lima

Muchas de las creaciones de Li Mei incluyen gajos de lima, ya sea como ingrediente o como parte de la decoración. Por eso, cuando empieza su turno por la mañana, tiene que asegurarse de que el contenedor de gajos de lima esté lleno para el día siguiente.  
  
Implementa la función `limesToCut` que toma el número de gajos de lima que Li Mei necesita cortar y un array que representa el suministro de limas enteras que tiene a mano. Puede obtener 6 gajos de una lima `"small"`, 8 gajos de una lima `"medium"` y 10 de una lima `"large"`. Siempre corta las limas en el orden en que aparecen en la lista, empezando por la primera. Continúa hasta que alcanza el número de cuñas que necesita o hasta que se le acaban las limas.  
  
A Li Mei le gustaría saber de antemano cuántas limas necesita cortar. La función `limesToCut` debe devolver el número de limas a cortar.

```js
limesToCut(25, ['small', 'small', 'large', 'medium', 'small']);
// => 4
```
### Mi solución

```js
export function limesToCut(wedgesNeeded, limes) {
  let wedges = 0;
  let limesNeed = 0;

  for (let lime of limes) {
    if(wedges < wedgesNeeded){
      switch (lime) {
      case "small":
        wedges += 6;
        limesNeed++
        break
      case "medium":
        wedges += 8;
        limesNeed++
        break
      case "large":
        wedges += 10;
        limesNeed++
        break
      }
    }
  }
  return limesNeed
}
```
## 3. Terminar el turno

Li Mei siempre trabaja hasta las tres de la tarde. Después, su empleado Dmitry toma el relevo. A menudo hay bebidas que se han pedido pero aún no están preparadas cuando termina el turno de Li Mei. Dmitry se encarga entonces de preparar los zumos restantes.  
  
Para facilitar el traspaso, implemente una función `remainingOrders` que tome el número de minutos que quedan en el turno de Li Mei y un array de zumos que se han pedido pero que aún no se han preparado. La función debe devolver los pedidos que Li Mei no puede empezar a preparar antes del final de su jornada laboral.  
  
El tiempo restante del turno siempre será mayor que 0. La matriz de zumos por preparar nunca estará vacía. Además, los pedidos se preparan en el orden en que aparecen en la matriz. Si Li Mei empieza a mezclar un zumo determinado, siempre lo terminará aunque tenga que trabajar un poco más. Si no quedan pedidos de los que Dmitry tenga que ocuparse, se devolverá un array vacío.

```js
remainingOrders(5, ['Energizer', 'All or Nothing', 'Green Garden']);
// => ['Green Garden']
```
### Mi solución

```js
export function remainingOrders(timeLeft, orders) {
  let time = 0
  let drinks = 0
  for(let drink of orders){
    if (time < timeLeft){
      drinks++
    }
    time += timeToMixJuice(drink)

  }
  return orders.slice(drinks)
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/mixed-juices