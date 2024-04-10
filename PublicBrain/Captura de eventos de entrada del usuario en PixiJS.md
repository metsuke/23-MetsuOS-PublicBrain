---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-08T04:10:16.772Z
modified: 2024-04-10T21:06:10.994Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
---
# Captura de eventos de entrada del usuario en PixiJS

[[Aprender sobre PixiJS]]

En PixiJS, la captura de eventos de entrada del usuario es fundamental para crear interacciones dinámicas en tus aplicaciones y juegos web. Aquí te explico cómo puedes capturar y manejar diferentes tipos de eventos de entrada del usuario:

### 1. Eventos de Mouse

PixiJS proporciona eventos de mouse para interactuar con los elementos visuales en el lienzo:

- **click:** Se dispara cuando se hace clic en un sprite.
- **mouseover:** Se dispara cuando el puntero del mouse entra en el área de un sprite.
- **mouseout:** Se dispara cuando el puntero del mouse sale del área de un sprite.
- **mousedown:** Se dispara cuando se presiona un botón del mouse sobre un sprite.
- **mouseup:** Se dispara cuando se suelta un botón del mouse que se ha presionado sobre un sprite.

Puedes capturar estos eventos utilizando el método `on`:

```javascript
sprite.on('click', () => {
    // Acciones a realizar cuando se hace clic en el sprite
});
```

### 2. Eventos de Teclado

También puedes capturar eventos de teclado en PixiJS:

- **keydown:** Se dispara cuando se presiona una tecla del teclado.
- **keyup:** Se dispara cuando se suelta una tecla del teclado.

```javascript
window.addEventListener('keydown', (event) => {
    // Acciones a realizar cuando se presiona una tecla del teclado
});
```

### 3. Coordenadas del Evento

Cuando manejas eventos de mouse, puedes acceder a las coordenadas del evento en relación con el lienzo o con el sprite que desencadenó el evento:

```javascript
sprite.on('click', (event) => {
    console.log('Coordenadas del mouse:', event.data.global.x, event.data.global.y);
});
```

### 4. Propagación de Eventos

Puedes detener la propagación de eventos en PixiJS para evitar que se propague a los elementos padre o hijos:

```javascript
sprite.on('click', (event) => {
    event.stopPropagation(); // Detiene la propagación del evento
});
```

Con estas técnicas, puedes capturar y manejar eventos de entrada del usuario en PixiJS para crear interacciones personalizadas y receptivas en tus aplicaciones y juegos web.