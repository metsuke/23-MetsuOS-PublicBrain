---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo, llama3-70b-8192, grpk-4, Raúl Carrillo aka metsuke
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2024-04-07T07:43:18.747Z
modified: 2025-10-19T06:13:42.863Z
supervisado: 2024-05-27T13:38:00.569Z
ACCION:
ver_major: 0
ver_minor: 4
ver_rev: 17
nav_primary:
nav_secondary:
tags:
MOS_TopImg_Video: CursoPixiJS_ImagenesTexturas.mp4
---
# Carga y gestión de imágenes y texturas (PixiJS) 🔴②

![Imagenes y Texturas en PixiJS](PublicBrain/_resources/fb89498a19570fba6d7a5e8de0260eaa_MD5.jpg)

 * [[Curso de PixiJS ⚫①]]
* [[Dibujando formas básicas y gráficos (PixiJS) 🟡③|<< Anterior]] |  [[Creación y manipulación de sprites en PixiJS 🔴②|Siguiente >>]]

> WIP: Revisando Fuentes

PixiJS es una biblioteca de renderizado 2D en JavaScript que brilla por su habilidad para manejar gráficos interactivos con un rendimiento excepcional. En el corazón del desarrollo de juegos y aplicaciones visuales con esta herramienta se encuentra la carga y gestión de imágenes y texturas, elementos clave que sirven de base para sprites, mallas y otros objetos que se renderizan en pantalla.

En este capítulo, vamos a sumergirnos de forma exhaustiva y detallada en cómo cargar, crear, gestionar y optimizar estas imágenes y texturas en PixiJS. Abordaremos el ciclo de vida completo de las texturas, los métodos de carga asíncrona, los tipos de fuentes de datos compatibles, las mejores prácticas para el manejo de la memoria y el rendimiento, junto con ejemplos prácticos de código. Todo esto se inspira en la documentación oficial de PixiJS versión 8.x, adaptado al entorno de MetsuOS, donde damos prioridad a configuraciones vanilla con HTML y JS puro en producción, sin dependencias como Node.js durante la ejecución.

## Introducción a las Texturas en PixiJS

Las texturas en PixiJS son piezas fundamentales en el proceso de renderizado. Ellas definen el contenido visual que se aplica a objetos como los Sprites (para imágenes sencillas) o las Meshes (para gráficos más elaborados). El sistema de texturas gira en torno a dos clases principales:

- **TextureSource**: Representa la fuente subyacente de píxeles, como una imagen, un lienzo o un vídeo. Es el "origen" puro de los datos visuales.
- **Texture**: Ofrece una "vista" sobre un TextureSource, permitiendo subregiones (como en un sprite sheet), recortes (trims) y transformaciones. Varias Textures pueden compartir el mismo TextureSource para ahorrar memoria de forma eficiente.

El flujo habitual en su ciclo de vida es el siguiente:  

Archivo de origen (imagen o vídeo) → TextureSource → Texture → Objeto visual (por ejemplo, un Sprite).

Estas texturas aprovechan WebGL para un renderizado rápido y fluido, con un respaldo a Canvas en caso de que WebGL no esté disponible. En el contexto de MetsuOS, esto resulta perfecto para entornos compatibles con tecnología retro, ya que no exige dependencias extra en producción.

### Propiedades Comunes de Texture

- **frame**: Rectángulo que delimita la porción visible dentro de la fuente.
- **orig**: Dimensiones originales sin aplicar recortes.
- **trim**: Define áreas a recortar para eliminar espacios transparentes (ideal para atlas de sprites).
- **uvs**: Coordenadas UV generadas a partir de `frame` y `rotate`.
- **rotate**: Valor de rotación (GroupD8) para compatibilidad con atlas.
- **defaultAnchor**: Punto de anclaje predeterminado para Sprites.
- **defaultBorders**: Usado en escalados de tipo 9-slice.
- **source**: La instancia asociada de TextureSource.

### Propiedades Comunes de TextureSource

- **resolution**: Influye en el tamaño de renderizado relativo a los píxeles reales (útil para escalados en pantallas retina).
- **format**: Formato de la textura (por ejemplo, `rgba8unorm` o `bgra8unorm`).
- **alphaMode**: Controla la interpretación del canal alfa al subir a la GPU (por ejemplo, `premultiply-alpha`).
- **wrapMode / scaleMode**: Modos de envoltura (wrap) y escalado (por ejemplo, `repeat` o `linear` para un filtrado suave).
- **autoGenerateMipmaps**: Genera mipmaps de forma automática para optimizar el rendimiento en escalados.

Puedes configurar estas propiedades al crear la textura o modificarlas dinámicamente según necesites.

## Carga de Imágenes y Texturas

PixiJS emplea el singleton `Assets` para cargar recursos de manera asíncrona, basado en Promises, con soporte integrado para caché y parsers automáticos. Es una opción más moderna y eficiente que los loaders antiguos. `Assets` detecta automáticamente el tipo de archivo por su extensión y gestiona imágenes, vídeos, JSON para sprite sheets y texturas comprimidas.

### Inicialización de Assets

Antes de empezar a cargar, es recomendable inicializar `Assets` con opciones globales, especialmente en MetsuOS para definir rutas base sin recurrir a Node.js:

```javascript
import { Assets } from 'pixi.js';
await Assets.init({
  basePath: './assets/',  // Ruta base para recursos relativos
  defaultSearchParams: 'v=1.0',  // Parámetros URL por defecto (ej. para cache-busting)
  texturePreference: { resolution: 2, format: 'png' }  // Preferencias para texturas (ej. alta resolución)
});
```

### Carga de una Sola Textura

La carga es sencilla: llama a `Assets.load()` con la URL. Devuelve una Promise que se resuelve con la textura cargada.

```javascript
import { Assets, Sprite, Texture } from 'pixi.js';

// Carga asíncrona
const texture = await Assets.load<Texture>('assets/bunny.png');  // URL absoluta o relativa

// Crea un Sprite con la textura
const sprite = new Sprite(texture); app.stage.addChild(sprite);
```

Para usar alias (nombres cortos en vez de URLs largas):

```javascript
await Assets.load<Texture>({ alias: 'bunny', src: 'assets/bunny.png' });
const bunnyTexture = Assets.get('bunny');  // Recupera por alias
```

### Carga de Múltiples Texturas

Puedes cargar un array de URLs o un objeto con alias. Devuelve un objeto con las texturas indexadas por URL o alias.

```javascript
const textures = await Assets.load<Texture>([
  'assets/bunny.png',
  'assets/cat.png'
]);

const bunnySprite = new Sprite(textures['assets/bunny.png']);
const catSprite = new Sprite(textures['assets/cat.png']);
app.stage.addChild(bunnySprite, catSprite);
```

O con alias para varios:

```javascript
const assetsToLoad = [
  { alias: 'bunny', src: 'assets/bunny.png' },
  { alias: 'cat', src: 'assets/cat.png' }
];
await Assets.load(assetsToLoad);
const bunny = Assets.get('bunny');
```

### Carga en Segundo Plano (Background Loading)

Para evitar bloquear la interfaz durante cargas pesadas, usa `Assets.backgroundLoad()`. No espera a que termine, pero puedes verificar el progreso.

```javascript
Assets.backgroundLoad(['assets/large-image.png', 'assets/another.png']);
// Más tarde, accede cuando esté listo
const texture = await Assets.load('assets/large-image.png');  // Espera si no ha terminado
```

### Tipos de Fuentes de Datos Soportadas

PixiJS soporta una variedad de fuentes para TextureSource, adaptadas a distintos escenarios:

| Tipo de TextureSource | Descripción | Ejemplo de uso |
|-----------------------|-------------|----------------|
| **ImageSource** | HTMLImageElement, ImageBitmap, SVG, VideoFrame, etc. | Imágenes estáticas: `new ImageSource({ resource: myImageElement })` |
| **CanvasSource** | HTMLCanvasElement o OffscreenCanvas | Gráficos generados dinámicamente: dibujar en canvas y usarlo como textura. |
| **VideoSource** | HTMLVideoElement | Texturas de vídeo: `new VideoSource({ resource: myVideo, autoPlay: true, updateFPS: 30 })` |
| **BufferImageSource** | TypedArray o ArrayBuffer con width/height/format explícitos | Datos raw de píxeles: útil para generación procedural. |
| **CompressedSource** | Array de mipmaps comprimidos (Uint8Array[]) | Texturas optimizadas para GPU: soporta .basis, .dds, .ktx. |

Para texturas comprimidas (mejor rendimiento en móviles):

```javascript
const compressedTexture = await Assets.load('assets/texture.ktx2');
```

## Gestión y Optimización de Texturas

### Caché y Reutilización

`Assets` cachea automáticamente por URL o alias. Las cargas repetidas devuelven la misma instancia, lo que ahorra ancho de banda y memoria.

```javascript
const tex1 = await Assets.load('bunny.png');
const tex2 = await Assets.load('bunny.png');
console.log(tex1 === tex2);  // true
```

### Descarga y Destrucción

Para liberar memoria (esencial en MetsuOS para entornos con recursos limitados):

- `Assets.unload('bunny.png')`: Descarga y elimina del caché.
- `texture.destroy()`: Destruye manualmente (para texturas no cargadas por Assets).
- `texture.source.unload()`: Descarga de la GPU pero mantiene en memoria (útil para reutilizar después).

Ejemplo:

```javascript
await Assets.load('temp.png');
const tempTexture = Assets.get('temp.png');
// Usar...
await Assets.unload('temp.png');  // Libera completamente
```

### Preparación de Texturas (Plugin Prepare)

Para evitar picos de lag al subir muchas texturas a la GPU, usa el plugin Prepare para precargar.

```javascript
import { PrepareSystem } from 'pixi.js';  // Asegúrate de importar si es necesario
app.renderer.addSystem(PrepareSystem, 'prepare');  // Agrega al renderer

// Prepara texturas antes de mostrar
await app.renderer.prepare.upload([texture1, texture2]);
```

### Creación Manual de Texturas

Si prefieres no usar `Assets` (por ejemplo, para generación dinámica en MetsuOS vanilla):

```javascript
const myImage = new Image();
myImage.src = 'assets/bunny.png';
myImage.onload = () => {
  const source = new TextureSource({ resource: myImage });
  const texture = new Texture({ source, frame: new Rectangle(0, 0, 100, 100) });  // Sub-región opcional
  const sprite = new Sprite(texture);
};
```

Para texturas dinámicas (actualizaciones en tiempo de ejecución):

```javascript
const texture = new Texture({ source: mySource, dynamic: true });
texture.frame = new Rectangle(10, 10, 50, 50);  // Modifica dinámicamente
```

### Manejo de Errores

`Assets` gestiona errores mediante Promises. Usa `try-catch` o `.catch()`:

```javascript
try {
  const texture = await Assets.load('invalid.png');
} catch (error) {
  console.error('Error cargando textura:', error);
  // Fallback: usa una textura placeholder
  const fallback = Texture.EMPTY;  // Textura vacía predeterminada de PixiJS
}
```

Si una carga falla, `Texture.from()` crea una textura válida de 1x1 píxel por defecto.

## La app de prueba

Un ejemplo cargando texturas de MetsuOS
**<div class='pixi-app' id='mos-integration'><div class='pixi-container'  id='pixi-container'></div></div><script type='text/javascript' id='PixiText' async src='https://metsuke.com/assets/apps/PixiJS/004-Texturas/app-texturas.iife.js'></script>

## Referencias Bibliográficas que Apoyan el Contenido

> WIP: Revisando Fuentes

- [Documentación oficial de PixiJS sobre Textures (v8.x) 🌐🟡③](https://pixijs.com/8.x/guides/components/textures) .– Proporciona una guía detallada sobre la carga y uso de texturas, alineada con el ciclo de vida descrito.
- [Documentación oficial de PixiJS sobre Assets (v8.x) 🌐🟡③](https://pixijs.com/8.x/guides/components/assets) .- Explica el sistema de carga asíncrona y caché, respaldando los ejemplos de código proporcionados.
- [Tutorial en YouTube: "Pixi.js Tutorial for Absolute Beginners - Assets" por Wael Yasmina (2024) 🌐🟡③](https://www.youtube.com/watch?v=JRYU6-CgHU4](https://www.youtube.com/watch?v=JRYU6-CgHU4) .– Demuestra la carga de assets de forma práctica, coincidiendo con los métodos descritos.
- [Tutorial en YouTube: "PixiJS Part 4: Texture Loading" (2019) 🌐🟡③](https://www.youtube.com/watch?v=EDEUsXqPTI0](https://www.youtube.com/watch?v=EDEUsXqPTI0) .– Cubre la carga de texturas en versiones anteriores, pero compatible con v8.x en principios básicos.
- Tutorial de PixiJS para principiantes por Wael Yasmina (2024): 
---
- [https://waelyasmina.net/articles/pixi-js-tutorial-for-complete-beginners/](https://waelyasmina.net/articles/pixi-js-tutorial-for-complete-beginners/) – Refuerza conceptos de carga y gestión con ejemplos accesibles.
- Tutoriales para PixiJS y TexturePacker por CodeAndWeb: [https://www.codeandweb.com/texturepacker/tutorials/pixijs](https://www.codeandweb.com/texturepacker/tutorials/pixijs) – Enfocado en optimización de texturas y sprite sheets, apoyando las prácticas de rendimiento.

## Referencias Bibliográficas que Refutan el Contenido

> WIP: Revisando Fuentes

- Discusión en GitHub sobre Pixi Asset Pack 1.0 – Beneficios y Limitaciones actuales (2024): [https://github.com/pixijs/pixijs/discussions/10917](https://github.com/pixijs/pixijs/discussions/10917) – Señala limitaciones en el workflow de assets, como la necesidad de mejoras en la generación de manifests, lo que podría cuestionar la simplicidad absoluta del sistema Assets en escenarios complejos.
- Comparación Pixi.js vs Phaser 3 por Selina Byeon (2021): [https://selinabyeon.medium.com/pixi-js-vs-phaser-3-519eba2f9817](https://selinabyeon.medium.com/pixi-js-vs-phaser-3-519eba2f9817) – Argumenta que Phaser ofrece más funcionalidades integradas (como física), lo que implica que PixiJS requiere más trabajo manual en gestión de texturas para juegos completos, refutando la idea de que sea siempre la opción más eficiente.
- Artículo "Phaser vs PixiJS for making 2D games" en DEV Community (2022): [https://dev.to/ritza/phaser-vs-pixijs-for-making-2d-games-2j8c](https://dev.to/ritza/phaser-vs-pixijs-for-making-2d-games-2j8c) – Destaca que Phaser incluye física incorporada, a diferencia de PixiJS, sugiriendo que la gestión de texturas en Pixi podría ser menos integrada en entornos de juegos avanzados.
- Pregunta en Stack Overflow: "Decide Pixi.js or Phaser" (2016): [https://stackoverflow.com/questions/38509629/decide-pixi-js-or-phaser](https://stackoverflow.com/questions/38509629/decide-pixi-js-or-phaser) – Menciona que Phaser usa una versión modificada y más antigua de Pixi para renderizado, lo que podría implicar que las optimizaciones de texturas en Pixi v8 no siempre superan a frameworks más completos en rendimiento real.
- Comparación PixiJS vs Phaser: The Gold Standard por Aircada (2023): [https://aircada.com/blog/pixijs-vs-phaser](https://aircada.com/blog/pixijs-vs-phaser) – Enfatiza que Phaser despliega Canvas y WebGL de manera más holística para juegos, cuestionando la superioridad de PixiJS en gestión de texturas para aplicaciones no puramente renderizadas.

![[Plantilla - 1MT#One More Thing]]