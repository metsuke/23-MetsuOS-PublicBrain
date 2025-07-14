---
iaStatus: 8
iaStatus_Model: Grok-3, Raúl Carrillo aka Metsuke
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.105Z
modified: 2025-07-13T22:47:38.051Z
supervisado: 2024-05-27T13:38:01.062Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 17
nav_primary: 
nav_secondary: 
tags:
---
# Dibujando formas básicas y gráficos (PixiJS) 🔴②

![Dibujando formas básicas y gráficos](PublicBrain/_resources/50ff92b24210175073c429285ad684dc_MD5.jpg)

 * [[Curso de PixiJS ⚫①]]
* [[Integrando PixiJS con MetsuOS I - Ejemplo de Inico 🟡③|<< Anterior]] | Siguiente >>

> WIP

PixiJS es una biblioteca de JavaScript para gráficos 2D que aprovecha WebGL para un renderizado rápido y eficiente, con Canvas como alternativa si WebGL no está disponible. Comenzaremos hoy con el dibujado de formas básicas

> Podeis encontrar los ejemplos del curso en [este repositorio de Github  🌐🟡③](https://github.com/metsuke/ejemplos-curso-pixijs-metsuos/tree/main)
## 1. Dibujando formas básicas con PIXI.Graphics

La clase `PIXI.Graphics` es ideal para crear formas primitivas como líneas, rectángulos, círculos o polígonos. Aquí tienes ejemplos prácticos para que los pongas en marcha. 

Como ya hemos instalado y configurado nuestra base de trabajo, este código lo crearemos directamente en nuestra aplicacion main.ts

### 1.1. Dibujar un rectángulo

Dibujamos un rectángulo rojo en la posición (50, 50) con un tamaño de 100x80 píxeles.

```javascript
const graphics = new PIXI.Graphics();
graphics.beginFill(0xff0000, 1); // Relleno rojo, opacidad completa
graphics.drawRect(50, 50, 100, 80); // Posición (x, y), ancho, alto
graphics.endFill();
app.stage.addChild(graphics);
```

### 1.2. Dibujar un círculo

Creamos un círculo verde centrado en (200, 200) con un radio de 50 píxeles.

```javascript
const graphics = new PIXI.Graphics();
graphics.beginFill(0x00ff00); // Relleno verde
graphics.drawCircle(200, 200, 50); // Centro (x, y), radio
graphics.endFill();
app.stage.addChild(graphics);
```

### 1.3. Dibujar una línea

Trazamos una línea azul de 4 píxeles de grosor desde (300, 50) hasta (400, 150).

```javascript
const graphics = new PIXI.Graphics();
graphics.lineStyle(4, 0x0000ff, 1); // Grosor, color azul, opacidad
graphics.moveTo(300, 50); // Punto inicial
graphics.lineTo(400, 150); // Punto final
app.stage.addChild(graphics);
```

### 1.4. Dibujar un polígono

Dibujamos un triángulo amarillo definido por tres vértices.

```javascript
const graphics = new PIXI.Graphics();
graphics.beginFill(0xffff00); // Relleno amarillo
graphics.drawPolygon([500, 50, 550, 150, 450, 150]); // Vértices del triángulo
graphics.endFill();
app.stage.addChild(graphics);
```

## 2. Combinando formas en un solo objeto Graphics

Para mejorar el rendimiento, puedes dibujar varias formas en un único objeto `PIXI.Graphics`.

```javascript
const graphics = new PIXI.Graphics();

// Rectángulo
graphics.beginFill(0xff0000);
graphics.drawRect(50, 50, 100, 80);
graphics.endFill();

// Círculo
graphics.beginFill(0x00ff00);
graphics.drawCircle(200, 200, 50);
graphics.endFill();

// Línea
graphics.lineStyle(4, 0x0000ff);
graphics.moveTo(300, 50);
graphics.lineTo(400, 150);

// Polígono
graphics.beginFill(0xffff00);
graphics.drawPolygon([500, 50, 550, 150, 450, 150]);
graphics.endFill();

app.stage.addChild(graphics);
```

## 3. Animando formas básicas

Puedes animar gráficos con el bucle `app.ticker`. Aquí, un círculo se mueve hacia la derecha y vuelve al inicio al salir del lienzo.

```javascript
const graphics = new PIXI.Graphics();
graphics.beginFill(0xff0000);
graphics.drawCircle(0, 0, 30);
graphics.endFill();
app.stage.addChild(graphics);

// Posición inicial
graphics.x = 100;
graphics.y = 100;

// Animación
app.ticker.add(() => {
    graphics.x += 2; // Mover a la derecha
    if (graphics.x > app.screen.width) graphics.x = 0; // Reiniciar
});
```

## 4. Añadiendo interactividad

Hacemos un rectángulo que cambia de color al hacer clic.

```javascript
const graphics = new PIXI.Graphics();
graphics.beginFill(0xff0000);
graphics.drawRect(50, 50, 100, 100);
graphics.endFill();

// Habilitar interactividad
graphics.interactive = true;
graphics.buttonMode = true; // Cursor de botón
graphics.on('pointerdown', () => {
    graphics.clear();
    graphics.beginFill(0x00ff00); // Cambiar a verde
    graphics.drawRect(50, 50, 100, 100);
    graphics.endFill();
});

app.stage.addChild(graphics);
```

## 5. Consejos prácticos para gráficos en PixiJS

- **Optimización**: Usa un solo `PIXI.Graphics` para varias formas si no necesitas controlarlas por separado; esto reduce la carga de renderizado.
- **Colores**: Usa colores en formato hexadecimal (0xRRGGBB) y ajusta la opacidad con `beginFill(color, alpha)`.
- **Interactividad**: Activa `graphics.interactive = true` y usa eventos como `pointerdown` para clics o `pointermove` para arrastrar.
- **Texturas**: Aplica texturas con `beginTextureFill` para efectos visuales más avanzados.
- **Depuración**: Prueba tus gráficos en herramientas como CodePen o Vite para experimentar rápidamente.

## Referencias bibliográficas

### Fuentes que apoyan el contenido

- [Repositorio de Github con los ejemplos del curso 🌐🟡③](https://github.com/metsuke/ejemplos-curso-pixijs-metsuos/tree/main)
- **PixiJS Documentation**. (2025). *PIXI.Graphics*. Disponible en: [https://pixijs.download/release/docs/PIXI.Graphics.html](https://pixijs.download/release/docs/PIXI.Graphics.html).  
  Explica en detalle la clase `PIXI.Graphics`, con métodos como `beginFill`, `drawRect` y `drawCircle`, esenciales para este curso.
- **Goodboy Digital**. (2025). *PixiJS Examples*. Disponible en: [https://pixijs.io/examples/](https://pixijs.io/examples/).  
  Muestra ejemplos prácticos de formas y animaciones, en línea con los ejemplos del curso.
- **YouTube: PixiJS Tutorials by Goodboy Digital**. (2023). *Getting Started with PixiJS*. Disponible en: [https://www.youtube.com/watch?v=7H3W7UXgKeY](https://www.youtube.com/watch?v=7H3W7UXgKeY).  
  Tutorial oficial que cubre el uso de `PIXI.Graphics` para dibujar formas.

### Fuentes que refutan o matizan el contenido

- **MDN Web Docs**. (2025). *CanvasRenderingContext2D*. Disponible en: [https://developer.mozilla.org/es/docs/Web/API/CanvasRenderingContext2D](https://developer.mozilla.org/es/docs/Web/API/CanvasRenderingContext2D).  
  PixiJS usa Canvas como respaldo, pero MDN señala que Canvas es más lento para gráficos complejos, lo que podría limitar el rendimiento en entornos sin WebGL.
- **WebGL Fundamentals**. (2025). *WebGL vs Canvas Performance*. Disponible en: [https://webglfundamentals.org/webgl/lessons/webgl-performance.html](https://webglfundamentals.org/webgl/lessons/webgl-performance.html).  
  Indica que WebGL, usado por PixiJS, puede requerir optimizaciones específicas, matizando la afirmación de "alto rendimiento" sin una configuración adecuada.
- **YouTube: GameFromScratch**. (2024). *PixiJS vs Phaser for 2D Game Development*. Disponible en: [https://www.youtube.com/watch?v=7I4qT7eBKrQ](https://www.youtube.com/watch?v=7I4qT7eBKrQ).  
  Compara PixiJS con Phaser, sugiriendo que Phaser podría ser mejor para ciertos juegos 2D, lo que cuestiona la elección de PixiJS para proyectos más avanzados.



![[Plantilla - 1MT#One More Thing]]