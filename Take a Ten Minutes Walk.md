#6kyu 
___
Vives en la ciudad de **Cartesia**, donde todas las calles están trazadas en una cuadrícula perfecta. Has llegado diez minutos demasiado pronto a una cita, así que has decidido aprovechar para dar un pequeño paseo. La ciudad pone a disposición de sus ciudadanos una aplicación que genera paseos en sus teléfonos: cada vez que pulsas el botón, te envía una serie de cadenas de una sola letra que representan las direcciones a seguir (por ejemplo, `['n', 's', 'w', 'e']`). Siempre caminas una sola manzana por cada letra (dirección) y sabes que tardas un minuto en recorrer una manzana, así que crea una función que devuelva **true** si el paseo que te da la aplicación te lleva exactamente diez minutos (¡no quieres llegar pronto ni tarde!) y que, por supuesto, te devuelva al punto de partida. En caso contrario, devolverá **false**.

>[!note] Nota
>Siempre recibirá un array válido que contiene un surtido aleatorio de letras de dirección ('n', 's', 'e', o 'w' solamente). Nunca te dará un array vacío (¡eso no es un paseo, eso es estar parado!).
## Link del problema

https://www.codewars.com/kata/54da539698b8a2ad76000228/train/javascript
## Mi solución

```js
function isValidWalk(walk) {
  let directions = { n: 0, s: 0, w: 0, e: 0 };
  if (walk.length === 10) {
    for (let d of walk) {
      directions[d] = directions[d] + 1;
    }
    if (
      directions.n - directions.s === 0 &&
      directions.e - directions.w === 0
    ) {
      return true;
    } else {
      return false;
    }
  } else {
    return false;
  }
}
```