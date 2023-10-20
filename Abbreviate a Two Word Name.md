#8kyu 
____
# Abreviar un nombre de dos palabras

Escribe una función para convertir un nombre en iniciales. Esta kata toma estrictamente dos palabras con un espacio entre ellas.

La salida debe ser dos letras mayúsculas con un punto separándolas.

## Ejemplo

```js
"Sam Harris" => "S.H"
"patrick feeney" => "P.F"
```

## Link del problema

[Problema](https://www.codewars.com/kata/57eadb7ecd143f4c9c0000a3/train/javascript)

## Mi solución

```js
function abbrevName(name) {
  // Inicializo una variable donde divido las palabras por el " " espacio en blanco.
  let splitedName = name.split(' ');
  // Devuelvo la primer palabra de la primer palabra + un punto "." + la primer palabra de la segunda palabra.
  // agrego el metodo .toUpperCase() ya que las iniciales deben ser siempre en mayusculas.
  return (
    splitedName[0][0].toUpperCase() + '.' + splitedName[1][0].toUpperCase()
  );
}
```

-   [.split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
-   [.toUpperCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase)

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]