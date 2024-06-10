---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo, llama3-70b-8192
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-07T07:46:24.979Z
modified: 2024-06-10T15:14:13.960Z
supervisado: 2024-05-27T13:38:00.872Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 8
nav_primary: 
nav_secondary: 
tags:
---
# Creación y manipulación de sprites en PixiJS 🔴②

[[Aprender sobre PixiJS ⚫①]]

## Introducción

En PixiJS, los sprites son elementos fundamentales para representar gráficos en la pantalla. Los sprites pueden ser imágenes, texturas o incluso objetos gráficos que pueden ser manipulados y animados en tu aplicación o juego.

## Creación de un Sprite

Para crear un sprite en PixiJS, puedes utilizar la clase `PIXI.Sprite`. Aquí tienes un ejemplo básico:

```javascript
// Crear un sprite a partir de una imagen
const sprite = PIXI.Sprite.from('ruta/a/la/imagen.png');

// Añadir el sprite al escenario
app.stage.addChild(sprite);
```

En este ejemplo, `ruta/a/la/imagen.png` es la ruta de la imagen que deseas usar como sprite. Puedes cargar la imagen previamente usando el cargador de PixiJS, como se mencionó en la respuesta anterior, o puedes usar una textura existente.

## Posicionamiento y Escala

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

## Rotación

Puedes rotar un sprite utilizando la propiedad `rotation`. Por ejemplo:

```javascript
// Rotar el sprite 45 grados en sentido antihorario
sprite.rotation = Math.PI / 4; // 45 grados en radianes
```

## Animación

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

## Referencias

* [PixiJS Documentation](https://pixijs.com/docs/)
* [PixiJS Tutorials](https://pixijs.com/tutorials/)

## Bibliografía

* [PixiJS: A High-Performance HTML5 Canvas Library](https://www.smashingmagazine.com/2014/06/pixijs-high-performance-html5-canvas-library/)
* [Creating a PixiJS Game](https://www.gamedev.net/articles/programming/general-programming/creating-a-pixijs-game-r3014/)

## Bibliografía que refuta el contenido

* [PixiJS Limitations](https://github.com/pixijs/pixi.js/issues/4444): Este issue en GitHub destaca algunas limitaciones de PixiJS, como la falta de soporte para WebGL 2.0 y la limitación en el uso de shaders.
* [PixiJS vs. Phaser: A Comparison](https://www.gamedev.net/articles/programming/general-programming/pixijs-vs-phaser-a-comparison-r3015/): Este artículo de GameDev.net compara PixiJS con Phaser, otro framework de juegos, y destaca algunas limitaciones de PixiJS en comparación con Phaser.
* [PixiJS Performance Issues](https://www.smashingmagazine.com/2019/02/pixijs-performance-issues/): Este artículo de Smashing Magazine destaca algunos problemas de rendimiento comunes en PixiJS y ofrece consejos para mejorar el rendimiento.


![[⚫🔴🟡🟢🔵⚪ (🔴②)#Sobre el sistema de validez de un contenido en MetsuOS]]