Given a random non-negative number, you have to return the digits of this number within an array in reverse order.

Dado un número aleatorio no negativo, hay que devolver los dígitos de este número dentro de una matriz en orden inverso.

Example:
348597 => [7,9,5,8,4,3]

###### Mi solucion:
````js
function digitize(n) {
	
	// Devuelvo el numero con los metodos toString() - convierte los numberos en un string - split("") - separa el string en un arreglo separando cada palabra - reverse() - revierte el orden del arreglo - map((a)=> parseInt(a)) - para pasar a numberos cada string dentro del arreglo
	
	return n.toString().split('').reverse().map((a) => parseInt(a));
}

````

###### Otras soluciones:

````js
// Utilizando el metodo String() para convertir el numbero en un string

function digitize(n) {
	return String(n).split('').map(Number).reverse();
}

// Utilizando la concatenacion para convertir el numbero en un string

function digitize(n) {
	return (n + '').split('').map(Number).reverse();
}

// Crea un Array con el numbero convertido a string

function digitize(n) {
	return Array.from(String(n), Number).reverse();
}
````

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]