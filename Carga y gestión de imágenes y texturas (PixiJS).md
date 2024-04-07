---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-07T07:43:18.747Z
modified: 2024-04-07T07:49:24.981Z
ver_major: 0
ver_minor: 1
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# Carga y gestión de imágenes y texturas (PixiJS)

[[Aprender sobre PixiJS]]

Por supuesto, en el contexto de aprender PixiJS, la carga y gestión de imágenes y texturas es un aspecto fundamental para crear contenido visual en tus aplicaciones o juegos. PixiJS proporciona una manera fácil y eficiente de cargar y manejar imágenes y texturas. Aquí hay una guía básica sobre cómo hacerlo:

1. **Cargar una Imagen**:
   Para cargar una imagen en PixiJS, puedes usar la clase `PIXI.Loader`. Aquí tienes un ejemplo básico:

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

2. **Usar una Textura**:
   Una vez que la imagen está cargada, puedes usarla para crear texturas. Aquí tienes un ejemplo de cómo crear una textura y un sprite:

   ```javascript
   // Crear una textura a partir de la imagen cargada
   const texture = PIXI.Texture.from('nombre');

   // Crear un sprite usando la textura
   const sprite = new PIXI.Sprite(texture);

   // Añadir el sprite al escenario
   app.stage.addChild(sprite);
   ```

3. **Gestión de Múltiples Imágenes**:
   Si necesitas cargar múltiples imágenes, simplemente repite el proceso de agregar imágenes al cargador y usa las texturas correspondientes donde sea necesario.

4. **Gestión de Texturas Atlas**:
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

Con esta guía básica, deberías poder comenzar a cargar y gestionar imágenes y texturas en PixiJS. Recuerda que cargar imágenes puede llevar tiempo, por lo que es importante manejar los eventos de carga apropiadamente para asegurarte de que tu aplicación o juego se ejecute de manera suave y eficiente.

---

PixiJS ofrece una forma fácil y eficiente de cargar y gestionar imágenes y texturas en tus aplicaciones web interactivas. Hay varios métodos que puedes utilizar para cargar imágenes y texturas en PixiJS:

1. **PIXI.Loader**: El objeto PIXI.Loader te permite cargar imágenes y texturas de forma asíncrona. Puedes agregar imágenes individuales o cargar un archivo JSON que contenga información sobre múltiples imágenes y texturas. Una vez que las imágenes se han cargado, puedes acceder a ellas a través del objeto PIXI.Loader.shared.resources.



2. **PIXI.Texture.fromImage**: Utiliza el método PIXI.Texture.fromImage para crear una textura a partir de una imagen cargada previamente en el DOM.



3. **Spritesheet y Texture Atlas**: Puedes utilizar spritesheets y texture atlases para gestionar múltiples imágenes y texturas en un solo archivo. Esto es útil para reducir el número de solicitudes de red y mejorar el rendimiento de tu aplicación.

4. **Carga de texturas en WebGL**: PixiJS también te ofrece la posibilidad de cargar texturas en formatos específicos para WebGL, como texturas comprimidas en formatos PVR, DDS o KTX. Esto puede mejorar significativamente el rendimiento de tus aplicaciones, especialmente en dispositivos móviles.

En resumen, PixiJS proporciona una variedad de opciones para cargar y gestionar imágenes y texturas de forma eficiente en tus aplicaciones web interactivas, lo que te permite crear experiencias visuales de alta calidad para tus usuarios.
