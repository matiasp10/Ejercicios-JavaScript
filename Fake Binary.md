#8kyu

# Binario falso

Dada una cadena de dígitos, debe sustituir cualquier dígito inferior a 5 por '0' y cualquier dígito igual o superior a 5 por '1'. Devuelve la cadena resultante.

> [!note] Nota
> La entrada nunca será una cadena vacía

## Link al problema

https://www.codewars.com/kata/57eae65a4321032ce000002d

## Mi solución 

```js
function fakeBin(x){
  let nums = x.split("")
  let arr = []
  for(let num of nums){
    if(+num < 5){
      arr.push(0)
    } else {
      arr.push(1)
    }
  }
  return arr.join("")
}
```

- [[Array]]

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]