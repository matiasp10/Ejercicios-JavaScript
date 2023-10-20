#8kyu 
___
¡A jugar! ¡Tienes que devolver qué jugador ha ganado! En caso de empate ¡devuelve Empate!.
## Ejemplos

```
"scissors", "paper" --> "Player 1 won!"
"scissors", "rock" --> "Player 2 won!"
"paper", "paper" --> "Draw!"
```

## Link del problema

https://www.codewars.com/kata/5672a98bdbdd995fad00000f/train/javascript

## Mi solución

```js
const rps = (p1, p2) => {
  if(p1 === p2) return "Draw!"
  else if(
    p1 === "rock" && p2 === "scissors" || 
    p1 === "scissors" && p2 === "paper" || 
    p1 === "paper" && p2 === "rock") {
    return "Player 1 won!"
  }
  else return "Player 2 won!"
};
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]