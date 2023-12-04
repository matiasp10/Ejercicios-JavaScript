En el taller de Santa, **un elfo travieso** ha estado jugando en la cadena de fabricación de regalos, añadiendo o eliminando un paso no planificado.

Tienes la secuencia original de pasos en la fabricación _original_ y la secuencia modificada _modified_ que puede incluir un paso extra o faltar un paso.

Tu tarea es **escribir una función que identifique y devuelva el primer paso extra que se ha añadido o eliminado en la cadena de fabricación**. Si no hay ninguna diferencia entre las secuencias, devuelve una cadena vacía.

```javascript
const original = 'abcd'
const modified = 'abcde'
findNaughtyStep(original, modified) // 'e'

const original = 'stepfor'
const modified = 'stepor'
findNaughtyStep(original, modified) // 'f'

const original = 'abcde'
const modified = 'abcde'
findNaughtyStep(original, modified) // ''
```

A tener en cuenta:

- Siempre habrá un paso de diferencia o ninguno.
- La modificación puede ocurrir en cualquier lugar de la cadena.
- La secuencia _original_ puede estar vacía
## Mi solución

```js
function findNaughtyStep(original, modified) {
  if (original === modified) return "";
  let larger = original.length > modified.length ? original : modified
  let lower = original.length < modified.length ? original : modified

  for(let i = 0; i < larger.length; i++){
    if(larger[i] !== lower[i]) return larger[i]
  }
}
```
## Puntuación

- Puntos conseguidos: 340
- 3063 ops/s (Más alto es mejor)
- Complejidad cognitiva: 6(Más bajo es mejor)

Los retos son puntuados utilizando diferentes factores como la complejidad cognitiva y la velocidad de ejecución. El número de líneas no es un factor determinante.