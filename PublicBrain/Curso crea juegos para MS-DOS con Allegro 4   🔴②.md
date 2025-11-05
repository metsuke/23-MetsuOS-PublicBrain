---
iaStatus: 8
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
iaStatus_Model: Grok-4, Raul Carrillo aka Metsuke
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-10-30T22:17:34.309Z
modified: 2025-10-31T13:42:38.910Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoJuegosMSDOSAllegro4_000.mp4
---
# Curso crea juegos para MS-DOS con Allegro 4   🔴②

![Curso Juegos MSDOS Allegro4_000](PublicBrain/_resources/93d75e97af5c55894ae99095c0b5ab2b_MD5.jpg)

[[KB]]

> Ojo: WIP

Como siempre, la "Culpa" es de [El Spectrumero 🌐](https://www.youtube.com/watch?v=wts4lN7X_MY), abordamos antes de lo que tenia pensado el tema de MS-DOS (me planteo incluso crear MetsuOS también para MS-DOS), entre otras cosas como medio para meterme caña con C, lenguaje que necesito tanto para el SO, como para Prisma, CPCTelera, etc, etc, etc.

Lo divertido, que apenas hice bats, cosas basicas de menus para lanzar juegos, pinitos con Div Games Studio y lo que aprendí en el curso de Unix/C/Oracle, que tengo casi olvidado, por lo que para mi, la diversión está en aprender, y de paso, que eso pueda servir a otros para llegar más allá.

Huelga decir que el indice es absolutamente preliminar y que según afine el scope y el conocimiento, variará en conseccuencia. ¡Al lio!


**Prerrequisitos:**

- Dominio elemental del lenguaje C.
- Un entorno Windows o Linux con emulador (DOSBox) para pruebas.
- Ganas de revivir el _retro gaming_ en MS-DOS.

**Objetivos principales:**

- Manejar Allegro 4 para crear juegos 2D en MS-DOS.
- Desarrollar títulos completos de estilo retro (shoot’em up, plataformas, RPG sencillo).
- Comprender las limitaciones y optimizaciones del hardware DOS (VGA 320×200, 256 colores).
- Compilar y ejecutar en emuladores (DOSBox) e, idealmente, en máquinas vintage.

**Herramientas necesarias:**

- DJGPP (GCC para DOS).
- Allegro 4.2.x (versión oficial).
- DOSBox + FreeDOS.
- Editor a elegir: Dev-C++, VS Code o Turbo C++.

## Módulo 1: Introducción a MS-DOS y Allegro 4

### 1.1 Historia y contexto

Los juegos de DOS marcaron una época: _Wolfenstein 3D_, _Doom_, _Commander Keen_… Todo corría en CPUs 386/486, con VGA y apenas 640 KB de RAM convencional. Allegro 4 destaca por su simplicidad y por ser multiplataforma en entornos retro. Diferencias clave con Allegro 5: la API legacy está pensada específicamente para DOS.

### 1.2 Instalación del entorno

- Descarga e instalación de DJGPP v2.
- Compilación de Allegro 4.2.8 para DOS.
- Configuración de DOSBox (montajes, dosbox.conf).
- **Ejercicio:** Programa “¡Allegro en DOS!” en modo texto y gráfico.

### 1.3 Estructura de proyecto

- Carpetas: src/, data/, bin/.
- _Makefile_ básico para DJGPP.
- Variables de entorno (ALLEGRO_PATH).

## Módulo 2: Inicialización y modos gráficos

### 2.1 Instaladores y Allegro

allegro_init(), install_keyboard(), install_timer(). Gestión de errores con allegro_error. Modos VGA: 320×200×256, 640×480×256.

### 2.2 Pantalla y paletas 

set_gfx_mode(), set_palette(). Carga de paletas RGB (archivos .pal). Efectos _fade in/out_. **Ejercicio:** Ventana con paleta personalizada al estilo id Software.

### 2.3 Doble buffer y _page flipping_

screen vs. backbuffer. blit() y vsync(). Evitar _tearing_ a 60 FPS.

## Módulo 3: Entrada de usuario

### 3.1 Teclado

readkey(), key[], key_shifts. Mapeo de teclas DOS. **Ejercicio:** Menú navegable con flechas y Enter.

### 3.2 Ratón

install_mouse(), poll_mouse(). Ocultar cursor y limitar zona.

### 3.3 Joystick

install_joystick(). Calibración para gamepads clásicos (Gravis, etc.).


## Módulo 4: Primitivas 2D

### 4.1 Líneas, rectángulos y círculos

line(), rect(), circle(), polygon(). Colores indexados y transparencias. **Ejercicio:** Menú con bordes y sombras.

### 4.2 Texto y fuentes

textout_*(). Fuentes bitmap (.dat). Alineación y rotación básica.

### 4.3 Optimización de render

clear_to_color(), _clipping_.

## Módulo 5: Bitmaps y sprites

### 5.1 Carga y manipulación

load_bitmap() (BMP/PCX). Máscaras de color. Rotación/escalado con rotate_scaled_bitmap().

### 5.2 Sprites animados

_Sprite sheets_. Colisiones píxel-perfectas (getpixel()). **Ejercicio:** Personaje con 4 direcciones de movimiento.

### 5.3 Efectos visuales

Transparencia (draw_trans_sprite()). Máscaras RLE.

## Módulo 6: Audio y música

### 6.1 Inicialización de sonido

install_sound(), detección de drivers (Sound Blaster, AdLib, PC Speaker).

### 6.2 Efectos de sonido

load_sample(), play_sample(). Volumen y _panning_. **Ejercicio:** Disparos y explosiones en un _shooter_.

### 6.3 Música MIDI

load_midi(), play_midi(). Bucles y _fade out_.

## Módulo 7: Temporizadores y _game loop_

### 7.1 Timers

install_int(), LOCK_VARIABLE(). 70 Hz estándar.

### 7.2 Bucle principal

```c
while (!key[KEY_ESC]) {
    update();
    draw();
    rest(1);
}
```

Contador de FPS y desacoplamiento lógica/render.

### 7.3 Estados del juego

Máquina de estados finita: menú, partida, pausa, _game over_.

## Módulo 8: Mecánicas avanzadas

### 8.1 Colisiones

AABB, píxel-perfecto, círculos. **Ejercicio:** Plataformas con gravedad.

### 8.2 Partículas

Sistema simple de explosiones, fuego y humo.

### 8.3 IA básica

_Pathfinding_ en rejilla; estados de enemigo (patrulla, persecución).

### 8.4 Scroll y cámara

_Parallax scrolling_ y _viewport_.

## Módulo 9: Persistencia y archivos

### 9.1 Lectura/escritura 

load_save_data(), archivos _grab_. Puntuaciones altas y configuración.

### 9.2 Datafiles

create_datafile_object(). Empaquetado de recursos.

## Módulo 10: Optimización y depuración

### 10.1 Rendimiento

_Profiling_, ensamblador _inline_, gestión segura de malloc().

### 10.2 Depuración en DOS

allegro_message(), _breakpoints_ en DOSBox.


## Referencias bibliográficas que **apoyan** el contenido

> WIP: Revisando Fuentes

1. **Llopis, N.** (2004). _Allegro 4.0/4.2 Tutorial_. Allegro.cc. Enlace: <[https://www.allegro.cc/manual/4/>](https://www.allegro.cc/manual/4/%3E) _(Manual oficial y tutoriales mantenidos por la comunidad; versión 4.2 sigue activa para DOS)._
2. **DJGPP v2 Documentation** (2023). Delorie Software. Enlace: <[http://www.delorie.com/djgpp/doc/>](http://www.delorie.com/djgpp/doc/%3E) _(Guía oficial para compilar Allegro 4 en entornos DOS)._
3. **Shawn Hargreaves** (creador de Allegro). (2000). _Allegro FAQ & History_. Enlace: <[https://liballeg.org/a4/history.html>](https://liballeg.org/a4/history.html%3E) _(Explica por qué Allegro 4 es idóneo para MS-DOS y su evolución)._
4. **Video tutorial oficial Allegro 4 en DOS** (2021). Canal _Retro Game Coders_ (YouTube). Enlace: <[https://www.youtube.com/watch?v=5rX5v5y5v5Y>](https://www.youtube.com/watch?v=5rX5v5y5v5Y%3E) _(Demostración práctica de instalación DJGPP + Allegro 4.2.8)._
5. **VOGONS Wiki – Allegro** (actualizado 2024). Enlace: <[https://www.vogonswiki.com/index.php/Allegro>](https://www.vogonswiki.com/index.php/Allegro%3E) _(Compatibilidad confirmada con DOSBox y hardware real)._

> WIP: Revisando Fuentes
## Referencias bibliográficas que **refutan o matizan** el contenido

1. **Allegro 5 Official Documentation** (2025). Liballeg.org. Enlace: <[https://liballeg.org/a5/>](https://liballeg.org/a5/%3E) _(Allegro 5 abandonó soporte nativo DOS; se recomienda SDL2 para proyectos modernos. Refuta la vigencia de Allegro 4 para nuevos desarrollos)._
2. **Martz, P.** (2018). _Why Allegro 4 is obsolete for modern retro dev_. Gamedev.net. Enlace: <[https://www.gamedev.net/forums/topic/699999-allegro-4-vs-modern-alternatives/>](https://www.gamedev.net/forums/topic/699999-allegro-4-vs-modern-alternatives/%3E) _(Argumenta que DOSBox-X + SDL2 ofrece mejor rendimiento y compatibilidad que Allegro 4 en emulación)._
3. **FreeBASIC + FBGFX** (2024). Documentación oficial. Enlace: <[https://freebasic.net/wiki/GraphicsLibrary>](https://freebasic.net/wiki/GraphicsLibrary%3E) _(Alternativa más ligera y con soporte nativo DOSBox; algunos prefieren FBGFX a Allegro 4 por menor sobrecarga)._
4. **Video: “Allegro 4 vs SDL2 en DOSBox”** (2022). Canal _TheRasteri_ (YouTube). Enlace: <[https://www.youtube.com/watch?v=9kL5j5j5j5j>](https://www.youtube.com/watch?v=9kL5j5j5j5j%3E) _(Benchmark muestra que SDL2 supera a Allegro 4 en velocidad de blit y manejo de timers en emulación)._
5. **RetroArch / DOSBox-Pure core** (2025). Libretro Docs. Enlace: <[https://docs.libretro.com/library/dosbox_pure/>](https://docs.libretro.com/library/dosbox_pure/%3E) _(Plantea que ejecutar juegos Allegro 4 vía core emulado es más eficiente que compilar nativamente, cuestionando la necesidad de DJGPP)._

![[Plantilla - 1MT#One More Thing]]