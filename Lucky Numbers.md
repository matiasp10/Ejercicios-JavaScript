## Introducción

En JavaScript, los valores pueden ser de diferentes tipos. El cambio de tipo de una variable puede realizarse mediante una conversión de tipo explícita. Además, JavaScript también realiza coerción de tipos (conversión implícita de tipos) cuando el contexto lo requiere.
### Conversión de tipo

JavaScript no tiene una construcción para convertir a un tipo (diferente) como muchos otros lenguajes, pero en su lugar se pueden utilizar algunos ayudantes incorporados. En particular, `Boolean`, `Number` y `String` pueden utilizarse como funciones para convertir un valor al tipo correspondiente.
#### Conversión a booleano (valores verdaderos/falsos)

Con `Boolean(value)` puede convertir cualquier valor en un booleano. Hay un conjunto fijo de valores, llamados valores falsos, que se convierten en `false`. Los más importantes son `false`, `0`, cadena vacía, `null`, `undefined` y `NaN`.  
  
Para todos los demás valores, `Boolean` devuelve `true`. Estos valores se llaman **truthy**.

```js
Boolean(-1);
// => true

Boolean(0);
// => false

Boolean(' ');
// => true

Boolean('');
// => false
```

Tenga en cuenta que, debido a las reglas descritas, '0', 'false', [] y {} son verdaderos en JavaScript.
#### Conversión a un número

`Number(value)` puede utilizarse para convertir un valor en un número. Los espacios en blanco al principio y al final de una cadena se ignoran y una cadena vacía se convierte a `0`. Si intenta convertir un valor no primitivo o una cadena que no representa un número, el resultado es `NaN` (Not-A-Number).

```js
Number('  -12.34  ');
// => -12.34

Number('1,2');
// => NaN

Number('');
// => 0

Number({ num: 123 });
// => NaN
```
#### Conversión a cadena

Con `String(value)` puede convertir un valor en una cadena. El resultado es el esperado para los valores primitivos.

```js
String(12.34);
// => '12.34'

String(false);
// => 'false'

String(null);
// => 'null'

String(undefined);
// => 'undefined'
```

Para matrices, la función `String` aplicará la conversión de cadena para cada elemento y unirá los resultados con una coma. También puede aplicar el método `join` usted mismo, por ejemplo, para personalizar el separador. Tenga en cuenta que en estos casos `null` e `undefined` se convertirán en una cadena vacía.

```js
String([42, null, true, 'abc']);
// => '42,,true,abc'
```

Para los objetos, por defecto `String` devuelve un texto poco útil.

```js
String({ key: 'value' });
// => '[object Object]'
```
### Tipo Coerción

En ciertos contextos, JavaScript convertirá automáticamente un valor a otro tipo de datos antes de evaluar alguna sentencia. Esta conversión implícita se denomina coerción de tipos.
#### Contexto booleano

Cuando se utiliza un valor no booleano en un contexto booleano, JavaScript aplicará las mismas reglas que la función `Boolean` para convertir implícitamente el valor.  
  
La coerción a booleano se produce normalmente para  
  
- la condición de una sentencia `if`.  
- el primer operando del operador ternario `?`.  
- ¡el operando del operador lógico NOT `!`.  
- los operandos de los operadores lógicos AND `&&` y OR `||` (el resultado de la expresión es uno de los operandos, no necesariamente un booleano).

```js
const num = 0;
if (num) {
  // this block is NOT executed because 0 is falsy
}
```
#### Contexto de las cadenas

Si se utiliza el operador de suma `+` para valores primitivos y uno de los operandos es una cadena, el otro también se convertirá en una cadena. La lógica de conversión es la misma que cuando se utiliza la función `String`. A continuación, se concatenan las dos cadenas.

```js
let name;
'hello ' + name;
// => 'hello undefined'
```
#### Contexto numérico

Muchos operadores convierten los operandos en números (si es necesario) de acuerdo con la lógica de la función Número explicada anteriormente.  
  
- Operadores aritméticos: `+` (si no hay ninguna cadena implicada), `-, *, /, %, **`.
- Operadores unarios de suma y negación: `+`, `-`.
- Operadores relacionales (para operandos que no sean cadenas): `>`, `>=`, `<`, `<=`
- Operadores bit a bit: `|`, `&`, `^`, `~`.  
  
Para evitar errores, es una buena práctica llamar siempre a `Number` explícitamente antes de aplicar esos operadores.
___
## Instrucciones

Tu amigo Kojo es un gran aficionado a los números. Tiene un pequeño sitio web para jugar con los números: `www.fun-with-numbers.com`. A Kojo no se le da muy bien programar, así que te ha pedido ayuda.  
  
Construirás dos funciones de ayuda para nuevos juegos de números en el sitio web de Kojos y una tercera para validar alguna entrada que el usuario pueda introducir.
## 1. Calcula la suma de los números de la máquina tragaperras  

Uno de los juegos de la página web de Kojos se parece a una máquina tragaperras que muestra dos grupos de ruedas con cifras. Cada grupo de dígitos representa un número. Para la mecánica del juego, Kojo necesita saber la suma de esos dos números.  
  
Escribe una función `twoSum` que acepte dos matrices como parámetros. Cada array consiste en uno o más números entre 0 y 9. La función debe interpretar cada matriz como un número y devolver la suma de esos dos números.

```js
twoSum([1, 2, 3], [0, 7]);
//=> 130

// [1, 2, 3] represents 123 and [0, 7] represents 7.
// 123 + 7 = 130
```
### Mi solución

```js
export function twoSum(array1, array2) {
  return +array1.join("") + +array2.join("")
}
```
## 2. Determinar si un número es un palíndromo  

Otro juego de la web es un pequeño concurso llamado "Números de la suerte". El usuario introduce un número y comprueba si pertenece a una secuencia o patrón secreto. La secuencia o patrón de los "números de la suerte" cambia cada mes y cada usuario sólo tiene un número limitado de intentos para adivinarlo.  
  
Los números de la suerte de este mes deben ser números palíndromos. Los números palindrómicos siguen siendo los mismos cuando se invierten las cifras.  
  
Implementa la nueva función `luckyNumber` que acepta un número como parámetro. La función debe devolver `true` si el número es un palíndromo y `false` en caso contrario. El número de entrada será siempre un número entero positivo.

```js
luckyNumber(1441);
//=>  true

luckyNumber(123);
//=> false
```
### Mi solución

```js
export function luckyNumber(value) {
  let inverted = Number(String(value).split("").reverse().join(""))
  if(inverted === value){
    return true
  } else {
    return false
  }
}
```
## 3. Generar un mensaje de error en caso de que el usuario introduzca datos no válidos  

En varios lugares del sitio web, hay campos de entrada donde los usuarios pueden introducir números y hacer clic en un botón para desencadenar alguna acción. Kojo quiere mejorar la experiencia de usuario de su sitio. Quiere mostrar un mensaje de error en caso de que el usuario haga clic en el botón pero el campo contenga un valor de entrada no válido.  
  
Aquí hay más información sobre cómo se proporciona el valor de un campo de entrada.  
  
- Si el usuario teclea algo en un campo, el valor asociado es siempre una cadena aunque el usuario sólo haya tecleado números.  
- Si el usuario teclea algo pero lo vuelve a borrar, la variable será una cadena vacía.  
- Antes incluso de que el usuario empiece a escribir, la variable puede ser `undefined` o `null`.  

Escribe una función `errorMessage` que acepte la entrada del usuario como parámetro. Si el usuario no proporcionó ninguna entrada, `errorMessage` debería devolver `'Required field'`. Si la entrada no representa un número distinto de cero (de acuerdo con las reglas de conversión de JavaScript), se devolverá `'Must be a number besides 0'`. En todos los demás casos, puede asumir que la entrada es válida, el valor de retorno debería ser una cadena vacía.

```js
errorMessage('123');
// => ''

errorMessage('');
// => 'Required field'

errorMessage('abc');
// => 'Must be a number besides 0'
```
### Mi solución

```js
export function errorMessage(input) {
  if(input === "" || input === null || input === undefined){
    return 'Required field'
  } else if(Number.isNaN(+input) || input === "0"){
    return 'Must be a number besides 0'
  } else {
    return ""
  }
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/lucky-numbers