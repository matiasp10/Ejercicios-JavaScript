En esta kata crearás una función que toma una lista de enteros no negativos y cadenas y devuelve una nueva lista con las cadenas filtradas.

## Ejemplos

```js
filter_list([1,2,'a','b']) == [1,2]
filter_list([1,'a','b',0,15]) == [1,0,15]
filter_list([1,2,'aasf','1','123',123]) == [1,2,123]
```

## Link del problema

https://www.codewars.com/kata/53dbd5315a3c69eed20002dd/train/javascript

## Mi solución

```js
function filter_list(l) {
  let stack = [];
  for(let i = 0; i < l.length; i++){
    if (Number(l[i]) === l[i]){
      stack.push(l[i])
    }
  }
  return stack
}
```
