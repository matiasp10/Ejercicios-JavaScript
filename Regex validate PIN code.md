#7kyu 
___
Los cajeros automáticos permiten códigos PIN de 4 ó 6 dígitos y los códigos PIN no pueden contener más que exactamente 4 dígitos o exactamente 6 dígitos.  
  
Si a la función se le pasa una cadena PIN válida, devuelve true, en caso contrario devuelve false.
## Ejemplos

```js
"1234"   -->  true
"12345"  -->  false
"a234"   -->  false
```
## Mi solución

Forma corta con el operador ternario

```js
function validatePIN (pin) {
  return pin.match(/\D/) ? false : pin.length === 4 || pin.length === 6 ? true : false 
}
```

Forma larga con condicionales `if`

```js
function validatePIN(pin){
  if (pin.match(/\D/)){
    return false
  } else {
    if(pin.length === 4 || pin.length === 6){
      return true
    } else {
      return false
    }
  }
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]