---
iaStatus: 8
iaStatus_Model: DeepSeek-V3, Grok-4 , Gemini, Raul Carrillo Garrido
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2026-04-10T21:48:56.936Z
modified: 2026-04-10T22:17:49.536Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# Curso de ZX-DRAW 🔴②

![Curso de ZX-DRAW](_resources/b71c0e9eb02b3c03130c2d15684ba993_MD5.jpg)


[[Aprender a desarrollar videojuegos  ⚫①]]

Este manual ofrece un recorrido exhaustivo por **ZX-Draw**, una herramienta contemporánea diseñada para dominar la estética y las restricciones técnicas del Sinclair ZX Spectrum. A través de este curso, aprenderás a transformar limitaciones de hardware en decisiones artísticas.

## 1. Fundamentos y Configuración del Entorno

- **Arquitectura Visual del Spectrum:** Comprender la resolución nativa de $256 \times 192$ píxeles y la gestión de memoria de video (VRAM).
    
- **Instalación Multiplataforma:** Configuración optimizada en Windows, macOS y Linux.
    
- **Interfaz y Personalización:** Uso de los menús en castellano y ajuste del área de trabajo para maximizar la precisión.
    
- **Estructura de Archivos:** Diferencias operativas entre el proyecto nativo `.zxp` y el volcado de memoria estándar `.scr`.
    

## 2. Herramientas de Dibujo y Edición Técnica

- **Precisión de Píxel:** Técnicas de dibujo manual y uso de pinceles.
    
- **La Rejilla de Atributos:** Edición basada estrictamente en bloques de $8 \times 8$, la unidad fundamental del Spectrum.
    
- **Manipulación de Bloques:** Herramientas de selección, movimiento y clonación de celdas.
    
- **Transformaciones Geométricas:**
    
    - Inversión lógica de píxeles frente a inversión de atributos de color.
        
    - Rotación en ángulos rectos y simetrías (Espejo H/V).
        
- **Tipografía Retro:** Inserción de texto mediante el gestor de fuentes compatibles con el juego de caracteres del Spectrum.
    

## 3. El Sistema de Atributos y el Color

- **Gestión de Ink, Paper y Bright:** Aplicación de los 15 colores disponibles (7 colores básicos en dos niveles de brillo, más el negro).
    
- **Dinámica del Flash:** Implementación de parpadeo por software mediante el bit de atributo correspondiente.
    
- **Resolución del _Attribute Clash_:** Estrategias avanzadas para minimizar el conflicto de colores cuando dos elementos comparten un mismo bloque de $8 \times 8$.
    

## 4. Importación y Conversión de Imagen Moderna

- **Preparación de _Assets_:** Requisitos de contraste y resolución para importar archivos PNG/JPG.
    
- **Procesado en Tiempo Real:** Uso del modal interactivo para ajustar brillo, contraste y saturación antes de la rasterización.
    
- **Refinado Post-conversión:** Limpieza manual de "ruido" tras el proceso de importación.
    

## 5. Creación de _Assets_ para Desarrollo de Videojuegos

- **Pantallas de Carga (_Loading Screens_):** Composición artística en formato completo.
    
- **Diseño de _Spritesets_:** Creación de personajes y objetos dinámicos (estándar 256x48).
    
- **Construcción de _Tilesets_:** Diseño de escenarios basados en patrones repetitivos para optimizar memoria.
    

## 6. Exportación e Integración Profesional

- **Flujo de Trabajo Eficiente:** Uso del historial de archivos recientes.
    
- **Exportación Gráfica:** Generación de imágenes PNG para documentación y promoción.
    
- **Exportación Técnica:** Creación de archivos `.scr` de $6912$ bytes (bitmap + atributos) listos para ser cargados en motores de juegos o código ensamblador mediante:
       $$\text{Dirección VRAM} = 16384 + \text{Bitmap}(6144) + \text{Atributos}(768)$$
    

## Referencias Bibliográficas

### Fuentes que apoyan y fundamentan el contenido

- **Fernández Moreno, J. A. (2018).** _ZX Spectrum: Un recorrido visual_. Dolmen Editorial. (Analiza la estética del sistema y las técnicas de diseño de las pantallas de carga más icónicas).
    
- **Smith, C. (2010).** _The ZX Spectrum ULA: "H"ow to design a microcomputer_. ZXDesign Media. (Referencia técnica fundamental sobre cómo el chip ULA genera el vídeo y causa el _attribute clash_).
    
- **Overtaken by Events.** _The ZX-Spectrum screen layout_. [Consultar artículo técnico](https://www.overtakenbyevents.com/lets-talk-about-the-zx-specrum-screen-layout/). (Explicación detallada del mapa de memoria de los archivos `.scr`).
    

### Fuentes que cuestionan o limitan el contenido

- **Wozniak, S. (2006).** _iWoz_. W. W. Norton & Company. (Aunque trata sobre Apple, ofrece una perspectiva crítica sobre las arquitecturas de vídeo de bajo coste como la del Spectrum frente a sistemas con mayor flexibilidad de color).
    
- **Loguidice, B., & Barton, M. (2014).** _Vintage Game Consoles_. Focal Press. (Compara las limitaciones gráficas del Spectrum frente al Commodore 64, señalando la inferioridad del sistema de atributos del primero para el desplazamiento lateral suave).
    
- **El Spectrum y sus extraños colores.** [Análisis crítico en vídeo](https://www.youtube.com/watch?v=jC5FTjA2ORg). (Explica de forma práctica por qué el sistema de atributos es una barrera insuperable para ciertos estilos de dibujo moderno).


![[Plantilla - 1MT#One More Thing]]
