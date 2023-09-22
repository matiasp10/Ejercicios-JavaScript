¡¡Si no puedes dormir, cuenta ovejas!!

Dado un número entero no negativo, 3 por ejemplo, devuelve una cadena con un murmullo: "1 oveja...2 ovejas...3 ovejas...". La entrada siempre será válida, es decir, sin enteros negativos.

## Link del problema

https://www.codewars.com/kata/5b077ebdaf15be5c7f000077/train/javascript

## Mi solución

```js
function countSheep(num){
  let sheeps = []
  for(let i = 1; i <= num; i++){
    sheeps.push(`${i} sheep...`)
  }
  return sheeps.join("")
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]