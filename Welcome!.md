#8kyu 
___
El BA de su empresa ha informado a marketing de que su sitio web tiene una gran audiencia en Escandinavia y los países vecinos. Marketing cree que sería estupendo dar la bienvenida a los visitantes en su propio idioma. Por suerte, ya utilizáis una API que detecta la ubicación del usuario, así que es fácil.

- Piensa en una forma de almacenar los idiomas como base de datos. ¡Los idiomas se enumeran a continuación para que pueda copiar y pegar!  
- Escribe una función 'welcome' que tome un parámetro 'language', con un tipo String, y devuelva un saludo - si lo tienes en tu base de datos. Si el idioma no está en la base de datos, o en caso de que la entrada no sea válida, debería devolver el saludo en inglés.

## Base de datos

```json
[ 
("english", "Welcome")
, ("czech", "Vitejte")
, ("danish", "Velkomst")
, ("dutch", "Welkom")
, ("estonian", "Tere tulemast")
, ("finnish", "Tervetuloa")
, ("flemish", "Welgekomen")
, ("french", "Bienvenue")
, ("german", "Willkommen")
, ("irish", "Failte")
, ("italian", "Benvenuto")
, ("latvian", "Gaidits")
, ("lithuanian", "Laukiamas")
, ("polish", "Witamy")
, ("spanish", "Bienvenido")
, ("swedish", "Valkommen")
, ("welsh", "Croeso")
]
```

## Link del problema

https://www.codewars.com/kata/577ff15ad648a14b780000e7/train/javascript

## Mi solución

```js
function greet(language) {
  let db = {
  "english": "Welcome"
, "czech":"Vitejte"
, "danish": "Velkomst"
, "dutch":"Welkom"
, "estonian": "Tere tulemast"
, "finnish":"Tervetuloa"
, "flemish": "Welgekomen"
, "french": "Bienvenue"
, "german": "Willkommen"
, "irish":"Failte"
, "italian": "Benvenuto"
,"latvian": "Gaidits"
, "lithuanian": "Laukiamas"
, "polish": "Witamy"
, "spanish": "Bienvenido"
, "swedish": "Valkommen"
, "welsh": "Croeso"
, "IP_ADDRESS_INVALID": "Welcome"
, "IP_ADDRESS_NOT_FOUND": "Welcome"
, "IP_ADDRESS_REQUIRED": "Welcome"
  }
  return db[language]
}
```
