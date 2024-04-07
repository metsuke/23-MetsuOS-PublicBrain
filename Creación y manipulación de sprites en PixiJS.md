---
iaStatus: 0
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-08-30T00:54:00
modified: 2024-03-06T23:35:00
ver_major: 0
ver_minor: "0"
ver_rev: "0"
nav_primary: []
nav_secondary: []
tags: []
---
# Creación y manipulación de sprites en PixiJS

[[Aprender sobre PixiJS]]

¡Por supuesto! En PixiJS, los sprites son elementos fundamentales para representar gráficos en la pantalla. Los sprites pueden ser imágenes, texturas o incluso objetos gráficos que pueden ser manipulados y animados en tu aplicación o juego. Aquí tienes una guía básica sobre la creación y manipulación de sprites en PixiJS:

1. **Creación de un Sprite**:
   Para crear un sprite en PixiJS, puedes utilizar la clase `PIXI.Sprite`. Aquí tienes un ejemplo básico:

   ```javascript
   // Crear un sprite a partir de una imagen
   const sprite = PIXI.Sprite.from('ruta/a/la/imagen.png');

   // Añadir el sprite al escenario
   app.stage.addChild(sprite);
   ```

   En este ejemplo, `ruta/a/la/imagen.png` es la ruta de la imagen que deseas usar como sprite. Puedes cargar la imagen previamente usando el cargador de PixiJS, como se mencionó en la respuesta anterior, o puedes usar una textura existente.

2. **Posicionamiento y Escala**:
   Puedes establecer la posición y la escala de un sprite utilizando las propiedades `x`, `y`, `width` y `height`. Aquí tienes un ejemplo:

   ```javascript
   // Establecer la posición del sprite
   sprite.x = 100;
   sprite.y = 200;

   // Establecer la escala del sprite
   sprite.scale.x = 2;
   sprite.scale.y = 2;
   ```

   Esto colocará el sprite en la posición `(100, 200)` y lo escalará al doble de su tamaño original.

3. **Rotación**:
   Puedes rotar un sprite utilizando la propiedad `rotation`. Por ejemplo:

   ```javascript
   // Rotar el sprite 45 grados en sentido antihorario
   sprite.rotation = Math.PI / 4; // 45 grados en radianes
   ```

4. **Animación**:
   Los sprites también pueden ser animados cambiando su textura o sus propiedades en el tiempo. Por ejemplo, para crear una animación simple de cambio de textura:

   ```javascript
   // Crear un array de texturas para la animación
   const texturas = [];
   texturas.push(PIXI.Texture.from('imagen1.png'));
   texturas.push(PIXI.Texture.from('imagen2.png'));
   // Agregar más texturas si es necesario

   // Crear un sprite de animación
   const animacion = new PIXI.AnimatedSprite(texturas);

   // Configurar la velocidad de la animación
   animacion.animationSpeed = 0.1;

   // Comenzar la animación
   animacion.play();

   // Añadir el sprite de animación al escenario
   app.stage.addChild(animacion);
   ```

   En este ejemplo, `imagen1.png` y `imagen2.png` son las imágenes que componen la animación. Puedes agregar más texturas al array `texturas` si deseas una animación más larga.

Con estas herramientas básicas, puedes crear y manipular sprites en PixiJS para construir gráficos interactivos y animaciones en tu aplicación o juego. Experimenta con diferentes propiedades y métodos para lograr los efectos visuales deseados.