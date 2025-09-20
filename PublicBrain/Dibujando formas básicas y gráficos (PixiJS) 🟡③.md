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
modified: 2025-09-20T04:51:05.990Z
supervisado: 2024-05-27T13:38:01.062Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 20
nav_primary: 
nav_secondary: 
tags:
---
# Dibujando formas básicas y gráficos (PixiJS) 🟡③

![Dibujando formas básicas y gráficos](PublicBrain/_resources/50ff92b24210175073c429285ad684dc_MD5.jpg)

 * [[Curso de PixiJS ⚫①]]
* [[Integrando PixiJS con MetsuOS I - Ejemplo de Inico 🟡③|<< Anterior]] |  [[Carga y gestión de imágenes y texturas (PixiJS) 🔴②|Siguiente >>]]

PixiJS es una biblioteca de JavaScript para gráficos 2D que aprovecha WebGL para un renderizado rápido y eficiente, con Canvas como alternativa si WebGL no está disponible. Comenzaremos hoy con el dibujado de formas básicas

> Podeis encontrar los ejemplos del curso en [este repositorio de Github  🌐🟡③](https://github.com/metsuke/ejemplos-curso-pixijs-metsuos/tree/main)
## Dibujando formas básicas con PIXI.Graphics

La clase `PIXI.Graphics` es ideal para crear formas primitivas como líneas, rectángulos, círculos o polígonos. Aquí tienes ejemplos prácticos para que los pongas en marcha. 

Como ya hemos instalado y configurado nuestra base de trabajo, este código lo crearemos directamente en nuestra aplicacion main.ts

### Dibujar un rectángulo

Dibujamos un rectángulo rojo en la posición (50, 50) con un tamaño de 100x80 píxeles.

```javascript
const graphics = new PIXI.Graphics();
graphics.beginFill(0xff0000, 1); // Relleno rojo, opacidad completa
graphics.drawRect(50, 50, 100, 80); // Posición (x, y), ancho, alto
graphics.endFill();
app.stage.addChild(graphics);
```

### Dibujar un círculo

Creamos un círculo verde centrado en (200, 200) con un radio de 50 píxeles.

```javascript
const graphics = new PIXI.Graphics();
graphics.beginFill(0x00ff00); // Relleno verde
graphics.drawCircle(200, 200, 50); // Centro (x, y), radio
graphics.endFill();
app.stage.addChild(graphics);
```

### Dibujar una línea

Trazamos una línea azul de 4 píxeles de grosor desde (300, 50) hasta (400, 150).

```javascript
const graphics = new PIXI.Graphics();
graphics.lineStyle(4, 0x0000ff, 1); // Grosor, color azul, opacidad
graphics.moveTo(300, 50); // Punto inicial
graphics.lineTo(400, 150); // Punto final
app.stage.addChild(graphics);
```

### Dibujar un polígono

Dibujamos un triángulo amarillo definido por tres vértices.

```javascript
const graphics = new PIXI.Graphics();
graphics.beginFill(0xffff00); // Relleno amarillo
graphics.drawPolygon([500, 50, 550, 150, 450, 150]); // Vértices del triángulo
graphics.endFill();
app.stage.addChild(graphics);
```

## Combinando formas en un solo objeto Graphics

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

## Animando formas básicas

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

## Añadiendo interactividad

Hacemos un rectángulo que cambia de color al hacer clic.

```javascript
const graphics = new PIXI.Graphics();
graphics.beginFill(0xff0000);
graphics.drawRect(50, 50, 100, 100);
graphics.endFill();

// Habilitar interactividad
graphics.interactive = true;
graphics.cursor = 'pointer'; // Use cursor instead of buttonMode
graphics.on('pointerdown', () => {
    graphics.clear();
    graphics.beginFill(0x00ff00); // Cambiar a verde
    graphics.drawRect(50, 50, 100, 100);
    graphics.endFill();
});

app.stage.addChild(graphics);
```

## El ejemplo en acción

Con la tonteria, y siendo que he implementado lo descrito en un solo ejemplo a mi propio estilo (lo teneis en GitHub), tenemos ya nuestro primer juego (no accesible, no se puede jugar a ciegas, con dificultades motoras, tampoco), pero un juego (mierdijuego) al fin y al cabo :)

```pre
Instrucciones: pulse el circulo azul en movimiento para que sea verde, vuelva a pulsar para que retorne al azul ... ¿alguien necesita POKEs? xDD
```

Hale pues ya está, hasta aquí el curso... no no no jajajjaaj acabamos de empezar, ¡veamos donde nos lleva la madriguera de conejos!
**<div class='pixi-app' id='mos-formas-basicas'><div class='pixi-container'  id='pixi-container'></div></div><script type='text/javascript' id='PixiText' async src='https://metsuke.com/assets/apps/PixiJS/003-MosFormasGeometricas/app-mosformasgeometricas.iife.js'></script>**

Como ex-maquetador web (tengo unos años me ha dado tiempo a hacer reroll bastantes veces), me chirria el tema del "responsive" dentro del canvas, pero eso creo que tendré que investigarlo a fondo por si existe algo hecho, o acabar implementarndolo personalmente.
## Consejos prácticos para gráficos en PixiJS

- **Optimización**: Usa un solo `PIXI.Graphics` para varias formas si no necesitas controlarlas por separado; esto reduce la carga de renderizado.
- **Colores**: Usa colores en formato hexadecimal (0xRRGGBB) y ajusta la opacidad con `beginFill(color, alpha)`.
- **Interactividad**: Activa `graphics.interactive = true` y usa eventos como `pointerdown` para clics o `pointermove` para arrastrar.
- **Texturas**: Aplica texturas con `beginTextureFill` para efectos visuales más avanzados.
- **Depuración**: Prueba tus gráficos en herramientas como CodePen o Vite para experimentar rápidamente.

## Referencias bibliográficas

### Fuentes que apoyan el contenido

- Pruebas de campo en primera persona.
- [Repositorio de Github con los ejemplos del curso 🌐🟡③](https://github.com/metsuke/ejemplos-curso-pixijs-metsuos/tree/main)
- [PixiJS Documentation. (2025). PIXI.Graphics 🌐🟡③](https://api.pixijs.io/@pixi/graphics.html) - Explica en detalle la clase `PIXI.Graphics`, con métodos como `beginFill`, `drawRect` y `drawCircle`, esenciales para este curso.
- [Goodboy Digital (2025). PixiJS Examples 🌐🟡③](https://pixijs.com/8.x/examples/graphics/simple) - Muestra ejemplos prácticos de formas y animaciones, en línea con los ejemplos del curso.

### Fuentes que refutan o matizan el contenido

- **Ninguna fuente verificable disponible**.  

![[Plantilla - 1MT#One More Thing]]