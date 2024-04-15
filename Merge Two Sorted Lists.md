#Easy 
____
Se dan las cabezas de dos listas enlazadas ordenadas `lista1` y `lista2`.  
  
Fusione las dos listas en una lista ordenada. La lista debe hacerse empalmando los nodos de las dos primeras listas.  
  
Devuelve la cabeza de la lista enlazada combinada.
## Ejemplos

### 1
![[Pasted image 20231022191922.png|center]]

```js
Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]
```
### 2

```js
Input: list1 = [], list2 = []
Output: []
```
### 3

```js
Input: list1 = [], list2 = [0]
Output: [0]
```
## Restricciones:  
  
- El número de nodos en ambas listas está en el rango `[0, 50]`.  
- -100 <= `Node.val` <= 100  
- Tanto la `lista1` como la `lista2` están ordenadas en orden no decreciente.