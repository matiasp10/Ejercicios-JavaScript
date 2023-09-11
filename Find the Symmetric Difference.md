# Hallar la diferencia simétrica

El término matemático diferencia simétrica (△ o ⊕) de dos conjuntos es el conjunto de elementos que están en cualquiera de los dos conjuntos pero no en ambos. Por ejemplo, para los conjuntos A = {1, 2, 3} y B = {2, 3, 4}, A △ B = {1, 4}.

La diferencia simétrica es una operación binaria, lo que significa que sólo opera sobre dos elementos. Así que para evaluar una expresión que implica diferencias simétricas entre tres elementos (A △ B △ C), debe completar una operación a la vez. Así, para los conjuntos A y B anteriores, y C = {2, 3}, A △ B △ C = (A △ B) △ C = {1, 4} △ {2, 3} = {1, 2, 3, 4}.

Cree una función que tome dos o más matrices y devuelva una matriz con su diferencia simétrica. La matriz devuelta debe contener sólo valores únicos (sin duplicados).

## Solución 1

```js
function sym() {
  let args = [];
  for (var i = 0; i < arguments.length; i++) {
    args.push(arguments[i]);
  }

  function symDiff(arrayOne, arrayTwo) {
    let result = [];

    arrayOne.forEach(function(item) {
      if (arrayTwo.indexOf(item) < 0 && result.indexOf(item) < 0) {
        result.push(item);
      }
    });

    arrayTwo.forEach(function(item) {
      if (arrayOne.indexOf(item) < 0 && result.indexOf(item) < 0) {
        result.push(item);
      }
    });

    return result;
  }

  return args.reduce(symDiff);
}
```

### Explicación 

```js
var args = [];
for (var i = 0; i < arguments.length; i++) {
	args.push(arguments[i]);
}
```

Recorro con un bucle [[For]] los argumentos (arbitrarios) de la función y voy añadiéndolos (por el método [[Array.prototype.push()|push()]]) a una variable `args`.

```js
function symDiff(arrayOne, arrayTwo) {
	let result = [];

arrayOne.forEach(function(item) {
	if (arrayTwo.indexOf(item) < 0 && result.indexOf(item) < 0) {
	    result.push(item);
      }
});

arrayTwo.forEach(function(item) {
	if (arrayOne.indexOf(item) < 0 && result.indexOf(item) < 0) {
        result.push(item);
      }
});

	return result;
}
```

La función `symDiff` encuentra la diferencia simétrica entre dos conjuntos. Se utiliza como función de callback para el método reduce() llamado sobre `args`.

En la variable `result` vacía se añadirán los números que no se encuentran en el otro array.

```js
arrayOne.forEach(function(item) {
	if (arrayTwo.indexOf(item) < 0 && result.indexOf(item) < 0) {
	    result.push(item);
      }
});

arrayTwo.forEach(function(item) {
	if (arrayOne.indexOf(item) < 0 && result.indexOf(item) < 0) {
        result.push(item);
      }
});
```

Se utiliza el método [[Array.prototype.forEach()|forEach()]] para recorrer cada elemento de los dos arrays, y mediante un condicional [[if]] hacer la siguiente comprobación: 

```js
arrayTwo.indexOf(item) < 0 && result.indexOf(item) < 0
```

Mediante el método [[Array.prototype.indexOf()|indexOf()]] comprobamos si no se encuentra en el otro array y además comprobamos que no este en la variable `result`.

y por ultimo retornamos el valor de `result` que contendrá la diferencia simétrica entre esos dos conjuntos.

Como retorno de la función `sym()` vamos a devolver 

```js
return args.reduce(symDiff);
```

Ejecuta el método [[Array.prototype.reduce()|reduce()]] sobre `args` utilizando de callback `symDiff()`.

## Solución 2

```js
function sym() {

  let args = Array.prototype.slice.call(arguments);

  let getDiff = function(arr1, arr2) {
    function filterFunction(arr1, arr2) {
      return arr1.filter(function(item) {
        return arr2.indexOf(item) === -1;
      });
    }

    return filterFunction(arr1, arr2).concat(filterFunction(arr2, arr1));
  };

  let summary = args.reduce(getDiff, []);

  let unique = summary.filter(function(elem, index, self) {
    return index === self.indexOf(elem);
  });
  return unique;
}
```

### Explicación 

```js
let args = Array.prototype.slice.call(arguments);
```

Convierte el objeto `arguments` de la función en un array.

```js
let getDiff = function(arr1, arr2) {
	function filterFunction(arr1, arr2) {
	    return arr1.filter(function(item) {
		    return arr2.indexOf(item) === -1;
	});
}

	return filterFunction(arr1, arr2).concat(filterFunction(arr2, arr1));
};
```




```js
const diff = (arr1, arr2) => [
  ...arr1.filter(e => !arr2.includes(e)),
  ...arr2.filter(e => !arr1.includes(e))
];

const sym = (...args) => [...new Set(args.reduce(diff))];
```

