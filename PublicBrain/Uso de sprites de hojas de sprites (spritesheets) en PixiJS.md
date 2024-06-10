---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-14T00:24:55.726Z
modified: 2024-06-10T15:26:26.361Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
---
# Uso de sprites de hojas de sprites (spritesheets) en PixiJS

[[Aprender sobre PixiJS ⚫①]]

¡Por supuesto! El uso de hojas de sprites (spritesheets) es una técnica común en el desarrollo de juegos y aplicaciones con PixiJS. Una hoja de sprites es una imagen que contiene múltiples frames de animación o imágenes de diferentes elementos del juego. Aquí te muestro cómo puedes usar hojas de sprites en PixiJS:

1. **Preparación de la hoja de sprites**:
   - Crea una hoja de sprites que contenga todas las imágenes que necesitas para tu juego. Puedes utilizar software de diseño como Photoshop o herramientas en línea para crear y organizar tus frames de animación en una sola imagen.

2. **Carga de la hoja de sprites**:
   - Utiliza la clase `PIXI.Loader` para cargar la hoja de sprites en tu proyecto PixiJS. Agrega la hoja de sprites a la cola de carga y luego maneja el evento `load` para obtener la referencia a la textura de la hoja de sprites.

```javascript
const loader = PIXI.Loader.shared;
loader.add('hoja-sprites', 'ruta/a/hoja-de-sprites.png').load((loader, resources) => {
    const hojaSprites = resources['hoja-sprites'].texture;
    // Ahora puedes usar 'hojaSprites' para crear sprites individuales
});
```

3. **Definición de frames de animación**:
   - Especifica las coordenadas y dimensiones de cada frame de animación en la hoja de sprites. Puedes hacer esto utilizando la clase `PIXI.Rectangle`, que define un área rectangular en una textura.

```javascript
// Define los frames de animación en la hoja de sprites
const frame1 = new PIXI.Rectangle(x, y, ancho, alto);
const frame2 = new PIXI.Rectangle(x, y, ancho, alto);
// Define más frames si es necesario
```

4. **Creación de sprites individuales**:
   - Utiliza la textura de la hoja de sprites cargada y las coordenadas de los frames de animación para crear sprites individuales. Puedes hacer esto utilizando la clase `PIXI.Sprite` y especificando la región de la textura que corresponde a cada frame.

```javascript
// Crea sprites individuales utilizando la hoja de sprites y las coordenadas de los frames
const sprite1 = new PIXI.Sprite(new PIXI.Texture(hojaSprites, frame1));
const sprite2 = new PIXI.Sprite(new PIXI.Texture(hojaSprites, frame2));
// Crea más sprites si es necesario
```

5. **Animación de sprites**:
   - Si estás creando una animación, puedes cambiar el frame de un sprite a intervalos regulares para simular la animación. Esto se hace cambiando la textura del sprite en cada frame.

```javascript
// Cambia la textura del sprite en cada frame para animar
function animar() {
    requestAnimationFrame(animar);
    // Cambia la textura del sprite para el siguiente frame de animación
    sprite.texture = nuevaTextura;
}
```

Con estos pasos, puedes usar hojas de sprites para crear y animar elementos visuales en tus proyectos de PixiJS de manera eficiente y dinámica.