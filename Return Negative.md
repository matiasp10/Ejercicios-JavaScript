# Devolución Negativa

En esta sencilla tarea te dan un número y tienes que hacerlo negativo. Pero, ¿quizá el número ya es negativo?

## Notas

-   El número **puede ser ya negativo**, en cuyo caso no es necesario ningún cambio.
-   El **cero** (0) **no se comprueba para ningún signo específico**. Los ceros negativos no tienen sentido matemático.
    

## Ejemplo

```js
makeNegative(1);    // return -1
makeNegative(-5);   // return -5
makeNegative(0);    // return 0
makeNegative(0.12); // return -0.12
```

## Link del problema

[Problema](https://www.codewars.com/kata/55685cd7ad70877c23000102/train/javascript)

## Mi solución

```js
function makeNegative(num) {
// Simplemente con un condicional verifico si el numero es igual o menor a 0 devuelvo el mismo numero, de lo contrario devuelvo el numero 
  if(num <= 0){
    return num
  } else {
    return -num
  }
}
```

-   [Number](https://es.javascript.info/number)
-   [If ... else](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/if...else)