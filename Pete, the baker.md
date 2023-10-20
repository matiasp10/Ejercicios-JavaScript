#5kyu 
___
# Pete, el pastelero

A Pete le gusta hacer pasteles. Tiene algunas recetas e ingredientes. Por desgracia, no se le dan bien las matemáticas. ¿Puedes ayudarle a averiguar cuántos pasteles puede hacer teniendo en cuenta sus recetas?

Escriba una función **cakes()**, que tome la receta (**objeto**) y los ingredientes disponibles (también un **objeto**) y devuelva el número máximo de pasteles que Pete puede hornear (**entero**). Para simplificar, no hay unidades para las cantidades (por ejemplo, 1 lb de harina o 200 g de azúcar son simplemente 1 o 200). Los ingredientes que no están presentes en los objetos, se pueden considerar como 0.

## Ejemplos

```js
// must return 2
cakes({flour: 500, sugar: 200, eggs: 1}, {flour: 1200, sugar: 1200, eggs: 5, milk: 200}); 
// must return 0
cakes({apples: 3, flour: 300, sugar: 150, milk: 100, oil: 100}, {sugar: 500, flour: 2000, milk: 2000});
```

## Link del problema

[Problema](https://www.codewars.com/kata/525c65e51bf619685c000059/train/javascript)

## Mi solución

```js
function cakes(recipe, available) {

  let cantPorIngrediente = []

  for(let ingrediente in recipe){

    let isIngredienteAvailable = Number.isNaN(available[ingrediente] / recipe[ingrediente])

    if (isIngredienteAvailable){
      return 0
    } else {
      cantPorIngrediente.push(available[ingrediente] / recipe[ingrediente])
    }
  }
  let minimo = Math.min(...cantPorIngrediente)
  let redondeoMinimo = Math.floor(minimo)
  return redondeoMinimo
}
```

Inicializó una variable que es donde voy a almacenar la cantidad de recetas que voy a poder realizar por ingredientes `cantPorIngrediente`.

Recorro el objeto `recipe` mediante un `for...in` para iterar sobre cada ingrediente de la receta.  
En una variable almaceno un valor que me verifica mediante `Number.isNaN()` si el ingrediente que estoy iterando es **NaN**, lo que al problema significaría que el ingrediente de la receta no lo tenemos disponible, ya que `available[ingrediente]` si no existiese seria **undefined** y `undefined / recipe[ingrediente] = NaN`.  
En un **condicional** compruebo lo antes mencionado, si se cumple que es **NaN** devuelvo directamente **0**, puesto que no se va a poder completar ninguna receta.  
Si no se cumple, mediante el metodo `.push()` envío el resultado del ingrediente disponible **dividido** la cantidad de ingrediente necesario para una receta, lo cual me dará como resultado las veces que puedo ejecutar la receta con ese ingrediente.

Una vez que ya verifique y calcule cada ingrediente, cálculo mediante `Math.min()` el mínimo de todos los ingredientes, luego lo redondeo hacia abajo mediante `Math.floor()` y devuelvo ese valor, resultando el número de recetas que puedo realizar con mis ingredientes.

-   [Math.min()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Math/min)
-   [for...in](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/for...in)
-   [Math.floor()](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Math/floor)
-   [Spread syntax](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]