---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo, llama3-70b-8192
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-07T07:43:18.747Z
modified: 2024-05-13T20:10:04.584Z
supervisado: 2024-05-03T21:33:52.679Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 5
nav_primary: 
nav_secondary: 
tags:
---
# Carga y gestión de imágenes y texturas (PixiJS) 🔴②

[[Aprender sobre PixiJS ⚫①]]

En el contexto de aprender PixiJS, la carga y gestión de imágenes y texturas es un aspecto fundamental para crear contenido visual en tus aplicaciones o juegos. PixiJS proporciona una manera fácil y eficiente de cargar y manejar imágenes y texturas.

## Cargar una Imagen

Para cargar una imagen en PixiJS, puedes utilizar la clase `PIXI.Loader`. A continuación, te presento un ejemplo básico:

```javascript
// Crear un cargador
const loader = PIXI.Loader.shared;

// Agregar la imagen que deseas cargar
loader.add('nombre', 'ruta/a/la/imagen.png');

// Escuchar eventos de carga
loader.onProgress.add((loader, recurso) => {
  console.log(`Cargando ${recurso.url}`);
  console.log(`Progreso: ${loader.progress}%`);
});

loader.onComplete.add(() => {
  console.log('¡Carga completa!');
  // Una vez que la carga esté completa, puedes usar la imagen
  const sprite = PIXI.Sprite.from('nombre');
  app.stage.addChild(sprite); // Añadir el sprite al escenario
});

// Comenzar la carga
loader.load();
```

## Usar una Textura

Una vez que la imagen esté cargada, puedes usarla para crear texturas. A continuación, te presento un ejemplo de cómo crear una textura y un sprite:

```javascript
// Crear una textura a partir de la imagen cargada
const texture = PIXI.Texture.from('nombre');

// Crear un sprite usando la textura
const sprite = new PIXI.Sprite(texture);

// Añadir el sprite al escenario
app.stage.addChild(sprite);
```

## Gestión de Múltiples Imágenes

Si necesitas cargar múltiples imágenes, simplemente repite el proceso de agregar imágenes al cargador y usa las texturas correspondientes donde sea necesario.

## Gestión de Texturas Atlas


En aplicaciones más complejas, a menudo se utilizan texturas atlas, que son imágenes que contienen múltiples texturas individuales. PixiJS tiene soporte incorporado para texturas atlas, lo que permite cargar y usar múltiples texturas desde un solo archivo.

```javascript
// Cargar un atlas
loader.add('atlas', 'ruta/al/atlas.json');

loader.onComplete.add(() => {
  console.log('¡Carga de atlas completa!');
  // Crear un sprite usando una textura de atlas
  const sprite = PIXI.Sprite.from('nombreDeTexturaEnAtlas.png');
  app.stage.addChild(sprite);
});
```

## Referencias Bibliográficas

* [PixiJS Documentation](https://pixijs.com/docs/)
* [PixiJS Loader](https://pixijs.com/docs/v5/docs/loader.html)

### Referencias que refutan

* [Alternativas a PixiJS](https://www.alternativeto.net/software/pixijs/)
* [Comparación de bibliotecas de renderizado 2D](https://www.toptal.com/javascript/2d-rendering-libraries)

Espero que esta guía te haya sido útil para aprender a cargar y gestionar imágenes y texturas en PixiJS. Recuerda que cargar imágenes puede llevar tiempo, por lo que es importante manejar los eventos de carga apropiadamente para asegurarte de que tu aplicación o juego se ejecute de manera suave y eficiente.

[[⚫🔴🟡🟢🔵⚪ (🔴②)]] | ①②③④⑤⑥ | ⚫① 🔴② 🟡③ 🟢④ 🔵⑤ ⚪⑥