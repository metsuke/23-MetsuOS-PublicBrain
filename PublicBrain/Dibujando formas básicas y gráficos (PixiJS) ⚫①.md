---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.105Z
modified: 2024-05-03T21:34:33.323Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
---
# Dibujando formas básicas y gráficos (PixiJS) ⚫①

[[Aprender sobre PixiJS ⚫①]]

En PixiJS, puedes dibujar formas básicas y gráficos utilizando la clase `Graphics`. Esta clase te permite crear y manipular gráficos vectoriales en tu lienzo. Aquí te muestro cómo puedes dibujar algunas formas básicas y gráficos con PixiJS:

1. **Dibujar un rectángulo:**
   
   Puedes dibujar un rectángulo utilizando el método `drawRect` de la clase `Graphics`. Por ejemplo:
   ```javascript
   const graphics = new PIXI.Graphics();

   // Dibujar un rectángulo
   graphics.beginFill(0xFF0000); // Color rojo
   graphics.drawRect(50, 50, 100, 100); // (x, y, ancho, alto)
   graphics.endFill();

   app.stage.addChild(graphics);
   ```

2. **Dibujar un círculo:**

   Para dibujar un círculo, puedes utilizar el método `drawCircle` de la clase `Graphics`. Por ejemplo:
   ```javascript
   const graphics = new PIXI.Graphics();

   // Dibujar un círculo
   graphics.beginFill(0x00FF00); // Color verde
   graphics.drawCircle(200, 200, 50); // (x, y, radio)
   graphics.endFill();

   app.stage.addChild(graphics);
   ```

3. **Dibujar una línea:**

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

4. **Dibujar un polígono:**

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

Estos son solo algunos ejemplos de cómo puedes dibujar formas básicas y gráficos utilizando PixiJS. Puedes combinar estas técnicas para crear gráficos más complejos y experiencias visuales interactivas en tu aplicación web.

[[⚫🔴 🟡 🟢 🔵⚪ (🔴②)]] | ①②③④⑤⑥ | ⚫① 🔴②  🟡 ③ 🟢④ 🔵⑤ ⚪⑥ 