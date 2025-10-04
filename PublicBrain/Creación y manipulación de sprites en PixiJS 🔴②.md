---
iaStatus: 8
iaStatus_Model: Grok-4, Raul Carrillo aka Metsuke
a11y: 0
checked: 0
lang: ES
translations:
created: 2024-04-07T07:46:24.979Z
modified: 2025-10-04T03:07:04.660Z
supervisado: 2024-05-27T13:38:00.872Z
ACCION:
ver_major: 0
ver_minor: 4
ver_rev: 10
nav_primary:
nav_secondary:
tags:
MOS_TopImg_Video: CursoPixiJSSprites.mp4
---
# Creación y manipulación de sprites en PixiJS 🔴②

![PixiJS Trabajo con Sprites](PublicBrain/_resources/3c671f8c502b676c4341adde15035570_MD5.jpg)

 * [[Curso de PixiJS ⚫①]]
* [[Carga y gestión de imágenes y texturas (PixiJS) 🔴②|<< Anterior]] |  Siguiente >>

> WIP Revisando texto

Vamos a sumergirnos en profundidad y de forma detallada en la creación y manipulación de sprites. PixiJS es una biblioteca de JavaScript muy potente para renderizar gráficos 2D interactivos directamente en el navegador. Los sprites son uno de sus elementos clave, ya que permiten crear visuales dinámicos en juegos, animaciones o apps interactivas. Básicamente, un sprite es una imagen o textura que puedes posicionar, escalar, rotar y modificar a tu antojo en el escenario (stage).

En esta guía, iremos desde lo más básico hasta técnicas más avanzadas, con ejemplos de código, propiedades, métodos, interactividad y hasta sprites animados. Suponemos que ya tienes nociones básicas de PixiJS, como configurar una aplicación simple con `PIXI.Application`. Si no, échale un vistazo a las secciones previas del curso. ¡Empecemos!

## 1. ¿Qué es un sprite en PixiJS?

En PixiJS, un sprite es un objeto visual que representa una imagen o textura que se renderiza en la pantalla. Hereda de `PIXI.Container`, lo que le permite contener otros objetos si es necesario, aunque su rol principal es mostrar una textura (como una imagen) y aplicar transformaciones como posición, escala, rotación o tinte. Son ideales para renderizar muchos elementos de forma eficiente, como personajes en un juego o partículas en una animación.

- **Ventajas principales**: Ofrecen un alto rendimiento, soporte para texturas optimizadas, interactividad nativa y compatibilidad con WebGL o WebGPU.
- **Diferencias con otros objetos**: A diferencia de `PIXI.Graphics`, que se usa para dibujos vectoriales, los sprites trabajan con texturas rasterizadas, lo que los hace más rápidos para imágenes predefinidas.

## 2. Creación de sprites

Para crear un sprite, lo primero que necesitas es una textura. PixiJS ofrece varias maneras de cargar y generar sprites de forma sencilla.

### 2.1. Cargar texturas

Utiliza el sistema de assets de PixiJS para cargar imágenes. En versiones recientes (v8 y superiores), se recomienda usar `Assets` como cargador principal.

Aquí va un ejemplo básico:

```javascript
import { Application, Assets, Sprite } from 'pixi.js';

// Crear la aplicación
const app = new Application();
await app.init({ width: 800, height: 600 });
document.body.appendChild(app.canvas);

// Cargar textura
const texture = await Assets.load('ruta/a/imagen.png');

// Crear sprite
const sprite = new Sprite(texture);

// Agregar al stage
app.stage.addChild(sprite);
```

- **Assets.load**: Carga la textura de manera asíncrona y soporta promesas para gestionar la espera.
- **Sprite.from(url o texture)**: Un método estático práctico para crear un sprite directamente desde una URL o textura ya cargada.

  ```javascript
  const sprite = Sprite.from('ruta/a/imagen.png'); // Se carga automáticamente si no está en caché
  ```

### 2.2. Creación desde texturas existentes

Si ya dispones de una textura (por ejemplo, de un spritesheet), puedes reutilizarla fácilmente.

```javascript
const texture = Assets.get('imagen.png'); // Obtener de la caché
const sprite = new Sprite(texture);
```

### 2.3. Sprites desde spritesheets

Un spritesheet es una imagen grande que agrupa múltiples frames. Usa `PIXI.Spritesheet` para analizarlo y extraer texturas individuales.

Ejemplo (suponiendo un archivo JSON generado con herramientas como TexturePacker):

```javascript
const sheet = await Assets.load('ruta/a/spritesheet.json');
const texture = sheet.textures['frame1.png'];
const sprite = new Sprite(texture);
```

## 3. Manipulación de propiedades

Los sprites heredan propiedades de `Container` y añaden otras específicas para el control visual. Aquí tienes una lista completa, basada en la documentación de PixiJS v8.

### 3.1. Propiedades básicas de transformación

- **position** (ObservablePoint, por defecto: {x:0, y:0}): Posición relativa al contenedor padre.

  ```javascript
  sprite.position.set(100, 200); // O bien: sprite.x = 100; sprite.y = 200;
  ```

- **scale** (ObservablePoint, por defecto: {x:1, y:1}): Escala en los ejes X e Y.

  ```javascript
  sprite.scale.set(2, 2); // Duplica el tamaño
  ```

- **rotation** (number, por defecto: 0): Rotación en radianes. Usa `angle` si prefieres grados.

  ```javascript
  sprite.rotation = Math.PI / 4; // 45 grados
  sprite.angle = 45; // Lo mismo
  ```

- **pivot** (ObservablePoint, por defecto: {x:0, y:0}): Punto central para rotaciones y escalas.

  ```javascript
  sprite.pivot.set(50, 50); // Centro para un sprite de 100x100
  ```

- **skew** (ObservablePoint, por defecto: {x:0, y:0}): Distorsión en radianes.

  ```javascript
  sprite.skew.set(0.1, 0.1);
  ```

- **anchor** (ObservablePoint, por defecto: basado en la textura): Punto de anclaje (de 0 a 1) para alineaciones. Influye en posición y rotación.

  ```javascript
  sprite.anchor.set(0.5, 0.5); // Centrado
  ```

### 3.2. Propiedades visuales

- **texture** (Texture): La textura que se muestra. Cambiarla actualiza automáticamente el ancho y alto.

  ```javascript
  sprite.texture = newTexture;
  ```

- **width** / **height** (number): Ancho y alto en píxeles. Ajustan la escala de forma automática.

  ```javascript
  sprite.width = 200; // Mantiene la proporción si no se establece height
  ```

- **alpha** (number, por defecto: 1): Opacidad (de 0 a 1).

  ```javascript
  sprite.alpha = 0.5; // Semi-transparente
  ```

- **tint** (number, por defecto: 0xFFFFFF): Tinte de color (en hexadecimal o ColorSource).

  ```javascript
  sprite.tint = 0xFF0000; // Rojo
  ```

- **blendMode** (BLEND_MODES, por defecto: 'normal'): Modo de mezcla (por ejemplo, 'add' o 'multiply').

  ```javascript
  sprite.blendMode = 'add';
  ```

- **visible** (boolean, por defecto: true): Controla la visibilidad.
- **renderable** (boolean, por defecto: true): Indica si se renderiza (útil para optimizaciones).
- **roundPixels** (boolean, por defecto: false): Redondea la posición para un renderizado más nítido.

### 3.3. Propiedades de accesibilidad y eventos

- **accessible** (boolean): Activa la accesibilidad para lectores de pantalla.
- **cursor** (string): Estilo del cursor al pasar el ratón (por ejemplo, 'pointer').

### 3.4. Propiedades avanzadas

- **cullable** (boolean): Optimiza el culling para objetos fuera de la vista.
- **filterArea** (Rectangle): Área específica para aplicar filtros.
- **hitArea** (IHitArea): Área personalizada para detectar clics.
- **mask** (Mask): Máscara para recortar la visibilidad.
- **filters** (Filter[]): Aplica efectos como desenfoque o matriz de color.

## 4. Métodos principales

- **addChild(child)** / **removeChild(child)**: Añade o quita hijos, ya que es un contenedor.
- **destroy(options)**: Destruye el sprite y libera recursos.

  ```javascript
  sprite.destroy({ texture: true }); // Destruye también la textura
  ```

- **getBounds()**: Devuelve los límites (Bounds).
- **containsPoint(point)**: Comprueba si un punto está dentro del sprite.
- **updateTransform()**: Actualiza las transformaciones manualmente (poco común).
- **getGlobalPosition()**: Obtiene la posición global en el escenario.

Para una lista exhaustiva, consulta la documentación oficial de PIXI.Sprite.

## 5. Interactividad en sprites

Los sprites pueden reaccionar a eventos del usuario, como clics, hover o arrastres. Para activar la interactividad, configura `eventMode`.

### 5.1. Configuración básica

```javascript
sprite.eventMode = 'static'; // O 'dynamic' para eventos continuos
sprite.cursor = 'pointer'; // Cambia el cursor al pasar por encima
```

### 5.2. Eventos comunes

PixiJS maneja eventos unificados (pointer, mouse, touch).

```javascript
sprite.on('pointerdown', (event) => {
  console.log('¡Sprite clicado!', event);
  sprite.scale.set(1.5); // Ejemplo de cambio
});

sprite.on('pointerover', () => {
  sprite.tint = 0xFFFF00; // Amarillo al hover
});

sprite.on('pointerout', () => {
  sprite.tint = 0xFFFFFF; // Reset
});
```

- **Eventos disponibles**: pointerdown, pointerup, pointermove, click, mousedown, etc.
- **Sprite arrastrable**: Usa pointerdown para empezar el arrastre y pointermove para actualizar la posición.

  ```javascript
  let dragging = false;
  sprite.on('pointerdown', () => dragging = true);
  app.stage.on('pointermove', (event) => {
    if (dragging) sprite.position = event.global;
  });
  sprite.on('pointerup', () => dragging = false);
  ```

## 6. Sprites animados (AnimatedSprite)

`PIXI.AnimatedSprite` extiende `Sprite` para animaciones frame a frame, perfectas para personajes o efectos.

### 6.1. Creación

Desde un array de texturas o un spritesheet.

```javascript
const frames = [];
for (let i = 1; i <= 10; i++) {
  frames.push(Texture.from(`frame${i}.png`));
}
const animatedSprite = new AnimatedSprite(frames);
app.stage.addChild(animatedSprite);
animatedSprite.play();
```

Desde un spritesheet:

```javascript
const sheet = await Assets.load('spritesheet.json');
const anim = new AnimatedSprite(sheet.animations['walk']); // 'walk' es el nombre de la animación
```

### 6.2. Propiedades específicas

- **animationSpeed** (number, por defecto: 1): Velocidad (por ejemplo, 0.5 para más lento).
- **loop** (boolean, por defecto: true): Repite la animación.
- **autoUpdate** (boolean, por defecto: true): Actualiza automáticamente con el ticker.
- **currentFrame** (number): Frame actual.
- **playing** (boolean): Indica si se está reproduciendo.
- **onComplete** / **onLoop** / **onFrameChange**: Callbacks para eventos.

### 6.3. Métodos

- **play()**: Inicia la animación.
- **stop()**: Detiene la animación.
- **gotoAndPlay(frame)** / **gotoAndStop(frame)**: Salta a un frame y reproduce o detiene.
- **update(delta)**: Actualiza manualmente (si autoUpdate es false).

Ejemplo completo:

```javascript
animatedSprite.animationSpeed = 0.2;
animatedSprite.loop = false;
animatedSprite.onComplete = () => console.log('Animación terminada');
animatedSprite.play();
```

## 7. Mejores prácticas y optimizaciones

- **Gestión de texturas**: Aprovecha `Assets` para el caché y cargas asíncronas. Evita recargar la misma imagen una y otra vez.
- **Rendimiento**: Para manejar muchos sprites, considera `PIXI.ParticleContainer` en vez de añadirlos directamente al stage. Activa `cullable` para ignorar objetos fuera de pantalla.
- **Spritesheets**: Usa siempre spritesheets en animaciones para minimizar peticiones HTTP y mejorar la velocidad.
- **Destrucción**: No olvides destruir sprites innecesarios para liberar memoria: `sprite.destroy({ texture: true, children: true })`.
- **Escalabilidad**: Emplea `anchor` para alinear sprites correctamente en distintas resoluciones.
- **Herramientas**: TexturePacker es genial para crear spritesheets optimizados.
- **Errores comunes**: No agregar al stage, olvidar esperar la carga de texturas (usa await) o ignorar las proporciones al escalar.

## 8. Ejercicio práctico

Prueba a crear un sprite de un personaje, hazlo interactivo (por ejemplo, que rote al clicar) y añade una animación de caminata con un spritesheet. Juega con tint y scale para ver los efectos. ¡Experimenta para afianzar lo aprendido!

Para más información, consulta la documentación oficial de PixiJS v8. ¡Sigue practicando para dominar los sprites!

## Referencias bibliográficas que apoyan el contenido

> WIP Revisando fuentes

Estas fuentes confirman y amplían los conceptos explicados, como la creación con Assets, propiedades de transformación y animaciones.

- Documentación oficial de PixiJS v8.13.2: [https://pixijs.download/v8.13.2/docs/index.html](https://pixijs.download/v8.13.2/docs/index.html)
- Guía de sprites en PixiJS v8: [https://pixijs.com/8.x/guides/components/scene-objects/sprite](https://pixijs.com/8.x/guides/components/scene-objects/sprite)
- Tutorial en vídeo: Sprites - Pixi.js Tutorial for Absolute Beginners (Wael Yasmina): [https://www.youtube.com/watch?v=gcy3JydsKPg](https://www.youtube.com/watch?v=gcy3JydsKPg)
- Tutorial en vídeo: PixiJS Part 5: Sprites (Dower Chin): [https://www.youtube.com/watch?v=99O671QWL9o](https://www.youtube.com/watch?v=99O671QWL9o)
- Tutorial en vídeo: PixiJS Part 8: Animated Spritesheets (Dower Chin): [https://www.youtube.com/watch?v=FjiQSwohBVs](https://www.youtube.com/watch?v=FjiQSwohBVs)

## Referencias bibliográficas que refutan el contenido

> WIP Revisando fuentes

Estas fuentes destacan limitaciones o problemas que contradicen afirmaciones como el "alto rendimiento" para grandes cantidades de sprites sin optimizaciones adicionales, o el rendimiento en móviles.

- Discusión sobre creación y destrucción de muchos sprites (limitaciones en rendimiento y GC): [https://www.html5gamedevs.com/topic/43650-creating-and-destroying-lots-of-sprites/](https://www.html5gamedevs.com/topic/43650-creating-and-destroying-lots-of-sprites/)
- Pregunta en Stack Overflow sobre rendimiento lento en móviles comparado con CSS: [https://stackoverflow.com/questions/49119066/pixijs-very-slow-in-mobile-compared-to-css](https://stackoverflow.com/questions/49119066/pixijs-very-slow-in-mobile-compared-to-css)
- Issue en GitHub sobre límite máximo de sprites en batch (16384 por limitaciones de WebGL): [https://github.com/pixijs/pixi.js/issues/91](https://github.com/pixijs/pixi.js/issues/91)

![[Plantilla - 1MT#One More Thing]]