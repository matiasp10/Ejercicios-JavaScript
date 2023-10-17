#Learning 
___
## Instrucciones

Elena es la nueva responsable de calidad de una fábrica de periódicos. Como acaba de llegar a la empresa, ha decidido revisar algunos de los procesos de la fábrica para ver qué se puede mejorar. Ha descubierto que los técnicos realizan muchos controles de calidad a mano. Ve que hay una buena oportunidad para la automatización y le pide a usted, desarrollador autónomo, que desarrolle un programa informático para controlar algunas de las máquinas.
## 1. Controlar el nivel de humedad de la sala  

Tu primera misión es escribir un programa informático para controlar el nivel de humedad de la sala de producción. Ya existe un sensor conectado al software de la empresa que devuelve periódicamente el porcentaje de humedad de la sala.  
  
Tienes que implementar una función en el software que lance un error si el porcentaje de humedad es demasiado alto. La función debe llamarse `checkHumidityLevel` y tomar el porcentaje de humedad como parámetro.  
  
Debe lanzar un error (el mensaje no es importante) si el porcentaje supera el 70%.

```js
checkHumidityLevel(60);
// => undefined
checkHumidityLevel(100); 
// Throws an error
```
### Mi solución 

```js
export function checkHumidityLevel(humidityPercentage) {
  if(humidityPercentage > 70) throw new Error()
}
```
## 2. Detectar el sobrecalentamiento  

Elena está muy satisfecha con tu primer encargo y te pide que te ocupes de la supervisión de la temperatura de las máquinas. Mientras charla con un técnico, Greg, le dice que si la temperatura de una máquina supera los 500 °C, los técnicos empiezan a preocuparse por el sobrecalentamiento.  
  
La máquina está equipada con un sensor que mide su temperatura interna. Debes saber que el sensor es muy sensible y a menudo se rompe. En ese caso, los técnicos tendrán que cambiarlo.  
  
Tu trabajo es implementar una función `reportOverheating` que tome la temperatura como parámetro y lance un error si el sensor se rompe o si la máquina empieza a sobrecalentarse. Sabiendo que más tarde necesitarás reaccionar de forma diferente dependiendo del error, necesitas un mecanismo para diferenciar los dos tipos de errores. Podrías confiar en los mensajes de error, pero esto haría que tu código fuera frágil ya que se rompería si el mensaje se actualiza. Así que para poder hacerlo correctamente, lanzarás instancias de diferentes clases de error.  
  
Si el sensor está roto, la temperatura será `null`. En este caso, deberías lanzar un `ArgumentError`.  
Cuando todo funciona, si la temperatura excede los 500°C, deberías lanzar un `OverheatingError`. Esta clase de error se instanciará con un argumento de temperatura. Asegúrese de que el `OverheatingError` que lanza tiene una propiedad de temperatura asociada.

```js
reportOverheating(null);
// Throws an ArgumentError
reportOverheating(800); 
// Throws an OverheatingError
```
### Mi solución 

```js
export function reportOverheating(temperature) {
  if(temperature === null) throw new ArgumentError()
  if(temperature > 500) throw new OverheatingError(temperature)
}
```
## 3. Supervisar la máquina  

Ahora que tu máquina puede detectar errores, implementarás una función que reaccione a esos errores de diferentes maneras :  
  
- Si el sensor está roto, deberá avisar a un técnico  
- Si la temperatura es demasiado alta, apagará la máquina si la temperatura supera los 600°C o encenderá una luz de advertencia si es inferior.  
- Si se produce otro error, la volverá a lanzar.  

Implementa una función `monitorTheMachine` que toma un argumento `actions`.  
  
`actions` es un objeto que tiene 4 propiedades :  
  
- `check` es una función que, al ser llamada, comprueba la temperatura de la máquina. Puede lanzar varios errores  
- `alertDeadSensor` es una función que, al ser llamada, alerta al técnico de que el sensor de temperatura está muerto.  
- `alertOverheating` es una función que, al ser llamada, encenderá una luz de aviso en la máquina.  
- `shutdown` es una función que, al ser llamada, apagará la máquina.  
  
La función `monitorTheMachine` debe llamar a `check()`. Si pasa, la función no debería devolver nada. Sin embargo, puede lanzar un error. Cuando esto sucede, debe, dependiendo del error:  
  
- `ArgumentError`: cuando esto ocurre, llamar a la función `alertDeadSensor`.  
- `OverheatingError`: cuando esto ocurra, si la temperatura es inferior a 600 °C, llame a la función `alertOverheating` para encender la luz de aviso. Si la temperatura supera los 600 °C, la situación es crítica, llame a la función `shutdown`.  
- Cualquier otra cosa: cuando esto ocurra, vuelva a lanzar el error.

```js
monitorTheMachine({
  check,
  alertDeadSensor,
  alertOverheating,
  shutdown,
});
```
### Mi solución 

```js
export function monitorTheMachine(actions) {
  try {
    actions.check()
  } catch (error) {
    if(error instanceof ArgumentError){
      actions.alertDeadSensor()
    } else if(error instanceof OverheatingError){
      if(error.temperature < 600) actions.alertOverheating()
      if(error.temperature > 600) actions.shutdown()
      
    } else {
      throw error
    }
  }
}
```
## Link del problema

https://exercism.org/tracks/javascript/exercises/factory-sensors