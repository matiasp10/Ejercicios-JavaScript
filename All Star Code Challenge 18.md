Crear una función que acepte una cadena y un único carácter, y devuelva un entero del recuento de ocurrencias que el 2º argumento se encuentra en el primero.  
  
Si no se encuentra ninguna ocurrencia, se devolverá un recuento de 0.

```js
("Hello", "o")  ==>  1
("Hello", "l")  ==>  2
("", "z")       ==>  0
```

```js
str_count("Hello", 'o'); // returns 1
str_count("Hello", 'l'); // returns 2
str_count("", 'z'); // returns 0
```

### Notas

- El primer argumento puede ser una cadena vacía  
- En los idiomas que no tienen un tipo de datos de caracteres distinto, el segundo argumento será una cadena de longitud 1

## Link del problema

https://www.codewars.com/kata/5865918c6b569962950002a1/train/javascript
## Mi solución

```js
function strCount(str, letter){  
  return str.split("").filter((word)=> word === letter).join("").length
}
```
