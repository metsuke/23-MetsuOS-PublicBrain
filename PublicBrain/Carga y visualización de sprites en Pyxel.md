---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-08T04:13:21.621Z
modified: 2024-04-14T14:29:03.871Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
---
# Carga y visualización de sprites en Pyxel

[[Aprender sobre Pyxel]]

En Pyxel, la carga y visualización de sprites es un aspecto esencial para crear gráficos y animaciones en tus proyectos de pixel art. Aquí te explico cómo cargar y mostrar sprites en Pyxel:

### 1. Carga de Sprites

Pyxel permite cargar sprites desde archivos de imagen en formatos compatibles, como PNG o GIF. Puedes cargar sprites utilizando el método `load`:

```python
pyxel.image(0).load(0, 0, "assets/sprite.png")
```

En este ejemplo, el método `load` carga el sprite ubicado en el archivo "sprite.png" en la posición (0, 0) del banco de imágenes número 0.

### 2. Visualización de Sprites

Una vez que hayas cargado el sprite, puedes mostrarlo en la pantalla utilizando el método `blt` (block transfer):

```python
pyxel.blt(100, 100, 0, 0, 0, 16, 16)
```

En este ejemplo, `blt` muestra el sprite del banco de imágenes número 0 en la posición (100, 100) de la pantalla. Los parámetros `(0, 0)` indican la posición del sprite en el banco de imágenes, y `(16, 16)` especifican el ancho y alto del sprite en píxeles.

### 3. Animación de Sprites

Para crear animaciones con sprites, puedes cambiar dinámicamente la posición del sprite en el banco de imágenes en cada cuadro de la animación. Por ejemplo, puedes alternar entre diferentes cuadros de un sprite para simular un movimiento o una acción:

```python
frame = 0

def update():
    global frame
    frame = (frame + 1) % 4  # Cambia entre 4 cuadros de animación

def draw():
    pyxel.cls(0)  # Limpia la pantalla
    pyxel.blt(100, 100, 0, frame * 16, 0, 16, 16)  # Muestra el cuadro de animación actual
```

En este ejemplo, la variable `frame` se actualiza en cada cuadro del juego, y `blt` muestra el cuadro correspondiente del sprite en función del valor de `frame`.

Con estas técnicas, puedes cargar, visualizar y animar sprites en Pyxel para crear gráficos y animaciones impresionantes en tus proyectos de pixel art.