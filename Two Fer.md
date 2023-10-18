#Easy
____
## Introducción 

En algunos acentos ingleses, cuando se dice `"two for"` rápidamente, suena como `"two fer"`. Dos por uno es una forma de decir que si compras uno, también te llevas otro gratis. Así que la frase `"two-fer"` suele implicar una oferta de dos por uno.  
  
Imagínese una panadería que tiene una oferta navideña en la que puede comprar dos galletas por el precio de una (`"¡dos por una!"`). Usted acepta la oferta y (muy generosamente) decide regalar la galleta extra a un amigo.
___
## Instrucciones 

Tu tarea consiste en determinar qué dirás mientras regalas la galleta extra.  
  
Si a tu amigo le gustan las galletas y se llama Do-yun, entonces dirás:

```
One for Do-yun, one for me.
```

Si a tu amigo no le gustan las galletas, le das la galleta a la siguiente persona de la cola de la pastelería. Como no sabes su nombre, dirás "tú" en su lugar.

```
One for you, one for me.
```

He aquí algunos ejemplos:

| name   | dialogue                    |
| ------ | --------------------------- |
| Alice  | One for Alice, one for me.  |
| Bohdan | One for Bohdan, one for me. |
|        | One for you, one for me     |
| Zaphod | One for Zaphod, one for me. |
### Mi solución

```js
export const twoFer = (name = "you") => {
  return `One for ${name}, one for me.`
};
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/two-fer