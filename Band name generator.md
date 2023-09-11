#7kyu

# Generador de nombres de grupos musicales

Mi amiga quiere un nuevo nombre para su banda. A ella le gustan las bandas que usan la fórmula "The" + un sustantivo con la primera letra en mayúscula, por ejemplo:

```js
"dolphin" -> "The Dolphin"
```

Sin embargo, cuando un sustantivo EMPIEZA y TERMINA con la misma letra, le gusta repetir el sustantivo dos veces y unirlas con la primera y la última letra, combinadas en una palabra (SIN "The" delante), así:

```js
"alaska" -> "Alaskalaska"
```

Completa la función que toma un nombre como cadena, y devuelve el nombre de su grupo preferido escrito como cadena.

## Mi solución

```js
function bandNameGenerator(str) {
  if(str[0] === str[str.length - 1]){
    return str[0].toUpperCase() + str.slice(1, str.length)+ str.slice(1, str.length)
  } else {
    return "The" + " " + str[0].toUpperCase() + str.slice(1, str.length)
  }
}
```

[[JavaScript/Tipos de datos/String|String]]
[[String.prototype.toUpperCase()]]
[[String.prototype.slice()]]
