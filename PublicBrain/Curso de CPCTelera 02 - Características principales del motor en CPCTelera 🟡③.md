---
iaStatus: 8
iaStatus_Model: Grok-3, Raúl Carrillo aka Metsuke
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-06-23T09:19:16.998Z
modified: 2025-10-07T18:30:00.261Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: 
nav_secondary: 
tags:
---
# Curso de CPCTelera 02 - Características principales del motor en CPCTelera 🟡③

![Caracteristicas de CPCTelera](PublicBrain/_resources/4e023cdd10c600cf9146c414c8dcc376_MD5.jpg)

* [[Curso de CPCTelera  ⚫①]]
* [[Curso de CPCTelera 01 - ¿Qué es CPCTelera? Historia y propósito 🟡③|<< Anterior]] | Siguiente >>


CPCtelera es una potente librería diseñada para facilitar el desarrollo de videojuegos y aplicaciones en el ordenador Amstrad CPC, utilizando principalmente lenguajes C y ensamblador Z80. 

Su "motor" abarca un conjunto de herramientas y funciones que simplifican la gestión de gráficos, sonido, entrada/salida y otros aspectos clave para programar en esta plataforma retro. A continuación, se describen las principales características del motor de CPCtelera, ideales para explorar en un curso sobre esta librería.

## 1. Gestión avanzada de gráficos

CPCtelera ofrece un robusto soporte para los modos gráficos del Amstrad CPC:

- **Modo 0**: Resolución de 160x200 píxeles con hasta 16 colores, ideal para gráficos coloridos.
- **Modo 1**: Resolución de 320x200 píxeles con 4 colores, equilibrando detalle y paleta.
- **Modo 2**: Resolución de 640x200 píxeles con 2 colores, perfecto para textos nítidos o gráficos monocromáticos.

Incluye funciones optimizadas para dibujar sprites y tiles, gestionar paletas de colores y minimizar el uso de la limitada memoria de vídeo del CPC. Además, proporciona herramientas para convertir imágenes modernas (como PNG) a formatos compatibles, facilitando la creación de gráficos retro.

## 2. Programación flexible en C y ensamblador

La librería permite desarrollar en:

- **Lenguaje C**: Con una API clara y bien documentada, ideal para principiantes y proyectos portables.
- **Ensamblador Z80**: Para optimizaciones de bajo nivel, maximizando el rendimiento en la CPU Z80 a 4 MHz del Amstrad CPC.

Incluye macros y funciones predefinidas en ensamblador que simplifican tareas comunes, reduciendo la complejidad del desarrollo.

## 3. Gestión eficiente de memoria

CPCtelera ofrece herramientas para administrar la memoria del CPC (64 KB estándar, ampliable a 128 KB en modelos como el CPC 6128). Sus funciones permiten:

- Cargar y gestionar datos en RAM y VRAM de forma eficiente.
- Utilizar bancos de memoria extendida para proyectos más ambiciosos, como videojuegos complejos.

## 4. Sistema de sprites y animaciones

El motor incluye funciones intuitivas para:

- Crear y mover sprites, con detección de colisiones y soporte para animaciones fluidas.
- Gestionar transparencias y máscaras, permitiendo superposiciones sin errores visuales.
- Optimizar el uso de ciclos de CPU al actualizar la pantalla, crucial para un rendimiento estable.

## 5. Soporte de audio

Integrado con el chip de sonido AY-3-8912 del Amstrad CPC, CPCtelera permite:

- Reproducir hasta 3 canales de audio para música y efectos de sonido.
- Convertir formatos modernos (como MOD o WAV) a formatos compatibles con el CPC.
- Usar la biblioteca de Arkos Tracker, popular en la escena retro, para crear bandas sonoras envolventes.

## 6. Gestión de entrada/salida

La librería proporciona funciones para:

- Leer entradas de teclado, joystick y otros dispositivos compatibles con el Amstrad CPC.
- Implementar un sistema de eventos que facilita la interacción del jugador de manera eficiente.

## 7. Herramientas de desarrollo integradas

CPCtelera incluye utilidades para:

- Compilar, depurar y empaquetar proyectos en entornos modernos (Windows, Linux, macOS), utilizando el subsistema Linux en Windows o entornos nativos.
- Realizar pruebas rápidas con emuladores compatibles, como CPCE o WinCPC.
- Automatizar tareas, como la conversión de recursos gráficos y sonoros, mediante scripts integrados.

## 8. Documentación y comunidad activa

La librería destaca por:

- Una documentación extensa, con tutoriales y ejemplos prácticos para todos los niveles.
- El respaldo de una comunidad vibrante en foros y redes, que comparte plantillas de código, proyectos de ejemplo y soporte técnico.

## 9. Compatibilidad y portabilidad

CPCtelera está diseñada para:

- Funcionar en todos los modelos de Amstrad CPC (464, 664, 6128), adaptándose a características como disqueteras o expansiones de memoria.
- Generar ejecutables compatibles con emuladores y hardware real, facilitando la distribución de juegos y aplicaciones.

## 10. Optimización para retrocomputing

El motor maximiza las capacidades del hardware del CPC mediante:

- Técnicas como el _double buffering_ para evitar parpadeos en pantalla.
- Rutinas rápidas de renderizado para un rendimiento óptimo.
- Un enfoque centrado en videojuegos, aunque también es útil para demos y aplicaciones interactivas.

## Referencias bibliográficas

### Fuentes que apoyan el contenido

1. [**CPCTelera Documentation** 🌐🟡③](https://github.com/lronaldo/cpctelera)
	- La documentación oficial de CPCtelera detalla las funciones de gráficos, sonido, entrada/salida y herramientas de desarrollo, confirmando las características descritas.
2. [Arkos Tracker 3 Manual 🌐🟡③](https://www.julien-nevo.com/arkostracker/)
	- Describe el uso de Arkos Tracker para música en Amstrad CPC, compatible con CPCtelera, validando el soporte de audio.
3. [Amstrad CPC Wiki - Video Modes 🌐🟡③](https://www.cpcwiki.eu/index.php/Video_modes)
    - Confirma los modos gráficos del Amstrad CPC (Modo 0, 1, 2) y sus especificaciones, alineadas con las descritas.
### Fuentes que refutan o matizan el contenido

- **Ninguna fuente verificable disponible**.  

![[Plantilla - 1MT#One More Thing]]