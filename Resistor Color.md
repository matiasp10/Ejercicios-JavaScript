#Easy 
___
## Instrucciones

Si quieres construir algo utilizando una Raspberry Pi, probablemente utilizarás resistencias. Para este ejercicio, necesitas saber dos cosas sobre ellas:  
  
- Cada resistencia tiene un valor de resistencia.  
- Las resistencias son pequeñas, tan pequeñas que si imprimieras el valor de la resistencia en ellas, sería difícil de leer.  

Para evitar este problema, los fabricantes imprimen bandas de colores en las resistencias para indicar su valor. Cada banda tiene una posición y un valor numérico.  
  
Las dos primeras bandas de una resistencia tienen un esquema de codificación sencillo: cada color corresponde a un único número.  
  
En este ejercicio vas a crear un programa útil para no tener que recordar los valores de las bandas.  
  
Estos colores se codifican de la siguiente manera:  
  
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

El objetivo de este ejercicio es crear un camino:  
  
- buscar el valor numérico asociado a una banda de color determinada.  
- enumerar los diferentes colores de las bandas.  

La mnemotecnia asigna los colores a los números que, cuando se almacenan en una matriz, se asignan a su índice en la matriz: Más Vale Que Sea Correcto O Sus Grandes Valores Se Equivocarán.  
  
Puede encontrar más información sobre la codificación de colores de las resistencias en el artículo de Wikipedia Código electrónico de colores.  
  
Aunque los nombres de los colores están en mayúsculas en la descripción, la función `colorCode` siempre se llamará con el equivalente en minúsculas, por ejemplo marrón en lugar de Marrón
## Mi solución

```js
export const colorCode = (colors) => {
  switch(colors){
    case "black":
      return 0
      break;
    case "brown":
      return 1
      break;
    case "red":
      return 2
      break;
    case "orange":
      return 3
      break;
    case "yellow":
      return 4
      break;
    case "green":
      return 5
      break;
    case "blue":
      return 6
      break;
    case "violet":
      return 7
      break;
    case "grey":
      return 8
      break;
    case "white":
      return 9
      break;
  }
};

export const COLORS = ["black", "brown", "red", "orange", "yellow", "green", "blue", "violet", "grey", "white"]
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/resistor-color