#6kyu 

# Construir torre

Construir una torre en forma de pirámide, como una matriz/lista de cadenas, dado un número entero positivo de pisos. Un bloque de torre se representa con el carácter "`*`".

Por ejemplo, una torre de 3 plantas tiene este aspecto:

```js
[
  "  *  ",
  " *** ", 
  "*****"
]
```

Y una torre de 6 plantas tiene este aspecto:

```js
[
  "     *     ", 
  "    ***    ", 
  "   *****   ", 
  "  *******  ", 
  " ********* ", 
  "***********"
]
```

## Link del problema

https://www.codewars.com/kata/576757b1df89ecf5bd00073b

## Mi solución

```js
function towerBuilder(nFloors) {
  
  let torre = []
  for(let i = 0; i < nFloors; i++){
    torre.push(" ".repeat(nFloors - i - 1) + "*".repeat((i*2) + 1) + " ".repeat(nFloors - i - 1))
  }
  return torre
  }
```

- [[Array]]