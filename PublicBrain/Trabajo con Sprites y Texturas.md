---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:49:00.814Z
modified: 2024-04-14T14:29:03.226Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
---
# Trabajo con Sprites y Texturas

[[Aprender sobre PixiJS]]

Trabajar con sprites y texturas es una parte fundamental al utilizar PixiJS para crear juegos y aplicaciones interactivas. Los sprites son imágenes que pueden ser manipuladas y animadas en la pantalla, mientras que las texturas representan la imagen o patrón utilizados por los sprites. Aquí tienes una guía básica sobre cómo trabajar con sprites y texturas en PixiJS:

### Carga de texturas:

Antes de crear un sprite, primero necesitas cargar la textura que quieres utilizar. Puedes cargar texturas desde archivos de imagen, utilizando el cargador de recursos de PixiJS.

```javascript
const loader = PIXI.Loader.shared;

loader.add('nombre-textura', 'ruta/imagen.png')
      .load(cargarTexturas);

function cargarTexturas(loader, recursos) {
    // La textura está cargada y lista para ser utilizada
    const textura = recursos['nombre-textura'].texture;

    // Crear sprite usando la textura cargada
    const sprite = new PIXI.Sprite(textura);
    app.stage.addChild(sprite);
}
```

### Creación de sprites:

Una vez que la textura está cargada, puedes crear un sprite utilizando esa textura. Luego, puedes posicionar el sprite en la pantalla y ajustar sus propiedades según sea necesario.

```javascript
const sprite = new PIXI.Sprite(textura);

// Configurar la posición del sprite
sprite.x = 100;
sprite.y = 100;

// Escalar el sprite
sprite.scale.set(0.5, 0.5);

// Rotar el sprite
sprite.rotation = Math.PI / 4;

// Añadir el sprite al escenario
app.stage.addChild(sprite);
```

### Animación de sprites:

PixiJS facilita la animación de sprites cambiando su textura a lo largo del tiempo. Esto te permite crear animaciones fluidas utilizando una serie de imágenes (frames).

```javascript
// Crear un array de texturas para la animación
const frames = [];

for (let i = 1; i <= 5; i++) {
    const textura = PIXI.Texture.from(`frame${i}.png`);
    frames.push(textura);
}

// Crear un sprite de animación
const animacion = new PIXI.AnimatedSprite(frames);

// Configurar la velocidad de la animación
animacion.animationSpeed = 0.1;

// Reproducir la animación
animacion.play();

// Añadir el sprite de animación al escenario
app.stage.addChild(animacion);
```

### Texturas de texto:

Además de las imágenes, PixiJS te permite crear texturas a partir de texto, lo que te permite mostrar texto en tu juego o aplicación.

```javascript
const estiloTexto = new PIXI.TextStyle({
    fontFamily: 'Arial',
    fontSize: 24,
    fill: 'white'
});

const texto = new PIXI.Text('Hola mundo', estiloTexto);

// Posicionar el texto
texto.x = 100;
texto.y = 100;

// Añadir el texto al escenario
app.stage.addChild(texto);
```

Estos son algunos conceptos básicos sobre cómo trabajar con sprites y texturas en PixiJS. Con estas herramientas, puedes crear una variedad de juegos y aplicaciones interactivas con gráficos animados y texto dinámico.