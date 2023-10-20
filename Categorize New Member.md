#7kyu 
___
# Categorizar Miembro Nuevo

El Western Suburbs Croquet Club tiene dos categorías de socios: Senior y Open. Les gustaría que les ayudaras con un formulario de solicitud que indicará a los futuros socios en qué categoría se encuadrarán.

Para ser senior, un socio debe tener **al menos 55 años** y un **hándicap superior a 7**. En este club de croquet, los hándicaps van de -2 a +26; cuanto mejor sea el jugador, menor será el hándicap.

## Input

La entrada consistirá en una **lista de pares**. Cada par contiene información sobre un miembro potencial. La información consiste en un número entero para la edad de la persona y un número entero para el hándicap de la persona.

## Output

La salida consistirá en un array de strings (en Haskell y C: Open o Senior) que indicarán si el miembro respectivo debe colocarse en la categoría senior o open.

## Ejemplo

```bash
input =  [[18, 20], [45, 2], [61, 12], [37, 6], [21, 21], [78, 9]]
output = ["Open", "Open", "Senior", "Open", "Open", "Senior"]
```

## Link del problema

[Problema](https://www.codewars.com/kata/5502c9e7b3216ec63c0001aa/train/javascript)
## Mi solución

```js
function openOrSenior(data){
// Inicializo una variable como un array vacio, que es donde voy a almacenar las categorias de los socios
  let result = []
// Mediante un bucle for...of recorro el array que recibo como input con las edades y handicaps de los socios
    for(let i of data){
    // En un condicional if...else recorro cada socio con la condicion que sea mayor o igual que 55 y tenga un handicap mayor a 7 siendo asi socios "Senior" pusheandolos al array, de lo contrario seran socios "Open" que tambien seran pusheados al array.
    if(i[0] >= 55 && i[1] > 7){
      result.push("Senior")
    } else {
      result.push("Open")
    }
  }
  return result
}
```

-   [Array](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array)
-   [For...of](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/for...of)
-   [If ... else](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/if...else)
-   [.push()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/push)

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]