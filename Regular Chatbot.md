#Learning 
___
## Instrucciones

Te han contratado como Especialista en Expresiones Regulares en una empresa que está desarrollando un Chatbot.  
  
Se encuentra en una fase muy básica de desarrollo, de ahí que tu misión sea utilizar Expresiones Regulares para mejorar la capacidad del chatbot para comprender y generar lenguaje natural.
## 1.Comprobar comando válido  

Además de inteligente, el Chatbot es un asistente leal.  
  
Para pedir algo al chatbot, el usuario debe decir la palabra "Chatbot" en la primera posición del comando.  
  
No importa si la palabra clave está en MAYÚSCULAS o en minúsculas. Lo importante aquí es la posición de la palabra.  
  
Implementa la función `isValidCommand()` que ayuda al Chatbot a reconocer cuando el usuario está dando un comando.

```js
isValidCommand("Chatbot, play a song from the 80's.";
// => True
isValidCommand("Hey Chatbot, where is the closest pharmacy?";
// => False
isValidCommand("CHATBOT, do you have a solution for this challenge?";
// => True
```
### Mi solución

```js
export function isValidCommand(command) {
  if(command.match(/Chatbot/i).index === 0) return true
  else return false
}
```
## 2. Eliminar emojis encriptados  

Al Chatbot le cuesta entender cómo los humanos utilizan los emojis para expresar sus emociones.  
  
Cuando el chatbot recibe mensajes de usuarios, cada emoji se representa como "emoji" seguido de su número de id.  
  
Implementa el método `removeEmoji()` para tomar una cadena y eliminar todas las codificaciones de emoji a lo largo del mensaje.  
  
Las líneas que no contengan texto de emoji deben devolverse sin modificar.  
  
Simplemente elimina la cadena emoji. No intente ajustar los espacios en blanco.  
  
Para este desafío en particular, utilice la sintaxis del constructor para crear la expresión regular.

```js
removeEmoji("I love playing videogames emoji3465 it's one of my hobbies");
// => "I love playing videogames  it's one of my hobbies"
```
### Mi solución

```js
export function removeEmoji(message) {
  return message.replace(/emoji[\d]+/g, "")
}
```
## 3. Comprobar el número de teléfono válido  

Teniendo en cuenta la descarga de funciones de chatbot en una aplicación móvil, se espera que el usuario escriba un número de teléfono durante la conversación.  
  
El problema es que el chatbot solo puede leer y validar un número con un formato específico.  
  
Si el número es válido (coincide con la secuencia de caracteres especificada por la expresión regular), el chatbot responde con un mensaje de agradecimiento al usuario y confirma el número. Si el número no es válido, la función informa al usuario de que el número de teléfono no es válido.  
  
El formato esperado es: **(+##) ###-##-####**

```js
checkPhoneNumber('(+34) 659-771-594');
// => "Thanks! You can now download me to your phone."
checkPhoneNumber('659-771-594');
// => "Oops, it seems like I can't reach out to 659-771-594"
```
### Mi solución

```js
export function checkPhoneNumber(number) {
  const REGEX = /\(\+\d{2}\) \d{3}-\d{3}-\d{3}/
  const VALID = "Thanks! You can now download me to your phone."
  const INVALID = `Oops, it seems like I can't reach out to ${number}`
  return REGEX.test(number) ? VALID : INVALID
}
```
## 4. Obtener enlace web  

El Chatbot es un software realmente curioso. Aunque puede buscar en Internet sobre un tema concreto, le gusta preguntar a los usuarios sobre sitios web o URL interesantes para encontrar información relevante.  
  
Ejemplo de conversación:  
  
- **Chatbot**: Hola nombre de usuario, me gustaría aprender a programar en JavaScript, ¿conoces algún sitio web interesante donde pueda aprender?  
- **User**: He aprendido mucho en exercism.com  

Implementar la función `getURL()` que es capaz de devolver una matriz con sólo el enlace de cada sitio web.

```js
getURL('I learned a lot from exercism.com');
// => ["exercism.com"];
```
### Mi solución

```js
export function getURL(userInput) {
  return userInput.match(/\w+\.\w+/g)
}
```
## 5. Saludar al usuario  

Para almacenar los datos de todas las personas con las que se ha mantenido una conversación, el chatbot puede obtener el Nombre Completo del perfil del usuario con este estilo "smith, john".  
  
De esta forma, queremos que nuestro chatbot sea realmente educado y cause una buena impresión.  
  
Escribe la función `niceToMeetYou()` que toma una cadena con el nombre completo del usuario, y devuelve la cadena "Nice to meet you, John Smith"  
  
Para fines de aprendizaje, implemente la función utilizando un método de sustitución de Expresiones Regulares.

```js
let str = 'Smith, John';

niceToMeetYou(str);
// => "Nice to meet you, John Smith"
```
### Mi solución

```js
export function niceToMeetYou(fullName) {
  const [lastName, firstName] = fullName.split(", ")
  return `Nice to meet you, ${firstName} ${lastName}`
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/regular-chatbot