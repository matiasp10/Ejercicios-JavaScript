#5kyu
____
# 1's, 0's y comodines

Se le da una cadena que contiene 0's, 1's y uno o más '?', donde ? es un comodín que puede ser 0 o 1.

Devuelve un array que contiene todas las posibilidades a las que se puede llegar sustituyendo la ? por un valor.

## Ejemplos

```js
'101?' -> ['1010', '1011']

'1?1?' -> ['1010', '1110', '1011', '1111']
```

> [!note] Notas
> - No te preocupes por ordenar la salida.
> - Tu cadena nunca estará vacía.
## Link del problema

https://www.codewars.com/kata/588f3e0dfa74475a2600002a
## Mi solución

```js
function possibilities(str) {
  
  let arr = []

  const stack = [];

  stack.push(str);
  
  let index;
  
  while(stack.length){
    let curr = stack.pop();
    if((index = curr.indexOf('?')) !== -1){
        for(let c = 0; c <= 1; c++){
          curr = curr.substring(0, index) + c + curr.substring(index+1);
          stack.push(curr);
        }
    }else{
      arr.push(curr)
    }
  }
  return arr
};
```

- [[Array]]
- 

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]