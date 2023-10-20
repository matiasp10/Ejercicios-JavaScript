#7kyu 
___
Esta vez ni historia ni teoría. Los ejemplos a continuación le muestran cómo escribir acumulación de funciones:

## Ejemplos

```js
accum("abcd") -> "A-Bb-Ccc-Dddd"
accum("RqaEzty") -> "R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy"
accum("cwAt") -> "C-Ww-Aaa-Tttt"
```

## Link del problema

https://www.codewars.com/kata/5667e8f4e3f572a8f2000039/train/javascript

## Mi solución

```js
function accum(s) {
  let mumbling = []
	for(let i = 0; i < s.length; i++){
    mumbling.push(s[i].toUpperCase() + s[i].repeat(i).toLowerCase())
  }
  return mumbling.join("-")
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]