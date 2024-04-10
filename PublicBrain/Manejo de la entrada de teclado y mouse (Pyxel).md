---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-10T10:23:02.163Z
modified: 2024-04-10T10:26:48.075Z
ver_major: 0
ver_minor: 1
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# Manejo de la entrada de teclado y mouse (Pyxel)

[[Aprender sobre Pyxel]]

En Pyxel, el manejo de la entrada de teclado y mouse es fundamental para interactuar con tus aplicaciones y juegos. Pyxel ofrece funciones integradas para manejar la entrada de teclado y mouse de manera sencilla. Aquí te muestro cómo puedes hacerlo:

### Manejo de la entrada de teclado:

```python
import pyxel

class Juego:
    def __init__(self):
        pyxel.init(160, 120)
        self.x = 80
        self.y = 60
        pyxel.run(self.actualizar, self.dibujar)

    def actualizar(self):
        if pyxel.btn(pyxel.KEY_LEFT):
            self.x -= 1
        elif pyxel.btn(pyxel.KEY_RIGHT):
            self.x += 1
        if pyxel.btn(pyxel.KEY_UP):
            self.y -= 1
        elif pyxel.btn(pyxel.KEY_DOWN):
            self.y += 1

    def dibujar(self):
        pyxel.cls(0)
        pyxel.rect(self.x, self.y, 8, 8, 7)

Juego()
```

En este ejemplo, cada vez que presionas una tecla de flecha (izquierda, derecha, arriba, abajo), la posición del rectángulo se actualiza en consecuencia.

### Manejo de la entrada de mouse:

```python
import pyxel

class Juego:
    def __init__(self):
        pyxel.init(160, 120)
        self.x = 80
        self.y = 60
        pyxel.mouse(True)
        pyxel.run(self.actualizar, self.dibujar)

    def actualizar(self):
        if pyxel.btn(pyxel.MOUSE_LEFT_BUTTON):
            self.x, self.y = pyxel.mouse_x, pyxel.mouse_y

    def dibujar(self):
        pyxel.cls(0)
        pyxel.rect(self.x, self.y, 8, 8, 7)

Juego()
```

En este ejemplo, cuando presionas el botón izquierdo del mouse, la posición del rectángulo se actualiza a la posición actual del mouse.

Estos son solo ejemplos básicos de cómo puedes manejar la entrada de teclado y mouse en Pyxel. Puedes combinar estas funciones con la lógica de tu juego o aplicación para crear interacciones más complejas y atractivas. Además, Pyxel ofrece otras funciones útiles para manejar la entrada de teclado y mouse, como detectar eventos de pulsación de teclas específicas o restringir la entrada del mouse a ciertas áreas de la pantalla.