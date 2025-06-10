---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-11T11:30:38.163Z
modified: 2025-06-10T21:14:03.971Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 5
nav_primary: []
nav_secondary: []
tags: []
---
# Creación y gestión de escenas en PixiJS

[[Curso de PixiJS ⚫①]]

En PixiJS, las escenas son entornos independientes donde se muestran los elementos gráficos y se manejan las interacciones del usuario. La creación y gestión de escenas son fundamentales para desarrollar juegos y aplicaciones interactivas. Aquí te explico cómo puedes crear y gestionar escenas en PixiJS:

### 1. Creación de una escena:
Para crear una nueva escena en PixiJS, puedes utilizar la clase `PIXI.Container`, que actúa como un contenedor para los elementos gráficos de la escena. Aquí tienes un ejemplo de cómo crear una nueva escena:

```javascript
// Crear una nueva escena
let escena = new PIXI.Container();
```

### 2. Agregar elementos a la escena:
Una vez que has creado una escena, puedes agregar elementos gráficos como sprites, formas geométricas o texto a la escena utilizando los métodos de la clase `PIXI.Container`, como `addChild()`. Por ejemplo:

```javascript
// Crear un sprite
let sprite = PIXI.Sprite.from('imagen.png');

// Agregar el sprite a la escena
escena.addChild(sprite);
```

### 3. Renderizado de la escena:
Después de crear la escena y agregar elementos a ella, necesitas renderizarla en el lienzo utilizando el renderizador de PixiJS. Esto generalmente se hace en un bucle de animación o de juego para actualizar y mostrar la escena en la pantalla. Aquí tienes un ejemplo básico de cómo renderizar una escena:

```javascript
// Crear un nuevo renderizador
let renderizador = PIXI.autoDetectRenderer({
    width: 800,
    height: 600,
    antialias: true,
    transparent: false,
    resolution: 1
});

// Agregar el lienzo al DOM
document.body.appendChild(renderizador.view);

// Función de animación del juego
function animar() {
    requestAnimationFrame(animar);
    
    // Renderizar la escena
    renderizador.render(escena);
}

// Iniciar la animación
animar();
```

### 4. Gestión de múltiples escenas:
En muchos casos, es posible que necesites gestionar múltiples escenas en tu aplicación o juego. Puedes hacerlo creando varias instancias de la clase `PIXI.Container` y alternando entre ellas según sea necesario. Por ejemplo, podrías tener una escena para el menú principal, otra para el juego en sí y otra para la pantalla de puntuación. Simplemente renderiza la escena activa en cada cuadro de animación.

```javascript
// Crear múltiples escenas
let escenaMenu = new PIXI.Container();
let escenaJuego = new PIXI.Container();
let escenaPuntuacion = new PIXI.Container();

// Función para cambiar de escena
function cambiarEscena(nuevaEscena) {
    escena.visible = false;
    nuevaEscena.visible = true;
    escena = nuevaEscena;
}

// Renderizar la escena activa
renderizador.render(escena);
```

Con estos pasos, puedes crear y gestionar escenas de manera efectiva en PixiJS, lo que te permite desarrollar juegos y aplicaciones interactivas más complejos y organizados.