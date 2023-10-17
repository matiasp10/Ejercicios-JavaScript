#Learning 
___
## Instrucciones

Ozan está preparando una lista de reproducción para un viaje por carretera. No quiere escuchar la misma canción más de una vez, pero la lista de reproducción es tan larga que le cuesta recordar las canciones que ya ha añadido.  
  
La API del reproductor de música de Ozan sólo sabe trabajar con matrices, así que intenta escribir un código que utilice `Array.indexOf()` para comprobar la presencia de una pista antes de añadirla a la lista de reproducción. Por desgracia, su programa tarda demasiado en ejecutarse. Necesita tu ayuda.  
  
Al acudir en ayuda de Ozan, te sorprendes al descubrir que su lista de reproducción contiene medio millón de pistas. Tal vez conozcas otra estructura de datos que te permita manipular la lista de reproducción de forma más eficaz.
## 1. Eliminar pistas duplicadas  

Implementa la función `removeDuplicates`, que toma una lista de reproducción como parámetro y devuelve una nueva lista de reproducción en la que todas las pistas son únicas.

```js
const playlist = [
  'Court and Spark - Joni Mitchell',
  'Big Yellow Taxi - Joni Mitchell',
  'Court and Spark - Joni Mitchell',
];

removeDuplicates(playlist);
//=> ['Court and Spark - Joni Mitchell', 'Big Yellow Taxi - Joni Mitchell']
```
### Mi solución 

```js
export function removeDuplicates(playlist) {
  let set = new Set(playlist)
  return Array.from(set)
}
```
## 2. Comprobar si ya se ha añadido una pista  

Implementa la función `hasTrack`, que toma una lista de reproducción y una pista como parámetros y devuelve un booleano que indica si la lista de reproducción contiene la pista.

```js
const playlist = [
  'The Fashion Show - Grace Jones',
  'Dr. Funkenstein - Parliament',
];

hasTrack(playlist, 'Dr. Funkenstein - Parliament');
//=> true

hasTrack(playlist, 'Walking in the Rain - Grace Jones');
//=> false
```
### Mi solución 

```js
export function hasTrack(playlist, track) {
  let set = new Set(playlist)
  return set.has(track)
}
```
## 3. Añadir una pista  

Implementa la función `addTrack`, que toma una lista de reproducción y una pista como parámetros y devuelve una nueva lista de reproducción que incluye la pista.

```js
const playlist = ['Selma - Bijelo Dugme'];

addTrack(playlist, 'Atomic Dog - George Clinton');
//=> ['Selma - Bijelo Dugme', 'Atomic Dog - George Clinton']

addTrack(playlist, 'Selma - Bijelo Dugme');
//=> ['Selma - Bijelo Dugme', 'Atomic Dog - George Clinton']
```
### Mi solución 

```js
export function addTrack(playlist, track) {
  let set = new Set(playlist)
  set.add(track)
  return Array.from(set)
}
```
## 4. Eliminar una pista  

Implementa la función `deleteTrack`, que toma una lista de reproducción y una pista como parámetros y devuelve una nueva lista de reproducción que no incluye la pista.

```js
const playlist = [
  'The Treasure - Fra Lippo Lippi',
  'After the Fall - Klaus Nomi',
];

deleteTrack(playlist, 'The Treasure - Fra Lippo Lippi');
//=> ['After the Fall - Klaus Nomi']

deleteTrack(playlist, 'I Feel the Magic - Belinda Carlisle');
//=> ['After the Fall - Klaus Nomi']
```
### Mi solución 

```js
export function deleteTrack(playlist, track) {
  let set = new Set(playlist)
  set.delete(track)
  return Array.from(set)
}
```
## 5. Lista de artistas únicos  

Implementa la función `listArtists`, que toma una lista de reproducción como parámetro y devuelve la lista de artistas únicos de la lista. Tenga en cuenta que los nombres de las pistas tienen el formato `<CANCIÓN> - <ARTISTA>`.

```js
const playlist = [
  'All Mine - Portishead',
  'Sight to Behold - Devendra Banhart',
  'Sour Times - Portishead',
];

listArtists(playlist);
//=> ['Portishead', 'Devendra Banhart']
```
### Mi solución 

```js
export function listArtists(playlist) {
  let set = new Set()
  for(let track of playlist){
    let t = track.split(" - ")
    set.add(t[1])
  }
  return Array.from(set)
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/ozans-playlist