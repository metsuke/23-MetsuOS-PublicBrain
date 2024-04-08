---
iaStatus: 0
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-08-30T00:54:00
modified: 2024-03-06T23:35:00
ver_major: 0
ver_minor: "0"
ver_rev: "0"
nav_primary: []
nav_secondary: []
tags: []
---
# Uso de paletas de colores y modos de mezcla en Pyxel

[[Aprender sobre Pyxel]]

En Pyxel, el uso de paletas de colores y modos de mezcla es esencial para dar estilo y crear efectos visuales interesantes en tus proyectos de pixel art. Aquí te explico cómo puedes utilizar paletas de colores y modos de mezcla en Pyxel:

### 1. Paletas de Colores

Una paleta de colores en Pyxel es un conjunto predefinido de colores que puedes usar para dibujar y pintar en tu lienzo. Pyxel permite cargar y gestionar paletas de colores personalizadas para tu proyecto. Puedes seleccionar los colores de tu paleta y utilizarlos de manera consistente en tu diseño para mantener una apariencia coherente.

```python
pyxel.image(0).load_palette(0, ["#000000", "#ffffff", "#ff0000", "#00ff00", "#0000ff"])  # Cargar una paleta de colores
```

En este ejemplo, se carga una paleta de colores con cinco colores diferentes. Puedes referenciar estos colores por su índice al dibujar en el lienzo.

### 2. Modos de Mezcla

Los modos de mezcla en Pyxel controlan cómo se combinan los colores al dibujar sobre el lienzo. Pyxel admite varios modos de mezcla, como `NORMAL`, `ADD`, `MULT`, `SCREEN`, `LIGHTEN`, entre otros. Puedes establecer el modo de mezcla utilizando el método `set`:

```python
pyxel.image(0).set(0, 0, image=0, u=0, v=0, w=16, h=16, colkey=1, blend=0)  # Establecer el modo de mezcla
```

En este ejemplo, se establece el modo de mezcla del sprite en el banco de imágenes número 0 en el modo `NORMAL`. Puedes experimentar con diferentes modos de mezcla para lograr efectos visuales únicos en tu proyecto.

### 3. Dibujar con Paletas y Modos de Mezcla

Una vez que hayas cargado una paleta de colores y establecido un modo de mezcla, puedes comenzar a dibujar en el lienzo utilizando los colores de la paleta y aplicando el modo de mezcla deseado:

```python
pyxel.rect(0, 0, 32, 32, 1)  # Dibujar un rectángulo con el color en el índice 1 de la paleta
pyxel.line(0, 0, 64, 64, 2)  # Dibujar una línea con el color en el índice 2 de la paleta
```

En este ejemplo, `rect` y `line` se utilizan para dibujar formas con colores específicos de la paleta. El modo de mezcla establecido anteriormente afectará cómo se combinan estos colores con los colores existentes en el lienzo.

Con el uso creativo de paletas de colores y modos de mezcla, puedes crear arte pixelado y efectos visuales únicos en tus proyectos de Pyxel. Experimenta con diferentes combinaciones de colores y modos de mezcla para lograr el estilo visual deseado.