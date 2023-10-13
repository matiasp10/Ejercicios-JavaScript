## Introducción 

A diferencia de muchos otros lenguajes, en JavaScript existen dos entidades diferentes que representan la ausencia de un valor (significativo). Existe null y undefined.
### Null

El valor primitivo `null` se utiliza como "valor vacío" intencional para variables de cualquier tipo.

```js
let name = null;
// name is intentionally set to "empty" because it is not
// available
```

Puede comprobar si una variable es nula utilizando el operador de igualdad estricta ` === `.

```js
let name = null;

name === null;
// => true
```
### Undefined

> [!faq] ¿Que es undefined?
> Una variable a la que no se ha asignado un valor es de tipo indefinido.
  
Eso significa que mientras `null` representa un valor vacío (pero aún así un valor), `undefined` representa la ausencia total de un valor. 
  
`undefined` aparece en diferentes contextos.  
  
- Si una variable se declara sin un valor (inicialización), es `undefined`.  
- Si se intenta acceder a un valor para una clave inexistente en un objeto, se obtiene `undefined`.  
- Si una función no devuelve un valor, el resultado es `undefined`.  
- Si no se pasa un argumento a una función, ésta queda `undefined`, a menos que dicho argumento tenga un valor por defecto.

```js
let name;
console.log(name);
// => undefined
```

Puede comprobar si una variable es indefinida utilizando el operador de igualdad estricta ` === `.

```js
let name;

name === undefined;
// => true
```
### Optional chaining

Si intenta recuperar un valor anidado en un objeto pero la clave padre no existe, JavaScript arrojará un error. Para evitarlo fácilmente, en 2020 se añadió el encadenamiento opcional a la especificación del lenguaje. Con el operador de encadenamiento opcional `?.` puede asegurarse de que JavaScript sólo intente acceder a la clave anidada si la clave padre no es `null` o `undefined`. En caso contrario, se devuelve `undefined`.

```js
const obj = {
  address: {
    street: 'Trincomalee Highway',
    city: 'Batticaloa',
  },
};

obj.address.zipCode;
// => undefined

obj.residence.street;
// => TypeError: Cannot read property 'street' of undefined

obj.residence?.street;
// => undefined
```
### Nullish coalescing

Hay situaciones en las que se desea aplicar un valor por defecto en caso de que una variable sea nula o indefinida (pero sólo en ese caso). Para solucionar este problema, en 2020 se introdujo el operador de coalescencia nulo `??` Devuelve el operando del lado derecho sólo cuando el operando del lado izquierdo es `null` o `undefined`. En caso contrario, devuelve el operando de la izquierda.

```js
let amount = null;
amount = amount ?? 1;
// => 1

amount = 0;
amount = amount ?? 1;
// => 0
```
___
## Instrucciones

Su trabajo consiste en proporcionar y mantener partes del sistema informático de un parque de atracciones. En concreto, eres responsable del programa que gestiona los visitantes y las entradas.  
  
En primer lugar, creará un nuevo visitante en el sistema. A continuación, proporcionará una función para revocar una entrada. En las tareas 3 y 4, trabajará en el sistema de seguimiento de entradas que ayuda a evitar falsificaciones. Por último, ayudará a adaptar el sistema a los nuevos requisitos legales.
## 1. Crear un nuevo visitante  

Cuando los visitantes acuden al parque de atracciones por primera vez, tienen que registrarse introduciendo su nombre y edad en un terminal y aceptando los términos y condiciones. Por supuesto, también tienen que comprar una entrada. Cada entrada tiene un identificador como `H32AZ123`.  
  
Escribe una función `createVisitor` que acepte tres argumentos.  
  
- El nombre del visitante.  
- La edad del visitante.  
- El identificador del billete que compró el visitante.  

La función debe devolver un objeto que contenga esta información. Las claves del objeto deben llamarse `name`, `age` y `ticketId`.

```js
createVisitor('Verena Nardi', 45, 'H32AZ123');
// => { name: 'Verena Nardi', age: 45, ticketId: 'H32AZ123' }
```
### Mi solución

```js
export function createVisitor(name, age, ticketId) {
  return {
    name,
    age,
    ticketId
  }
}
```
## 2. Revocar la entrada  

Cuando una persona abandona el parque de atracciones, se le revoca la entrada. Si vuelven, tendrán que comprar una nueva. Para ahorrar tiempo a los visitantes habituales, sólo tienen que registrarse una vez y la información del visitante se conservará para visitas posteriores.  
  
Esto significa que cuando un visitante abandona el parque, sólo su entrada debe ser invalidada, pero el resto del objeto visitante debe permanecer igual. Implementa la función `revokeTicket` que acepta un objeto visitante, establece el identificador del ticket a `null` y devuelve el objeto después.

```js
const visitor = {
  name: 'Verena Nardi',
  age: 45,
  ticketId: 'H32AZ123',
};

revokeTicket(visitor);
// => { name: 'Verena Nardi', age: 45, ticketId: null }
```
### Mi solución

```js
export function revokeTicket(visitor) {
  visitor.ticketId = null
  return visitor
}
```
## 3. Determinar el estado del billete  

Para evitar falsificaciones, los identificadores de los billetes son únicos. Una vez impreso un billete, su identificador se añade como clave en un objeto del sistema para que pueda ser rastreado.  
  
Antes de que el billete se venda a un visitante, se almacena con el valor `null` en el objeto de seguimiento del billete. Cuando se vende a un visitante, se le asigna como valor el nombre del visitante. Cuando los empleados tienen dudas sobre la validez de un ticket, deben comprobar el estado del ticket en el sistema.  
  
Implemente una función `ticketStatus` que acepte el objeto de seguimiento y un identificador de ticket como argumentos. Debe devolver uno de los siguientes resultados.  
  
- `'unknown ticket id'` si no se ha encontrado el identificador en el objeto de seguimiento.
- `'not sold'` en caso de que el billete se haya impreso pero no se haya vendido. 
- `'sold to {name}'` donde `{name}` es el nombre del visitante si el billete se vendió.

```js
const tickets = {
  '0H2AZ123': null,
  '23LA9T41': 'Verena Nardi',
};

ticketStatus(tickets, 'RE90VAW7');
// => 'unknown ticket id'

ticketStatus(tickets, '0H2AZ123');
// => 'not sold'

ticketStatus(tickets, '23LA9T41');
// => 'sold to Verena Nardi'
```
### Mi solución

```js
export function ticketStatus(tickets, ticketId) {
  if (tickets.hasOwnProperty(ticketId)){
    if(tickets[ticketId] !== null) return `sold to ${tickets[ticketId]}`
    if(tickets[ticketId] == null) return "not sold"
  } else {
    return "unknown ticket id"
  }
}
```
## 4. Mejorar la respuesta sobre el estado de los tickets

Al cabo de un tiempo, los empleados responden que quieren que el estado del ticket sea más fácil de entender a primera vista. Sólo quieren ver el nombre del visitante o que el ticket no es válido.  
  
Escriba una función `simpleTicketStatus` que acepte los mismos argumentos que `ticketStatus` en la tarea 3. Esta función sólo devuelve uno de dos resultados diferentes.  

- El nombre del visitante si la entrada se ha vendido.
- `'invalid ticket !!!'` si la entrada aún no se ha vendido o no se ha encontrado el identificador en el objeto de seguimiento.

```js
const tickets = {
  '0H2AZ123': null,
  '23LA9T41': 'Verena Nardi',
};

simpleTicketStatus(tickets, '23LA9T41');
// => 'Verena Nardi'

simpleTicketStatus(tickets, '0H2AZ123');
// => 'invalid ticket !!!'

simpleTicketStatus(tickets, 'RE90VAW7');
// => 'invalid ticket !!!'
```
### Mi solución

```js
export function simpleTicketStatus(tickets, ticketId) {
  if(tickets.hasOwnProperty(ticketId) && tickets[ticketId] !== null){
    return tickets[ticketId]
  } else {
    return "invalid ticket !!!"
  }
}
```
## 5. Determinar la versión de los términos y condiciones  

Debido a nuevos requisitos legales, los objetos de visitante recién creados ahora también contienen información detallada sobre las "Condiciones Generales de Contratación" (CGC) que el usuario aceptó. A continuación puede ver un ejemplo del nuevo objeto de visitante.  
  
Los cajeros del parque de atracciones ahora necesitan comprobar si un visitante necesita firmar una nueva versión de las CGC. Para ello, implementan una función `gtcVersion` que acepta un objeto visitante como argumento y devuelve la versión de las CGC si está disponible. Si la información sobre la versión no está disponible, no se devolverá nada.

```js
const visitorNew = {
  name: 'Verena Nardi',
  age: 45,
  ticketId: 'H32AZ123',
  gtc: {
    signed: true,
    version: '2.1',
  },
};

gtcVersion(visitorNew);
// => '2.1'

const visitorOld = {
  name: 'Verena Nardi',
  age: 45,
  ticketId: 'H32AZ123',
};

gtcVersion(visitorOld);
// => undefined
```
### Mi solución

```js
export function gtcVersion(visitor) {
  return visitor.gtc?.version
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/amusement-park