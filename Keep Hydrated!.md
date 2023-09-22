A Nathan le encanta el ciclismo.  
  
Como Nathan sabe que es importante mantenerse hidratado, bebe 0,5 litros de agua por hora de pedaleo.  
  
Te dan el tiempo en horas y tienes que devolver el número de litros que beberá Nathan, redondeado al valor más pequeño.

## Ejemplo

```
time = 3 ----> litres = 1

time = 6.7---> litres = 3

time = 11.8--> litres = 5
```

## Link del problema

https://www.codewars.com/kata/582cb0224e56e068d800003c/train/javascript

## Mi solución

```js
function litres(time) {
  return Math.floor(Math.floor(time) * 0.5)
}
```

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]