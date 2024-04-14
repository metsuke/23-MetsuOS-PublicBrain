---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-08T04:16:26.504Z
modified: 2024-04-14T14:29:03.850Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
---
# Creación de animaciones simples en Pyxel

[[Aprender sobre Pyxel]]

En Pyxel, la creación de animaciones simples es una parte importante para dar vida a tus proyectos de pixel art. Aquí te explico cómo puedes crear animaciones básicas en Pyxel:

### 1. Preparación de los Sprites

Antes de crear una animación, asegúrate de haber cargado todos los sprites necesarios en el banco de imágenes de Pyxel utilizando el método `load`. Por ejemplo:

```python
pyxel.image(0).load(0, 0, "sprite1.png")  # Cargar el primer sprite
pyxel.image(1).load(0, 0, "sprite2.png")  # Cargar el segundo sprite
# ...
```

### 2. Definición de la Animación

Para definir una animación, necesitas especificar qué sprites se mostrarán en cada cuadro de la animación y durante cuántos cuadros se mostrará cada sprite. Puedes hacer esto utilizando la función `play()`:

```python
def __init__(self):
    pyxel.play(0, [0, 1, 2, 1], loop=True)  # Reproducir la animación con los sprites 0, 1, 2, 1
```

En este ejemplo, `[0, 1, 2, 1]` especifica los índices de los sprites que se mostrarán en cada cuadro de la animación, y `loop=True` indica que la animación se repetirá continuamente.

### 3. Actualización y Dibujo

En el bucle principal de tu programa, debes actualizar y dibujar la animación en cada cuadro. Puedes hacer esto en las funciones `update()` y `draw()`:

```python
def update(self):
    pass  # No se necesita ninguna actualización explícita para la animación

def draw(self):
    pyxel.cls(0)  # Limpiar la pantalla
    pyxel.blt(100, 100, 0, 0, 0, 16, 16)  # Mostrar el sprite actual de la animación
```

En este ejemplo, `blt` se utiliza para mostrar el sprite actual de la animación en la posición (100, 100) de la pantalla.

### 4. Control de la Velocidad de la Animación

Puedes controlar la velocidad de la animación ajustando el valor de la propiedad `fps` en Pyxel:

```python
pyxel.init(160, 120, fps=30)  # Inicializar Pyxel con una velocidad de fotogramas de 30 cuadros por segundo
```

Esto establecerá la velocidad de la animación en 30 cuadros por segundo, pero puedes ajustar este valor según tus necesidades.

Con estos pasos, puedes crear animaciones simples en Pyxel para dar movimiento y vida a tus proyectos de pixel art. Experimenta con diferentes sprites y secuencias de animación para crear efectos visuales interesantes y cautivadores.