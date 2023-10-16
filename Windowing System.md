#Learning 
____
## Instrucciones 

En este ejercicio, simularás un sistema informático basado en ventanas. Creará algunas ventanas que pueden ser movidas y redimensionadas. La siguiente imagen es representativa de los valores con los que trabajarás a continuación.

```
                  <--------------------- screenSize.width --------------------->

       ^          ╔════════════════════════════════════════════════════════════╗
       |          ║                                                            ║
       |          ║          position.x,_                                      ║
       |          ║          position.y  \                                     ║
       |          ║                       \<----- size.width ----->            ║
       |          ║                 ^      *──────────────────────┐            ║
       |          ║                 |      │        title         │            ║
       |          ║                 |      ├──────────────────────┤            ║
screenSize.height ║                 |      │                      │            ║
       |          ║            size.height │                      │            ║
       |          ║                 |      │       contents       │            ║
       |          ║                 |      │                      │            ║
       |          ║                 |      │                      │            ║
       |          ║                 v      └──────────────────────┘            ║
       |          ║                                                            ║
       |          ║                                                            ║
       v          ╚════════════════════════════════════════════════════════════╝
```

Para practicar tu amplio abanico de conocimientos de JavaScript, intenta resolver las tareas 1 y 2 con la sintaxis de prototipos y el resto de tareas con la sintaxis de clases.
## 1. Definir Size para almacenar las dimensiones de la ventana  

Defina una clase (función constructora) llamada `Size`. Debe tener dos campos `width` y `height` que almacenen las dimensiones actuales de la ventana. La función constructora debe aceptar valores iniciales para estos campos. La anchura se proporciona como primer parámetro, la altura como segundo. La anchura y la altura por defecto deben ser `80` y `60`, respectivamente.  
  
Además, defina un método `resize(newWidth, newHeight)` que tome una nueva anchura y altura como parámetros y cambie los campos para reflejar el nuevo tamaño.

```js
const size = new Size(1080, 764);
size.width;
// => 1080
size.height;
// => 764

size.resize(1920, 1080);
size.width;
// => 1920
size.height;
// => 1080
```
### Mi solución

```js
export function Size(width = 80, height = 60) {
  this.width = width
  this.height = height
  this.resize = function(newWidth, newHeight) {
    this.width = newWidth
    this.height = newHeight
  }
}
```
## 2. Definir Position para almacenar la posición de una ventana  

Define una clase (función constructora) llamada `Position` con dos campos, `x` e `y` que almacenan la posición horizontal y vertical actual, respectivamente, de la esquina superior izquierda de la ventana. La función constructora debe aceptar valores iniciales para estos campos. El valor para `x` se proporciona como primer parámetro, el valor para `y` como segundo. El valor por defecto debe ser `0` para ambos campos.  
  
La posición `(0, 0)` es la esquina superior izquierda de la pantalla, con valores de `x` que aumentan a medida que se desplaza hacia la derecha y valores de `y` que aumentan a medida que se desplaza hacia abajo.  
  
Define también un método `move(newX, newY)` que tome los nuevos parámetros x e y y cambie las propiedades para reflejar la nueva posición.

```js
const point = new Position();
point.x;
// => 0
point.y;
// => 0

point.move(100, 200);
point.x;
// => 100
point.y;
// => 200
```
### Mi solución

```js
export function Position(x = 0, y = 0){
  this.x = x
  this.y = y
  this.move = function(newX, newY) {
    this.x = newX
    this.y = newY
  }
}
```
## 3. Definir una clase ProgramWindow  

Defina una clase `ProgramWindow` con los siguientes campos:  
  
- `screenSize`: contiene un valor fijo de tipo Size con anchura 800 y altura 600  
- `size` : contiene un valor de tipo Size, el valor inicial es el valor por defecto de la instancia Size  
- `position` : contiene un valor de tipo Position, el valor inicial es el valor por defecto de la instancia Position  

Cuando la ventana se abre (se crea), siempre tiene el tamaño y la posición por defecto al principio.

```js
const programWindow = new ProgramWindow();
programWindow.screenSize.width;
// => 800

// Similar for the other fields.
```

>[!note] Nota al margen
>El nombre ProgramWindow se utiliza en lugar de Window para diferenciar la clase de la clase Window incorporada que existe en los entornos de navegador.
### Mi solución

```js
export class ProgramWindow{
  constructor (){
    this.screenSize = new Size(800, 600)
    this.size = new Size()
    this.position = new Position()
	}
}
```
## 4. Añadir un método para redimensionar la ventana  

La clase `ProgramWindow` debería incluir un método `resize`. Debería aceptar un parámetro de tipo `Size` como entrada e intentar redimensionar la ventana al tamaño especificado.  
  
Sin embargo, el nuevo tamaño no puede exceder ciertos límites.  
  
- La altura o anchura mínima permitida es 1. Las alturas o anchuras solicitadas inferiores a 1 se recortarán a 1.  
- La altura y anchura máximas dependen de la posición actual de la ventana; los bordes de la ventana no pueden sobrepasar los bordes de la pantalla. Los valores superiores a estos límites se recortarán al tamaño más grande que puedan tomar. Por ejemplo, si la posición de la ventana es `x` = 400, `y` = 300 y se solicita un redimensionamiento a `height` = 400, `width` = 300, entonces la ventana se redimensionará a `height` = 300, `width` = 300 ya que la pantalla no es lo suficientemente grande en la dirección `y` para acomodar completamente la solicitud.

```js
const programWindow = new ProgramWindow();

const newSize = new Size(600, 400);
programWindow.resize(newSize);
programWindow.size.width;
// => 600
programWindow.size.height;
// => 400
```
### Mi solución

```js
export class ProgramWindow{
  constructor (){
    this.screenSize = new Size(800, 600)
    this.size = new Size()
    this.position = new Position()
  }

  resize(newSize){
    const maxWidth = this.screenSize.width - this.position.x
    const maxHeight = this.screenSize.height - this.position.y

    const newWidth = Math.max(1, Math.min(newSize.width, maxWidth))
    const newHeight = Math.max(1, Math.min(newSize.height, maxHeight))

    this.size.resize(newWidth, newHeight)
  }
}
```
## 5. Añadir un método para mover la ventana  

Además de la funcionalidad de redimensionar, la clase `ProgramWindow` también debería incluir un método `move`. Debería aceptar un parámetro de tipo `Position` como entrada. El método `move` es similar a `resize` sin embargo, este método ajusta la posición de la ventana al valor solicitado, en lugar del tamaño.  
  
Al igual que con `resize`, la nueva posición no puede exceder ciertos límites.  
  
- La posición más pequeña es 0 tanto para `x` como para `y`.  
- La posición máxima en cualquier dirección depende del tamaño actual de la ventana. Los bordes no pueden sobrepasar los bordes de la pantalla. Los valores superiores a estos límites se recortarán al tamaño más grande que puedan tomar. Por ejemplo, si el tamaño de la ventana es `x` = 250, `y` = 100 y se solicita un movimiento a `x` = 600, `y` = 200, la ventana se moverá a `x` = 550, `y` = 200, ya que la pantalla no es lo suficientemente grande en la dirección x para acomodar completamente la solicitud.

```js
const programWindow = new ProgramWindow();

const newPosition = new Position(50, 100);
programWindow.move(newPosition);
programWindow.position.x;
// => 50
programWindow.position.y;
// => 100
```
### Mi solución

```js
export class ProgramWindow{
  constructor (){
    this.screenSize = new Size(800, 600)
    this.size = new Size()
    this.position = new Position()
  }

  resize(newSize){
    const maxWidth = this.screenSize.width - this.position.x
    const maxHeight = this.screenSize.height - this.position.y

    const newWidth = Math.max(1, Math.min(newSize.width, maxWidth))
    const newHeight = Math.max(1, Math.min(newSize.height, maxHeight))

    this.size.resize(newWidth, newHeight)
  }
  move(newPosition){
    const maxX = this.screenSize.width - this.size.width
    const maxY = this.screenSize.height - this.size.height

    const newX = Math.max(0, Math.min(newPosition.x, maxX))
    const newY = Math.max(0, Math.min(newPosition.y, maxY))

    this.position.move(newX, newY)
  }
}
```
## 6. Cambiar una ventana de programa  

Implemente una función `changeWindow` que acepte una instancia de `ProgramWindow` como entrada y cambie la ventana al tamaño y posición especificados. La función debe devolver la instancia de `ProgramWindow` que se pasó después de aplicar los cambios.  
  
La ventana debe tener una anchura de 400, una altura de 300 y estar posicionada en x = 100, y = 150.

```js
const programWindow = new ProgramWindow();
changeWindow(programWindow);
programWindow.size.width;
// => 400

// Similar for the other fields.
```
### Mi solución

```js
export function changeWindow(programWindow) {
  programWindow.move(new Position())
  programWindow.resize(new Size(400,300))
  programWindow.move(new Position(100,150))
  return programWindow
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/windowing-system