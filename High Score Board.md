#Learning 
____
Además de los tipos de datos primitivos como número y cadena, hay otro tipo de datos importante en JavaScript llamado objeto. Los objetos son colecciones de pares clave-valor. Como tales, pueden utilizarse del mismo modo que lo que en otros lenguajes se suele denominar mapas o diccionarios.  
  
En otros lenguajes, todos los valores de un mapa deben tener el mismo tipo de datos. En JavaScript, sólo el tipo de la clave está restringido: tiene que ser una cadena. Los valores dentro de un objeto pueden tener diferentes tipos. Pueden ser tipos primitivos como números, pero también matrices, otros objetos o incluso funciones. Esto hace que los objetos sean muy versátiles, por lo que también son entidades clave para la programación orientada a objetos (POO) en JavaScript.  
  
A continuación, nos centraremos en los objetos como colecciones o mapas. Otros casos de uso de objetos serán cubiertos en otros conceptos, ver por ejemplo, Clases.
## Creación de un objeto

Se crea un objeto utilizando llaves. También puede incluir directamente algunas entradas. Para ello, indique primero la clave, seguida de dos puntos y el valor.

```js
const emptyObject = {};

const obj = {
  favoriteNumber: 42,
  greeting: 'Hello World',
  useGreeting: true,
  address: {
    street: 'Trincomalee Highway',
    city: 'Batticaloa',
  },
  fruits: ['melon', 'papaya'],
  addNumbers: function (a, b) {
    return a + b;
  },
};
```

La coma final después de la última entrada es opcional en JavaScript.  
  
Puede que se pregunte por qué las claves no van entre comillas aunque se supone que son cadenas. Se trata de una notación abreviada. Si la clave sigue las reglas de nomenclatura de un identificador de JavaScript, puede omitir las comillas. Para las claves con caracteres especiales en el nombre, es necesario utilizar la notación de cadena habitual.

```js
const obj = {
  '1keyStartsWithNumber': '...',
  'key/with/slashes': '...',
  'key-with-dashes': '...',
  'key with spaces': '...',
  '#&()[]{}èä樹keyWithSpecialChars': '...',
};
```
## Recuperar un valor

Existen dos formas de recuperar el valor de una clave determinada, la notación por puntos y la notación por corchetes.

```js
const obj = { greeting: 'hello world' };

obj.greeting;
// => hello world

obj['greeting'];
// => hello world

// Bracket notation also works with variables.
const key = 'greeting';
obj[key];
// => hello world
```

El uso del punto como abreviatura tiene la misma restricción que la omisión de las comillas. Sólo funciona si la clave sigue las reglas de denominación de identificadores.
## Añadir o modificar un valor

Puede añadir o modificar un valor utilizando el operador de asignación ` = `. De nuevo, existen notaciones de punto y corchete.

```js
const obj = { greeting: 'hello world' };

obj.greeting = 'Hi there!';
obj['greeting'] = 'Welcome.';

obj.newKey1 = 'new value 1';
obj['new key 2'] = 'new value 2';

const key = 'new key 3';
obj[key] = 'new value 3';
```
## Borrar una entrada

Puede eliminar un par clave-valor de un objeto utilizando la palabra clave delete.

```js
const obj = {
  key1: 'value1',
  key2: 'value2',
};

delete obj.key1;
delete obj['key2'];
```
## Comprobación de la existencia de una clave

Puede comprobar si una determinada clave existe en un objeto con el método `hasOwnProperty`.

```js
const obj = { greeting: 'hello world' };

obj.hasOwnProperty('greeting');
// => true

obj.hasOwnProperty('age');
// => false
```
## Recorrer un objeto en bucle

Existe un bucle especial `for...in` para iterar sobre todas las claves de un objeto.

```js
const obj = {
  name: 'Ali',
  age: 65,
};

for (let key in obj) {
  console.log(key, obj[key]);
}
// name Ali
// age 65
```

Para evitar errores sutiles, debe asumir siempre que el bucle for...in visita las claves en un orden arbitrario. Además, tenga en cuenta que for...in incluye claves heredadas en su iteración.
___
## Instrucciones 

En este ejercicio, estás implementando una forma de llevar la cuenta de las puntuaciones más altas del juego más popular de tu salón recreativo local.  
  
Tienes 6 funciones que implementar, la mayoría relacionadas con la manipulación de un objeto que contiene las puntuaciones más altas.
## 1. Crear un nuevo tablero de puntuaciones altas  

Crea una función `createScoreBoard` que cree un objeto que sirva como tablero de puntuaciones altas. Las claves de este objeto serán los nombres de los jugadores, los valores serán sus puntuaciones. Para propósitos de prueba, quieres incluir directamente una entrada en el objeto. Esta entrada inicial debe consistir en El `"The Best Ever"` como nombre del jugador y `1000000` como puntuación.

```js
createScoreBoard();
// returns an object with one initial entry
```
### Mi solución

```js
export function createScoreBoard() {
  return {"The Best Ever": 1000000 }
}
```
## 2. Añadir jugadores a un tablero de puntuaciones  

Para añadir un jugador a la tabla de puntuaciones, define la función `addPlayer`. Acepta 3 parámetros:  
  
- El primer parámetro es un objeto de marcador existente.  
- El segundo parámetro es el nombre de un jugador en forma de cadena.  
- El tercer parámetro es la puntuación en forma de número.  

La función devuelve el mismo objeto de marcador que se pasó después de añadir el nuevo jugador.

```js
addPlayer({ 'Dave Thomas': 0 }, 'José Valim', 486373);
// => {'Dave Thomas': 0, 'José Valim': 486373}
```
### Mi solución

```js
export function addPlayer(scoreBoard, player, score) {
  scoreBoard[player] = score
  return scoreBoard
}
```
## 3. Eliminar jugadores de una tabla de puntuaciones  

Si los jugadores violan las reglas del salón recreativo, son eliminados manualmente de la tabla de puntuaciones. Define removePlayer que toma 2 parámetros:  
  
- El primer parámetro es un objeto de marcador existente.  
- El segundo parámetro es el nombre del jugador en forma de cadena.  

Esta función debe eliminar del tablero la entrada para el jugador dado y devolver el tablero después. Si el jugador no estaba en el tablero en primer lugar, no debería pasarle nada al tablero. Se devolverá tal cual.

```js
removePlayer({ 'Dave Thomas': 0 }, 'Dave Thomas');
// => {}

removePlayer({ 'Dave Thomas': 0 }, 'Rose Fanaras');
// => { 'Dave Thomas': 0 }
```
### Mi solución

```js
export function removePlayer(scoreBoard, player) {
  delete scoreBoard[player]
  return scoreBoard
}
```
## 4. Aumentar la puntuación de un jugador

Si un jugador termina otra partida en el salón recreativo, se añadirá una cierta cantidad de puntos a la puntuación anterior en el tablero. Implementa updateScore, que toma 3 parámetros:

- El primer parámetro es un objeto de tablero de puntuación existente.
- El segundo parámetro es el nombre del jugador cuya puntuación debe ser incrementada.
- El tercer parámetro es la puntuación que se desea añadir a la puntuación máxima almacenada.

La función debe devolver el tablero de puntuaciones una vez realizada la actualización.

```js
updateScore({ 'Freyja Ćirić': 12771008 }, 'Freyja Ćirić', 73);
// => {"Freyja Ćirić", 12771081}
```
### Mi solución

```js
export function updateScore(scoreBoard, player, points) {
  scoreBoard[player] = scoreBoard[player] + points
  return scoreBoard
}
```
## 5. Aplicar los puntos de bonificación de los lunes 

El salón recreativo mantiene un tablero de puntuación separado los lunes. Al final del día, cada jugador de ese tablero obtiene 100 puntos adicionales.  
  
Implementa la función `applyMondayBonus` que acepta un tablero de puntuación. La función añade los puntos de bonificación para cada jugador que aparece en ese tablero. Después, se devuelve el tablero.

```js
const scoreBoard = {
  'Dave Thomas': 44,
  'Freyja Ćirić': 539,
  'José Valim': 265,
};

applyMondayBonus(scoreBoard);
// => { 'Dave Thomas': 144, 'Freyja Ćirić': 639, 'José Valim': 365 }
```
### Mi solución

```js
export function applyMondayBonus(scoreBoard) {
  for(let player in scoreBoard){
    scoreBoard[player] = scoreBoard[player] + 100
  }
  return scoreBoard
}
```
## 6. Normalizar una puntuación alta  

Los distintos salones recreativos otorgan puntuaciones diferentes. Para celebrar al mejor jugador arcade de la ciudad, la puntuación de un jugador debe normalizarse para que las puntuaciones de los distintos salones arcade sean comparables.  
  
Escribe una función `normalizeScore`. Para practicar tus habilidades con los objetos, en lugar de dos parámetros esta función debería aceptar un objeto como parámetro. Ese objeto contiene una clave puntuación cuyo valor es la puntuación de un jugador (un número). También hay una segunda clave `normalizeFunction` que tiene una función como valor. Esta función toma una puntuación como argumento y devuelve la puntuación corregida.  
  
Su función `normalizeScore` debe devolver la puntuación normalizada que se obtiene después de aplicar la función de normalización a la puntuación que se pasó.

```js
function normalize(score) {
  return 2 * score + 10;
}

const params = { score: 400, normalizeFunction: normalize };
normalizeScore(params);
// => 810
```
### Mi solución

```js
export function normalizeScore(params) {
  return params.normalizeFunction(params.score)
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/high-score-board