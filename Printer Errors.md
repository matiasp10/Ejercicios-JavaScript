#7kyu 
___
En una fábrica, un impresor imprime etiquetas para cajas. Para un tipo de cajas, el impresor tiene que utilizar colores que, en aras de la simplicidad, se nombran con letras de la `A a la M`.  
  
Los colores utilizados por la impresora se registran en una cadena de control. Por ejemplo, una "buena" cadena de control sería `aaabbbbhaijjjm`, que significa que la impresora utilizó tres veces el color a, cuatro veces el color b, una vez el color h y luego una vez el color a...  
  
A veces hay problemas: falta de colores, mal funcionamiento técnico y se produce una cadena de control "mala", por ejemplo `aaaxbbbbyyhwawiwjjjwwm` con letras que no van de la a `A la M`.  
  
Tienes que escribir una función `printer_error` que dada una cadena devolverá la tasa de error de la impresora como una cadena que representa un racional cuyo numerador es el número de errores y el denominador la longitud de la cadena de control. No reduzcas esta fracción a una expresión más simple.  
  
La cadena tiene una longitud mayor o igual a uno y sólo contiene letras de la `a` a la `z`.

## Ejemplos

```js
s="aaabbbbhaijjjm"
printer_error(s) => "0/14"

s="aaaxbbbbyyhwawiwjjjwwm"
printer_error(s) => "8/22"
```

## Link del problema

https://www.codewars.com/kata/56541980fa08ab47a0000040/train/javascript

## Mi solución

```js
function printerError(s) {
  let letras = s.split('');
  let errores = 0;
  for (let i = 0; i < letras.length; i++) {
    if (letras[i] > 'm') {
      errores += 1;
    }
  }
  return errores + '/' + letras.length;
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]