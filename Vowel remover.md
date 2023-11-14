#8kyu 
___
Crear una función llamada atajo para eliminar las vocales minúsculas (a, e, i, o, u ) en una cadena dada.
## Ejemplo

```python
"hello"     -->  "hll"
"codewars"  -->  "cdwrs"
"goodbye"   -->  "gdby"
"HELLO"     -->  "HELLO"
```

- No te preocupes por las vocales mayúsculas
- No se considera una vocal para este kata
## Link del problema

https://www.codewars.com/kata/5547929140907378f9000039/train/javascript
## Mi solución

```js
function shortcut (string) {
  let regex = /([aeiou])/g
  return string.replaceAll(regex, "") 
}
```