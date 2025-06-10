---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-14T00:22:40.088Z
modified: 2025-06-10T21:14:03.171Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 5
nav_primary: []
nav_secondary: []
tags: []
---
# Carga de audio y video en PixiJS

[[Curso de PixiJS ⚫①]]

¡Claro! En PixiJS, la carga de archivos de audio y video es fundamental para crear experiencias multimedia completas. Aquí te muestro cómo puedes cargar y utilizar archivos de audio y video en PixiJS:

**Carga de archivos de audio:**

1. **Importa PixiJS**: Asegúrate de incluir PixiJS en tu proyecto. Puedes hacerlo utilizando un enlace CDN o instalándolo a través de npm si estás utilizando un entorno de desarrollo basado en Node.js.

2. **Carga de archivos de audio**: PixiJS proporciona la clase `PIXI.Loader` para cargar recursos, incluidos archivos de audio. Puedes usar el método `add` para agregar archivos de audio a la cola de carga y luego llamar al método `load` para comenzar la carga.

```javascript
const loader = PIXI.Loader.shared;
loader.add('nombre-audio', 'ruta/al/archivo.mp3').load((loader, resources) => {
    // El audio se ha cargado correctamente
    const audio = resources['nombre-audio'].sound;
    // Ahora puedes usar 'audio' para reproducir el sonido
});
```

3. **Reproducción de audio**: Una vez que el audio se haya cargado correctamente, puedes reproducirlo utilizando la API de audio de JavaScript estándar.

```javascript
audio.play();
```

**Carga de archivos de video:**

1. **Carga de archivos de video**: PixiJS no tiene soporte nativo para la reproducción de video, pero puedes usar la etiqueta `<video>` de HTML para cargar y reproducir videos. Puedes crear un elemento `<video>` en tu HTML y luego manipularlo con JavaScript.

```html
<video id="video" src="ruta/al/video.mp4" controls></video>
```

2. **Manipulación de video con PixiJS**: Aunque PixiJS no tiene soporte nativo para la reproducción de video, puedes superponer elementos de video en tu lienzo de PixiJS y controlar su posición y escala como lo harías con cualquier otro objeto visual.

```javascript
// Obtener el elemento de video
const videoElement = document.getElementById('video');
// Crear una textura de video
const texture = PIXI.Texture.from(videoElement);
// Crear un sprite para el video
const videoSprite = new PIXI.Sprite(texture);
// Añadir el sprite al escenario
app.stage.addChild(videoSprite);
```

3. **Control de video**: Puedes controlar la reproducción y otros aspectos del video utilizando la API de video de HTML5 estándar en combinación con eventos y métodos de JavaScript.

```javascript
// Reproducir el video
videoElement.play();
```

Con estas técnicas, puedes cargar y utilizar archivos de audio y video en tus proyectos de PixiJS para crear experiencias multimedia envolventes y dinámicas.