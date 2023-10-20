#7kyu 
___
Complete the function that accepts a string parameter, and reverses each word in the string. All spaces in the string should be retained.

Complete la función que acepta un parámetro de cadena y que invierte cada palabra de la cadena. Todos los espacios de la cadena deben ser conservados.

Examples

"This is an example!" ==> "sihT si na !elpmaxe"

"double spaces" ==> "elbuod secaps"

````js

function reverseWords(str) {
	
	// Almaceno en una variable donde divido el string en palabras
	
	let arreglo1 = str.split(' ');
	
	// Almaceno en una variable un array vacio
	
	let final = [];
	
	// En un bucle for itero las palabras almacenadas en la variable arreglo1
	
		for (let i = 0; i < arreglo1.length; i++) {
		
		// Almaceno en una variable la palabra dada vuelta y la almaceno en la
		// variable con el array vacio
		
		let elemento = arreglo1[i].split('').reverse().join('');
		
		final.push(elemento);
		
	}
	
	// uno las palabras contenidas en el array en un string
	
	return final.join(' ');

}

// Otras soluciones

function reverseWords(str) {
	
	// Devuelvo el str con los metodos split(" ") para separar las palabras luego map() para agarrar cada palabra para separar en letras y darlas vueltas y unirlas, y luego unir todo con join(" ")
	
	return str.split(' ').map(function (word) {
		return word.split('').reverse().join('');
	}).join(' ');

}

function reverseWords(str) {
	
	// Mas de lo mismo
	
	return str.split('').reverse().join('').split(' ').reverse().join(' ');

}
````

__________

[[Ejercicios JavaScript/Ejercicios|Ejercicios]]