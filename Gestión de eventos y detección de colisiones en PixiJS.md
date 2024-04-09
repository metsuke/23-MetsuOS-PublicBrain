# Gestión de eventos y detección de colisiones en PixiJS

[[Aprender sobre PixiJS]]

Claro, la gestión de eventos y la detección de colisiones son aspectos importantes al desarrollar aplicaciones y juegos con PixiJS. Aquí tienes una explicación sobre cómo puedes implementar ambas:

1. **Gestión de eventos:**

   En PixiJS, puedes gestionar eventos utilizando los métodos `on` y `once` disponibles en los objetos visuales interactivos. Estos eventos pueden ser clics, toques, movimiento del mouse, etc. Por ejemplo:

   ```javascript
   // Crear un sprite interactivo
   const sprite = PIXI.Sprite.from('imagen.png');
   sprite.interactive = true;

   // Manejar clics en el sprite
   sprite.on('click', () => {
       console.log('Haz hecho clic en el sprite');
   });
   ```

   Además de los eventos básicos, PixiJS también proporciona eventos de puntero más avanzados como `'pointerdown'`, `'pointermove'`, `'pointerup'`, etc., que te permiten manejar interacciones de forma más precisa.

2. **Detección de colisiones:**

   Para la detección de colisiones, necesitas implementar la lógica para verificar si dos objetos visuales se están superponiendo. PixiJS no proporciona funciones de detección de colisiones integradas, pero puedes escribir tu propia lógica para esto.

   Por ejemplo, para detectar colisiones entre dos sprites rectangulares simples, puedes comparar las posiciones y dimensiones de los sprites:

   ```javascript
   function detectarColision(sprite1, sprite2) {
       return (
           sprite1.x < sprite2.x + sprite2.width &&
           sprite1.x + sprite1.width > sprite2.x &&
           sprite1.y < sprite2.y + sprite2.height &&
           sprite1.y + sprite1.height > sprite2.y
       );
   }

   // Uso:
   if (detectarColision(sprite1, sprite2)) {
       console.log('Colisión detectada');
   }
   ```

   Para colisiones más complejas, como formas irregulares o polígonos, puedes utilizar bibliotecas de detección de colisiones como SAT.js o implementar tus propios algoritmos según las necesidades de tu proyecto.

Al combinar la gestión de eventos y la detección de colisiones, puedes crear interacciones interesantes y dinámicas en tus aplicaciones y juegos PixiJS. Recuerda ajustar y optimizar tu código según las especificaciones y la complejidad de tu proyecto.