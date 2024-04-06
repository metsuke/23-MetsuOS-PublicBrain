# Creación de la ventana del juego en Pyxel

[[Aprender sobre Pyxel]]

Para crear la ventana del juego en Pyxel, primero necesitas inicializar el entorno de juego y configurar algunos parámetros básicos, como el tamaño de la ventana y la paleta de colores. Aquí tienes un ejemplo básico de cómo puedes crear la ventana del juego en Pyxel:

```python
import pyxel

# Definir el tamaño de la ventana del juego
ANCHO_VENTANA = 160
ALTO_VENTANA = 120

# Inicializar el juego
pyxel.init(ANCHO_VENTANA, ALTO_VENTANA)

# Definir la paleta de colores
pyxel.palette = [
    0x000000, # Color negro
    0xFFFFFF, # Color blanco
    0xFF0000, # Color rojo
    0x00FF00, # Color verde
    0x0000FF  # Color azul
]

# Ejecutar el bucle principal del juego
pyxel.run()
```

En este ejemplo:

- Importamos el módulo `pyxel` que proporciona las funciones necesarias para crear juegos en Pyxel.
- Definimos las constantes `ANCHO_VENTANA` y `ALTO_VENTANA` para especificar las dimensiones de la ventana del juego.
- Inicializamos el juego utilizando la función `pyxel.init()` y pasando las dimensiones de la ventana como argumentos.
- Configuramos la paleta de colores utilizando la propiedad `pyxel.palette`, que toma una lista de valores hexadecimales RGB.
- Finalmente, ejecutamos el bucle principal del juego utilizando la función `pyxel.run()`, que se encarga de manejar la lógica del juego y actualizar la ventana de forma automática.

Al ejecutar este código, deberías ver una ventana de juego con el tamaño especificado y la paleta de colores definida. A partir de aquí, puedes comenzar a agregar más elementos a tu juego, como sprites, sonidos y lógica de juego.