En el taller de Santa, los elfos tienen una **lista de regalos** que desean fabricar y un conjunto limitado de materiales.

Los _regalos son cadenas de texto_ y los _materiales son caracteres_. Tu tarea es escribir una función que, dada una lista de regalos y los materiales disponibles, devuelva una **lista de los regalos que se pueden fabricar**.

Un regalo se puede fabricar si contamos con todos los materiales necesarios para fabricarlo.

```javascript
const gifts = ['tren', 'oso', 'pelota']
const materials = 'tronesa'

manufacture(gifts, materials) // ["tren", "oso"]
// 'tren' SÍ porque sus letras están en 'tronesa'
// 'oso' SÍ porque sus letras están en 'tronesa'
// 'pelota' NO porque sus letras NO están en 'tronesa'

const gifts = ['juego', 'puzzle']
const materials = 'jlepuz'

manufacture(gifts, materials) // ["puzzle"]

const gifts = ['libro', 'ps5']
const materials = 'psli'

manufacture(gifts, materials) // []
```
## Mi solución

```js
function manufacture(gifts, materials) {
  let aux = [];
  
  for (let gift of gifts) {
    let check = true
    for (let c of gift) {
      if(!materials.includes(c)){
        check = false
      }
    }
    if(check == true){
      aux.push(gift)
    }
  }
  return aux;
}
```
## Puntuación

- Puntos conseguidos: 270
- 2639 ops/s (Más alto es mejor)
- Complejidad cognitiva: 3(Más bajo es mejor)[](https://www.sonarsource.com/docs/CognitiveComplexity.pdf)

Los retos son puntuados utilizando diferentes factores como la complejidad cognitiva y la velocidad de ejecución. El número de líneas no es un factor determinante.