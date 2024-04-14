---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-08T04:09:26.381Z
modified: 2024-04-14T14:29:03.552Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
---
# Interacción de Usuario y Eventos

[[Aprender sobre PixiJS]]

Por supuesto, en PixiJS, la interacción de usuario y los eventos son fundamentales para crear experiencias interactivas en aplicaciones y juegos web. Aquí te explico cómo puedes manejar la interacción del usuario y los eventos en PixiJS:

### 1. Eventos de Mouse

PixiJS proporciona una serie de eventos de mouse para interactuar con los elementos visuales en el lienzo:

- **click:** Se dispara cuando se hace clic en un sprite.
- **mouseover:** Se dispara cuando el puntero del mouse entra en el área de un sprite.
- **mouseout:** Se dispara cuando el puntero del mouse sale del área de un sprite.
- **mousedown:** Se dispara cuando se presiona un botón del mouse sobre un sprite.
- **mouseup:** Se dispara cuando se suelta un botón del mouse que se ha presionado sobre un sprite.

### 2. Eventos de Teclado

Además de los eventos de mouse, también puedes manejar eventos de teclado en PixiJS:

- **keydown:** Se dispara cuando se presiona una tecla del teclado.
- **keyup:** Se dispara cuando se suelta una tecla del teclado.

### 3. Manejo de Eventos

Para manejar eventos en PixiJS, puedes agregar listeners de eventos a los sprites y contenedores utilizando el método `on`:

```javascript
sprite.on('click', () => {
    // Acciones a realizar cuando se hace clic en el sprite
});

sprite.on('mouseover', () => {
    // Acciones a realizar cuando el puntero del mouse entra en el sprite
});

sprite.on('keydown', (event) => {
    // Acciones a realizar cuando se presiona una tecla del teclado
});
```

### 4. Coordenadas del Evento

Cuando manejas eventos de mouse, puedes acceder a las coordenadas del evento en relación con el lienzo o con el sprite que desencadenó el evento:

```javascript
sprite.on('click', (event) => {
    console.log('Coordenadas del mouse:', event.data.global.x, event.data.global.y);
});
```

### 5. Detención de la Propagación de Eventos

Puedes detener la propagación de eventos en PixiJS para evitar que se propague a los elementos padre o hijos:

```javascript
sprite.on('click', (event) => {
    event.stopPropagation(); // Detiene la propagación del evento
});
```

Con estas técnicas, puedes crear fácilmente interacciones de usuario dinámicas y receptivas en tus aplicaciones y juegos web desarrollados con PixiJS.