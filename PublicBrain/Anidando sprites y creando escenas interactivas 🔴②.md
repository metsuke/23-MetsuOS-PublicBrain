---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo, llama3-70b-8192
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: -3
lang: ES
translations: 
created: 2024-04-07T07:47:38.862Z
modified: 2024-05-27T13:37:59.469Z
supervisado: 2024-05-19T19:27:24.575Z
ACCION: 
ver_major: 0
ver_minor: 5
ver_rev: 6
nav_primary: 
nav_secondary: 
tags:
---
# Anidando sprites y creando escenas interactivas 🔴②

[[Aprender sobre PixiJS ⚫①]]

### Anidando Sprites
### Anidar sprites significa colocar un sprite dentro de otro, lo que te permite crear jerarquías de objetos visuales más complejas.

Anidar sprites significa colocar un sprite dentro de otro, lo que te permite crear jerarquías de objetos visuales más complejas. Por ejemplo, puedes anidar un sprite de un personaje dentro de un sprite de fondo para crear una escena más elaborada.

```javascript
// Crear sprites
const fondoSprite = PIXI.Sprite.from('ruta/al/fondo.png');
const personajeSprite = PIXI.Sprite.from('ruta/al/personaje.png');

// Añadir el personaje como hijo del fondo
fondoSprite.addChild(personajeSprite);

// Añadir el fondo al escenario
app.stage.addChild(fondoSprite);
```

En este ejemplo, el sprite del personaje se convierte en un hijo del sprite de fondo, lo que significa que se moverá junto con el fondo si el fondo se mueve.

## Creación de Escenas Interactivas
### PixiJS proporciona herramientas para crear escenas interactivas, lo que permite a los usuarios interactuar con los elementos visuales de la aplicación o juego.

PixiJS proporciona herramientas para crear escenas interactivas, lo que permite a los usuarios interactuar con los elementos visuales de la aplicación o juego. Puedes hacer que los sprites respondan a eventos del mouse o del teclado, como clics, movimientos y pulsaciones de teclas.

```javascript
// Hacer un sprite interactivo
sprite.interactive = true;

// Añadir un evento de clic al sprite
sprite.on('pointerdown', () => {
  console.log('El sprite ha sido clickeado');
});
```

En este ejemplo, `sprite.interactive = true` habilita la interactividad para el sprite, mientras que `sprite.on('pointerdown', ...)` agrega un evento de clic al sprite que imprime un mensaje en la consola cuando se hace clic en él.

## Manejo de Eventos
### PixiJS proporciona varios eventos que puedes usar para responder a la interacción del usuario.

PixiJS proporciona varios eventos que puedes usar para responder a la interacción del usuario. Algunos de los eventos comunes incluyen `'pointerdown'`, `'pointerup'`, `'pointermove'` para eventos de mouse, y `'keydown'`, `'keyup'` para eventos de teclado.

```javascript
// Añadir un evento de movimiento de ratón al sprite
sprite.on('pointermove', (evento) => {
  console.log(`Posición del mouse: ${evento.data.global.x}, ${evento.data.global.y}`);
});
```

En este ejemplo, el evento `'pointermove'` se activa cuando el mouse se mueve sobre el sprite, y se imprime la posición del mouse en la consola.

## Referencias bibliográficas

* PixiJS Documentation: <https://pixijs.com/docs/>
* PixiJS Tutorials: <https://pixijs.com/tutorials/>

## Referencias que refutan el contenido

* No se han encontrado referencias que refuten el contenido presentado.

Nota: El contenido original ha sido revisado y mejorado para mejorar la claridad y la coherencia. Se han agregado encabezados jerárquicos para facilitar la lectura y se ha incluido una sección de referencias bibliográficas y otra que refuta el contenido.

![[⚫🔴🟡🟢🔵⚪ (🔴②)#Sobre el sistema de validez de un contenido en MetsuOS]]