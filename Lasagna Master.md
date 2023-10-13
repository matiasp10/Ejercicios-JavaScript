## Introducción 

Una función es un bloque de código organizado y reutilizable que se utiliza para realizar alguna acción. Existen múltiples formas de definir funciones en JavaScript. Aquí veremos las declaraciones de función y las expresiones de función. Otras posibilidades, como las funciones de flecha, se tratarán en otros conceptos.
### Declaración de funciones

La forma estándar de definir una función en JavaScript es *una declaración de función, también llamada definición de función o declaración de función*.  
  
Consta de la palabra clave `function`, el nombre de la función y una lista de parámetros separados por comas entre corchetes. A continuación aparece el cuerpo de la función (conjunto de sentencias que definen lo que hace una función) entre llaves.

```js
function someName(param1, param2, param3) {
  // ...
}
```

En JavaScript, una función se invoca (se llama) indicando el nombre de la función seguido de paréntesis que contienen los argumentos.

```js
someName(arg1, arg2, arg3);
```
### Parametros

Cuando trabaje con parámetros dentro del cuerpo de la función, tenga en cuenta los posibles efectos secundarios.  
  
- Los valores de los **tipos de datos primitivos** son _inmutables_. El valor original nunca se ve afectado por lo que ocurra con el argumento en el cuerpo de la función.  
- Para todos los demás valores (objetos, matrices, funciones), una reasignación no afectará al valor original. Sin embargo, si se modifica un argumento de este tipo (por ejemplo, añadir una clave a un objeto), eso también modifica el valor original que se pasó.  

Por defecto, todos los parámetros definidos en la declaración de función son opcionales en JavaScript. Si proporciona menos argumentos que parámetros hay, los argumentos que faltan serán indefinidos dentro de la función, véase Nulo e Indefinido. En muchos casos, tiene sentido asignar un valor por defecto más apropiado que undefined. Esto puede hacerse especificando parámetros por defecto directamente en la definición de la función.

```js
function someName(param1 = defaultValue1, param2 = defaultValue2) {
  // ...
}
```
### Return

Una sentencia `return` finaliza la ejecución de la función y especifica un valor que se devolverá al invocador de la función. Una función puede tener varias sentencias `return`.

```js
function checkNumber(num) {
  if (num === 0) {
    return 'You passed 0, please provide another number.';
  }

  return 'Thanks for passing such a nice number.';
}
```

El resultado de una función que no devuelve ningún valor o no tiene una sentencia `return` es `undefined`. En JavaScript no hay retornos implícitos.

```js
function nakedReturn(a) {
  a * 2;
  return;
}

nakedReturn(1);
// => undefined

function noReturn(a) {
  a * 2;
}

noReturn(1);
// => undefined
```

En JavaScript, sólo se puede devolver exactamente un valor. Si quieres pasar más información, tienes que combinarla primero en una entidad, normalmente en un objeto, o en un array.

```js
function divide(a, b) {
  return {
    quotient: Math.floor(a / b),
    remainder: a % b,
  };
}
```
### Función Expresión

Una declaración de función es una expresión independiente. Pero a veces resulta útil definir una función como parte de otra expresión, por ejemplo, en una asignación, como parámetro de una función (`callback`) o como valor en un objeto. Esto puede hacerse con una expresión de función. Tiene la misma sintaxis que una declaración de función, sólo que el nombre de la función puede omitirse para crear una función anónima.

```js
const someFunction = function (param) {
  // ...
};

someOtherFunction(function (param) {
  // ...
});

const obj = {
  someFunction: function (param) {
    // ...
  },
};
```
___
## Instrucciones

En este ejercicio, vas a escribir algo más de código relacionado con la preparación y cocción de tu brillante lasaña de tu libro de cocina favorito.  
  
Tienes cinco tareas. La primera está relacionada con la cocción en sí, las otras cuatro tratan sobre la preparación perfecta.
## 1. Determinar si la lasaña está hecha

Cuando tienes la lasaña en el horno, quieres saber si ya puedes sacarla o no. Para asegurarte de que la lasaña no se quema en el horno, sueles poner un temporizador. Pero a veces te olvidas de eso.

Escribe una función `cookingStatus` que acepte como parámetro el tiempo restante del temporizador en minutos. La función tiene tres resultados posibles.

- Si el temporizador muestra `0`, debería devolver `'Lasagna is done.'`.
- Si el temporizador muestra cualquier otro número, el resultado debe ser `'Not done, please wait.'`.
- Si se llama a la función sin un valor del temporizador, el resultado debe ser `'You forgot to set the timer.'`.

El temporizador nunca mostrará un valor inferior a 0.

```js
cookingStatus(12);
// => 'Not done, please wait.'

cookingStatus();
// => 'You forgot to set the timer.'
```
### Mi solución

```js
export function cookingStatus(remainingTime){
  if(remainingTime === 0){
    return "Lasagna is done."
  } else if(remainingTime === undefined){
    return "You forgot to set the timer."
  } else {
    return "Not done, please wait."
  }
}
```
## 2. Calcule el tiempo de preparación  

Para la próxima lasaña que vayas a preparar, querrás asegurarte de que tienes suficiente tiempo reservado para poder disfrutar de la cocción. Ya has hecho un plan con todas las capas que tendrá tu lasaña. Ahora debes calcular el tiempo de preparación en función de eso.  
  
Implementa una función `preparationTime` que acepte un array de capas y el tiempo medio de preparación por capa en minutos. La función debe devolver la estimación del tiempo total de preparación basado en el número de capas. Si se llama a la función sin proporcionar el tiempo medio de preparación, se asumirá que es de `2` minutos.

```js
const layers = ['sauce', 'noodles', 'sauce', 'meat', 'mozzarella', 'noodles'];
preparationTime(layers, 3);
// => 18

preparationTime(layers);
// => 12
```
### Mi solución

```js
export function preparationTime(layers, time = 2){
  return time * layers.length
}
```
## 3. Calcule las cantidades de fideos y salsa necesarias

Además de reservar el tiempo, también querrás asegurarte de que tienes suficiente salsa y fideos para cocinar la lasaña de tus sueños. Para cada capa de fideos de la lasaña, necesitará 50 gramos de fideos. Para cada capa de salsa de la lasaña, necesitará 0,2 litros de salsa.  
  
Defina la función `quantities` que toma como parámetro una matriz de capas. La función determinará entonces la cantidad de fideos y salsa necesaria para hacer su comida. El resultado se devolverá como un objeto con las claves `noodle` y `sauce`.

```js
quantities(['sauce', 'noodles', 'sauce', 'meat', 'mozzarella', 'noodles']);
// => { noodles: 100, sauce: 0.4 }
```
### Mi solución

```js
export function quantities(layers){
  let quant = {noodles: 0, sauce:0}
  for(let layer of layers){
    if(layer === "sauce"){
      quant.sauce += 0.2
    } else if(layer === "noodles"){
      quant.noodles += 50
    }
  }
  return quant
}
```
## 4. Añade el ingrediente secreto  

Hace un tiempo visitaste a un amigo y comiste lasaña allí. Estaba buenísima y tenía algo especial. El amigo te envió la lista de ingredientes y te dijo que el último elemento de la lista es el "ingrediente secreto" que hizo que la comida fuera tan especial. Ahora tú también quieres añadir ese ingrediente secreto a tu receta.  
  
Escribe una función `addSecretIngredient` que acepte dos matrices de ingredientes como parámetros. El primer parámetro es la lista que te envió tu amigo y el segundo es la lista de ingredientes de tu propia receta. La función debería añadir el último elemento de la lista de tu amigo al final de tu lista. El array que representa tu receta debe modificarse directamente y la función no debe devolver nada. Sin embargo, el primer argumento no debe ser modificado.

```js
const friendsList = ['noodles', 'sauce', 'mozzarella', 'kampot pepper'];
const myList = ['noodles', 'meat', 'sauce', 'mozzarella'];

addSecretIngredient(friendsList, myList);
// => undefined

console.log(myList);
// => ['noodles', 'meat', 'sauce', 'mozzarella', 'kampot pepper']
```
### Mi solución

```js
export function addSecretIngredient(friendList, myList){
  myList.push(friendList[friendList.length - 1])
}
```
## 5. Escala la receta  

Las cantidades que aparecen en el libro de cocina sólo dan para dos raciones de lasaña. Como quieres cocinar para más personas la próxima vez, te conviene calcular las cantidades para distintos números de raciones.  
  
Implementa una función `scaleRecipe` que tome dos parámetros.  
  
- Un objeto receta que contiene las cantidades necesarias para 2 raciones. El formato del objeto se puede ver en el siguiente ejemplo.  
- El número de porciones que desea cocinar.  

La función debe devolver un objeto receta con las cantidades necesarias para el número de porciones deseado. Sin embargo, se desea mantener la receta original. Esto significa, que en esta tarea el argumento receta no debe ser modificado.

```js
const recipe = {
  noodles: 200,
  sauce: 0.5,
  mozzarella: 1,
  meat: 100,
};

scaleRecipe(recipe, 4);
// =>
// {
//   noodles: 400,
//   sauce: 1,
//   mozzarella: 2,
//   meat: 200,
// };

console.log(recipe);
// =>
// {
//   noodles: 200,
//   sauce: 0.5,
//   mozzarella: 1,
//   meat: 100,
// };
```
### Mi solución

```js
export function scaleRecipe(recipe, portions){
  let total = {...recipe}
  for(let ingredient in recipe){
    total[ingredient] = recipe[ingredient] * (portions/2)
  }
  return total
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/lasagna-master
