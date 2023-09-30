En esta pequeña tarea se te da una cadena de números separados por espacios, y tienes que devolver el número más alto y el más bajo.

### Ejemplos

```javascript
highAndLow("1 2 3 4 5");  // return "5 1"
highAndLow("1 2 -3 4 5"); // return "5 -3"
highAndLow("1 9 3 4 -5"); // return "9 -5"
```

### Notas

- Todos los números son Int32 válidos, no es necesario validarlos.  
- Siempre habrá al menos un número en la cadena de entrada.  
- La cadena de salida debe tener dos números separados por un espacio, y el número más alto es el primero.

## Link del problema

https://www.codewars.com/kata/554b4ac871d6813a03000035/train/javascript

## Mi solución

```js
function highAndLow(numbers){
  let nums = numbers.split(" ")
  nums = nums.sort((a,z)=>{
    return Number(a) - Number(z)
  })
  return `${nums[nums.length - 1]} ${nums[0]}`
}
```
