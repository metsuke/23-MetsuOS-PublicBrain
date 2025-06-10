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
created: 2024-04-08T04:10:16.772Z
modified: 2025-06-10T21:14:03.041Z
supervisado: 2024-05-27T13:38:12.936Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 8
nav_primary: 
nav_secondary: 
tags:
---
# Captura de eventos de entrada del usuario en PixiJS 🔴②

[[Curso de PixiJS ⚫①]]

En el desarrollo de aplicaciones y juegos web con PixiJS, la captura de eventos de entrada del usuario es fundamental para crear experiencias dinámicas y atractivas. En este artículo, exploraremos cómo capturar y manejar diferentes tipos de eventos de entrada del usuario en PixiJS.

## 1. Eventos de Mouse

PixiJS proporciona una variedad de eventos de mouse para interactuar con los elementos visuales en el lienzo. Estos eventos permiten responder a las acciones del usuario, como clics, movimientos del mouse y más.

### Eventos de mouse disponibles

* **click:** Se dispara cuando se hace clic en un sprite.
* **mouseover:** Se dispara cuando el puntero del mouse entra en el área de un sprite.
* **mouseout:** Se dispara cuando el puntero del mouse sale del área de un sprite.
* **mousedown:** Se dispara cuando se presiona un botón del mouse sobre un sprite.
* **mouseup:** Se dispara cuando se suelta un botón del mouse que se ha presionado sobre un sprite.

Para capturar estos eventos, puedes utilizar el método `on` de PixiJS:
```javascript
sprite.on('click', () => {
    // Acciones a realizar cuando se hace clic en el sprite
});
```

## 2. Eventos de Teclado

Además de los eventos de mouse, PixiJS también permite capturar eventos de teclado. Estos eventos permiten responder a las entradas del usuario a través del teclado.

### Eventos de teclado disponibles

* **keydown:** Se dispara cuando se presiona una tecla del teclado.
* **keyup:** Se dispara cuando se suelta una tecla del teclado.

Para capturar estos eventos, puedes utilizar el método `addEventListener` de JavaScript:
```javascript
window.addEventListener('keydown', (event) => {
    // Acciones a realizar cuando se presiona una tecla del teclado
});
```

## 3. Coordenadas del Evento

Cuando manejas eventos de mouse, puedes acceder a las coordenadas del evento en relación con el lienzo o con el sprite que desencadenó el evento. Esto te permite obtener información precisa sobre la posición del mouse en el momento del evento.

```javascript
sprite.on('click', (event) => {
    console.log('Coordenadas del mouse:', event.data.global.x, event.data.global.y);
});
```
## 4. Propagación de Eventos

En algunos casos, es posible que desees detener la propagación de eventos en PixiJS para evitar que se propague a los elementos padre o hijos. Puedes lograr esto utilizando el método `stopPropagation` del objeto `event`.

```javascript
sprite.on('click', (event) => {
    event.stopPropagation(); // Detiene la propagación del evento
});
```

Con estas técnicas, podrás capturar y manejar eventos de entrada del usuario en PixiJS para crear interacciones personalizadas y receptivas en tus aplicaciones y juegos web.

## Referencias bibliográficas

* PixiJS. (s.f.). _Event System_. Recuperado de <https://pixijs.download/release/docs/PIXI.EventSystem.html>
* Mozilla. (s.f.). _EventTarget.addEventListener()_. Recuperado de <https://developer.mozilla.org/es/docs/Web/API/EventTarget/addEventListener>

## Referencias que refutan

* Phaser. (s.f.). _Input_. Recuperado de <https://phaser.io/phaser/docs/3.50.1/Phaser.Input.InputPlugin> (Phaser es un framework de juego que ofrece una forma diferente de manejar eventos de entrada del usuario)
* CreateJS. (s.f.). _EaselJS_. Recuperado de <https://createjs.com/easeljs/> (EaselJS es un framework de gráficos que ofrece una forma diferente de manejar eventos de entrada del usuario)

![[⚫🔴🟡🟢🔵⚪ (🔴②)#Sobre el sistema de validez de un contenido en MetsuOS]]