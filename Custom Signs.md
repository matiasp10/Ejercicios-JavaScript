#Learning
____
## Introducción 

En JavaScript, las cadenas de plantilla permiten incrustar expresiones en cadenas, lo que también se conoce como interpolación de cadenas. Esta funcionalidad amplía la del objeto global String incorporado.  
  
Puede crear cadenas de plantilla en JavaScript envolviendo el texto con puntos suspensivos. No sólo permiten que el texto incluya nuevas líneas y otros caracteres especiales, sino que también se pueden incrustar variables y otras expresiones.

```js
const num1 = 1;
const num2 = 2;

`Adding ${num1} and ${num2} gives ${num1 + num2}.`;
// => Adding 1 and 2 gives 3.
```

En el ejemplo anterior, los puntos suspensivos - (` `` `) - se utilizan para representar una cadena de plantilla. El `${...}` es el marcador de posición que se utiliza para la sustitución. Cualquier tipo que no sea cadena se convierte implícitamente en cadena. Este tema se trata en el concepto de conversión de tipos. Todos los tipos de expresiones pueden utilizarse con cadenas de plantilla.

```js
const track = 'JavaScript';

`This track on exercism.org is ${track.toUpperCase()}.`;
// => This track on exercism.org is JAVASCRIPT.
```

Cuando necesite formatear cadenas en varias líneas:

```js
`This is an example of using template
strings to accomplish multiple
lines`;
```

Con las funciones de sustitución disponibles, también puede introducir lógica en el proceso para determinar cuál debe ser la cadena de salida.  
  
Un ejemplo de ello es incrustar un operador ternario. Este operador es una forma abreviada de escribir una sentencia if/else. La sintaxis es condición ? expresión-consecuente : expresión-alternativa. Si la condición es verdadera, se devuelve el operando situado a la izquierda de los dos puntos. En caso contrario, el resultado de la expresión ternaria es el operando situado a la derecha de los dos puntos.

```js
const grade = 95;

`You have ${grade > 90 ? 'passed' : 'failed'} the exam.`;
// => You have passed the exam.
```
___
## Instrucciones

En este ejercicio estarás escribiendo código para ayudar a una compañía de letreros a crear mensajes personalizados para sus letreros.
## 1. Construir un cartel de ocasión  

Implementa la función `buildSign(occasion, name)` que acepta una cadena como parámetro de `occasion` y una cadena con el nombre de alguien como parámetro de `name`. Los dos parámetros se incrustarán en una cadena de plantilla para mostrar el mensaje en el cartel.

```js
buildSign('Birthday', 'Rob');
// => "Happy Birthday Rob!"
```
### Mi solución

```js
export function buildSign(occasion, name) {
  return `Happy ${occasion} ${name}!`
}
```
## 2. Construir un cartel de cumpleaños  

Implementa la función `buildBirthdaySign(age)` que acepta una edad y en base a la edad determinará parte del mensaje en el cartel. Si la edad es 50 o más, el cartel se referirá al usuario como maduro, de lo contrario se referirá a él como joven. La salida exacta esperada se muestra a continuación:

```js
buildBirthdaySign(50);
// => "Happy Birthday! What a mature fellow you are."

buildBirthdaySign(45);
// => "Happy Birthday! What a young fellow you are."
```
### Mi solución

```js
export function buildBirthdaySign(age) {
  if(age >= 50){
    return `Happy Birthday! What a mature fellow you are.`
  } else {
    return `Happy Birthday! What a young fellow you are.`
  }
}
```
## 3. Construir un signo de graduación  

Implementa la función `graduationFor(name, year)` que toma un nombre como parámetro de cadena y un año como parámetro numérico y utiliza la interpolación de cadenas para crear una frase para un letrero que utiliza una nueva línea para separar las dos líneas del mensaje.

```js
graduationFor('Hannah', 2022);
// => "Congratulations Hannah!\nClass of 2022"
```
### Mi solución

```js
export function graduationFor(name, year) {
  return `Congratulations ${name}!
Class of ${year}`
}
```
## 4. Calcular el coste de un signo  

Implementa la función `costOf(sign, currency)` que toma una cadena que contiene el contenido del signo y una cadena que representa la moneda. El signo tiene un precio base de 20 en la moneda dada. Además, cada letra cuesta 2. (Los espacios en blanco se incluyen en el cálculo.) La frase devuelta incluye el coste de crear el signo, escrito con dos dígitos después del punto decimal, seguido de la cadena de moneda.

```js
costOf('Happy Birthday Rob!', 'dollars');
// => "Your sign costs 58.00 dollars."
```
### Mi solución

```js
export function costOf(sign, currency) {
  return `Your sign costs ${Number.parseFloat(sign.length*2 + 20).toFixed(2)} ${currency}.`
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/custom-signs
