#Easy 
___
Si quieres construir algo utilizando una Raspberry Pi, probablemente utilizarás resistencias. Para este ejercicio, necesitas saber dos cosas sobre ellas:  
  
- Cada resistencia tiene un valor de resistencia.  
- Las resistencias son pequeñas, tan pequeñas que si imprimieras el valor de la resistencia en ellas, sería difícil de leer.  

Para evitar este problema, los fabricantes imprimen bandas de colores en las resistencias para indicar su valor. Cada banda tiene una posición y un valor numérico.  
  
Las dos primeras bandas de una resistencia tienen un esquema de codificación sencillo: cada color corresponde a un único número. Por ejemplo, si imprimieran una banda marrón (valor 1) seguida de una verde (valor 5), se traduciría en el número 15.  
  
En este ejercicio vas a crear un programa útil para que no tengas que recordar los valores de las bandas. El programa tomará los nombres de los colores como entrada y dará como salida un número de dos dígitos, ¡incluso si la entrada tiene más de dos colores!  
  
Los colores de las bandas están codificados de la siguiente manera:  
  
- Negro: 0  
- Marrón: 1  
- Rojo: 2  
- Naranja 3  
- Amarillo 4  
- Verde 5  
- Azul: 6  
- Violeta: 7  
- Gris: 8  
- Blanco: 9  

Del ejemplo anterior: marrón-verde debería devolver 15 marrón-verde-violeta debería devolver 15 también, ignorando el tercer color.  
## Notas  

La entrada proporcionada será una matriz de nombres de colores y la salida será un número.
## Mi solución

```js
export const decodedValue = (colors) => {
  return +(COLORS[colors[0]] + COLORS[colors[1]])
};

export const COLORS = {"black":"0", "brown":"1", "red":"2", "orange":"3", "yellow":"4", "green":"5", "blue":"6", "violet":"7", "grey":"8", "white":"9"}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/resistor-color-duo