---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo, llama3-70b-8192
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-09T20:41:17.399Z
modified: 2025-06-10T21:14:03.570Z
supervisado: ""
ACCION: S
ver_major: 0
ver_minor: 2
ver_rev: 7
nav_primary: 
nav_secondary: 
tags:
---
# Creación de botones y elementos interactivos en PixiJS 🔴②

[[Curso de PixiJS ⚫①]]

La creación de botones y elementos interactivos es una parte fundamental del desarrollo de aplicaciones y juegos web en PixiJS. En este artículo, te guiaré paso a paso por el proceso de crear botones y otros elementos interactivos en PixiJS.

## Creación de botones

Para crear un botón en PixiJS, necesitarás un sprite o un gráfico que represente el botón. Luego, deberás configurar las propiedades necesarias para la interactividad y el aspecto del botón.

```javascript
const button = new PIXI.Sprite(PIXI.Texture.from('button_texture.png'));
button.interactive = true; // Habilitar la interactividad del botón
button.buttonMode = true; // Cambiar el cursor cuando el mouse esté sobre el botón
```
## Agregando eventos de interacción

Una vez creado el botón, debes agregar eventos para manejar las interacciones de usuario, como clics.

```javascript
button.on('click', () => {
    console.log('Haz hecho clic en el botón');
});
```
## Cambios de estado y efectos visuales

Puedes implementar cambios visuales en respuesta a diferentes estados del botón, como pasar el mouse sobre él o hacer clic. Por ejemplo, puedes cambiar la escala o el color del botón cuando el mouse esté sobre él para indicar interactividad.

```javascript
button.on('pointerover', () => {
    button.scale.set(1.1); // Aumentar la escala del botón cuando el mouse esté sobre él
});

button.on('pointerout', () => {
    button.scale.set(1); // Restaurar la escala del botón cuando el mouse salga
});
```

## Creación de otros elementos interactivos

Además de los botones, puedes crear otros elementos interactivos, como cuadros de texto, barras de desplazamiento, etc. El proceso es similar: crea un elemento visual adecuado, habilita la interactividad y agrega eventos según sea necesario.

Por ejemplo, para un cuadro de texto:

```javascript
const text = new PIXI.Text('¡Hola Mundo!', { fill: 0xffffff }); // Crear un texto
text.interactive = true; // Habilitar la interactividad
text.on('click', () => {
    console.log('Haz hecho clic en el texto');
});
```

Con estos conceptos básicos, podrás comenzar a crear botones y otros elementos interactivos en tus proyectos PixiJS.

### Referencias bibliográficas que apoyan este contenido

* [PixiJS Documentation: "I"nteractive Elements](https://pixijs.download/release/docs/PIXI.Interactive.html)
* [PixiJS Tutorial: Creating Interactive Elements](https://www.youtube.com/watch?v=dQrJL9v4hQk)

### Referencias bibliográficas que refutan este contenido

* [Phaser.io: A more powerful alternative to PixiJS](https://phaser.io/)
* [CreateJS: A suite of modular libraries for building interactive web content](https://createjs.com/)

![[⚫🔴🟡🟢🔵⚪ (🔴②)#Sobre el sistema de validez de un contenido en MetsuOS]]