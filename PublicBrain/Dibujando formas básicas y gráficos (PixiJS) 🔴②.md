---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo, llama3-70b-8192
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.105Z
modified: 2024-05-13T20:02:38.302Z
supervisado: 2024-05-11T21:48:56.863Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 9
nav_primary: 
nav_secondary: 
tags:
---
# Dibujando formas básicas y gráficos (PixiJS) 🔴②

[[Aprender sobre PixiJS ⚫①]]

Aquí tienes el contenido formateado en Markdown con encabezados jerárquicos:

## Introducción

PixiJS es una biblioteca de JavaScript para crear gráficos y experiencias visuales interactivas en la web. Una de las características más poderosas de PixiJS es la capacidad de dibujar formas básicas y gráficos utilizando la clase `Graphics`. En este artículo, te mostraremos cómo dibujar rectángulos, círculos, líneas y polígonos utilizando PixiJS.

## Dibujar un rectángulo

Para dibujar un rectángulo, puedes utilizar el método `drawRect` de la clase `Graphics`. Por ejemplo:

```javascript
const graphics = new PIXI.Graphics();

// Dibujar un rectángulo
graphics.beginFill(0xFF0000); // Color rojo
graphics.drawRect(50, 50, 100, 100); // (x, y, ancho, alto)
graphics.endFill();

app.stage.addChild(graphics);
```

## Dibujar un círculo

Para dibujar un círculo, puedes utilizar el método `drawCircle` de la clase `Graphics`. Por ejemplo:

```javascript
const graphics = new PIXI.Graphics();

// Dibujar un círculo
graphics.beginFill(0x00FF00); // Color verde
graphics.drawCircle(200, 200, 50); // (x, y, radio)
graphics.endFill();

app.stage.addChild(graphics);
```

## Dibujar una línea

Para dibujar una línea, puedes utilizar el método `lineStyle` para configurar el estilo de la línea y luego usar los métodos `moveTo` y `lineTo` para definir los puntos de inicio y fin de la línea. Por ejemplo:

```javascript
const graphics = new PIXI.Graphics();

// Configurar estilo de la línea
graphics.lineStyle(4, 0x0000FF, 1); // Grosor, color azul, opacidad 1

// Dibujar una línea
graphics.moveTo(300, 300); // Punto de inicio
graphics.lineTo(400, 400); // Punto de fin

app.stage.addChild(graphics);
```

## Dibujar un polígono

Para dibujar un polígono, puedes utilizar los métodos `drawPolygon` y `drawRect` para definir sus vértices. Por ejemplo:

```javascript
const graphics = new PIXI.Graphics();

// Dibujar un polígono
graphics.beginFill(0xFFFF00); // Color amarillo
graphics.drawPolygon([
    500, 500,   // Primer vértice (x, y)
    600, 500,   // Segundo vértice (x, y)
    550, 600    // Tercer vértice (x, y)
]);
graphics.endFill();

app.stage.addChild(graphics);
```

## Conclusión

En este artículo, hemos visto cómo dibujar formas básicas y gráficos utilizando PixiJS. Estas técnicas pueden ser combinadas para crear gráficos más complejos y experiencias visuales interactivas en tu aplicación web.

## Referencias bibliográficas que apoyan

- PixiJS. (s.f.). Graphics. En PixiJS Documentation. <https://pixijs.download/dev/docs/PIXI.Graphics.html>
- Goodboy Digital. (s.f.). Pixi.js Tutorial for Beginners. En Goodboy Digital. <https://goodboydigital.com/pixi-js-tutorial-for-beginners/>

## Referencias bibliográficas que refutan

- Phaser. (s.f.). Phaser vs Pixi.js. En Phaser. <https://phaser.io/phaser-vs-pixi-js/> (argumenta que Phaser es una mejor opción que PixiJS para desarrollar juegos en la web)
-  CreateJS. (s.f.). EaselJS vs Pixi.js. En CreateJS. <https://createjs.com/easeljs-vs-pixi-js/> (argumenta que EaselJS es una mejor opción que PixiJS para desarrollar gráficos en la web)
```

Este formato utiliza diferentes niveles de encabezados jerárquicos para organizar el contenido de manera clara y concisa. ¡Espero que esto te sea útil! Si necesitas más ayuda, ¡no dudes en preguntar!

[[⚫🔴🟡🟢🔵⚪ (🔴②)]] | ①②③④⑤⑥ | ⚫① 🔴②  🟡 ③ 🟢④ 🔵⑤ ⚪⑥ 