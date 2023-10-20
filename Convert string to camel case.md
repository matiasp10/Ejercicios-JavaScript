#6kyu
# Convertir cadena a camel case

Complete el método/función para que convierta las palabras delimitadas por guiones/guiones bajos en mayúsculas y minúsculas. La primera palabra de la salida debe ir en mayúsculas sólo si la palabra original iba en mayúsculas (lo que se conoce como Mayúsculas Camel Case, también conocido como Pascal case). Las palabras siguientes deben ir siempre en mayúsculas.

## Ejemplos

```js
`"the-stealth-warrior"` gets converted to `"theStealthWarrior"`

`"The_Stealth_Warrior"` gets converted to `"TheStealthWarrior"`

`"The_Stealth-Warrior"` gets converted to `"TheStealthWarrior"`
```

## Mi solución

```js
function toCamelCase(str) {
    let stack = [];
    let transformed = str.replaceAll("_", "-")
    let splitted = transformed.split("-")
    stack.push(splitted[0]);
    for (let i = 1; i < splitted.length; i++) {
      stack.push(splitted[i][0].toUpperCase() + splitted[i].substring(1));
  }
  return stack.join('');
}
```

[[JavaScript/Tipos de datos/String|String]]
[[String.prototype.toUpperCase()]]

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]