---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-07T07:54:32.940Z
modified: 2024-05-03T21:38:11.467Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
---
# Dibujando formas geométricas básicas (Pyxel)

[[Aprender sobre Pyxel  ⚫①]]

En Pyxel, puedes dibujar formas geométricas básicas, como rectángulos, círculos y líneas, utilizando sus funciones de dibujo integradas. Aquí tienes una descripción de cómo dibujar algunas de estas formas:

1. **Rectángulos:**
   - Pyxel te permite dibujar rectángulos especificando las coordenadas de las esquinas superior izquierda e inferior derecha.
   - Puedes utilizar la función `rect()` para dibujar un rectángulo. Por ejemplo, para dibujar un rectángulo con una esquina superior izquierda en (x1, y1) y una esquina inferior derecha en (x2, y2):

   ```python
   pyxel.rect(x1, y1, x2, y2, color)
   ```

   Donde `x1` y `y1` son las coordenadas de la esquina superior izquierda, `x2` y `y2` son las coordenadas de la esquina inferior derecha, y `color` es el color del rectángulo.

2. **Círculos:**
   - Pyxel te permite dibujar círculos especificando el centro y el radio.
   - Puedes utilizar la función `circ()` para dibujar un círculo. Por ejemplo, para dibujar un círculo con centro en (x, y) y radio r:

   ```python
   pyxel.circ(x, y, r, color)
   ```

   Donde `x` y `y` son las coordenadas del centro del círculo, `r` es el radio del círculo y `color` es el color del círculo.

3. **Líneas:**
   - Pyxel te permite dibujar líneas especificando las coordenadas de los puntos inicial y final.
   - Puedes utilizar la función `line()` para dibujar una línea. Por ejemplo, para dibujar una línea desde el punto (x1, y1) hasta el punto (x2, y2):

   ```python
   pyxel.line(x1, y1, x2, y2, color)
   ```

   Donde `x1` y `y1` son las coordenadas del punto inicial, `x2` y `y2` son las coordenadas del punto final, y `color` es el color de la línea.

Estas son algunas de las formas básicas que puedes dibujar en Pyxel. Con estas funciones, puedes crear ilustraciones y gráficos simples para tus proyectos de pixel art. Experimenta con diferentes coordenadas y colores para crear las formas que necesites.