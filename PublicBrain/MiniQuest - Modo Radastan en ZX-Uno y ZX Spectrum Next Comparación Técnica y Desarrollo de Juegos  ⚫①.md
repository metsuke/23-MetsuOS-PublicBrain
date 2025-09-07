---
iaStatus: 8
iaStatus_Model: ""
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-09-02T12:12:08.577Z
modified: 2025-09-02T12:26:27.733Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# MiniQuest - Modo Radastan en ZX-Uno y ZX Spectrum Next: Comparación Técnica y Desarrollo de Juegos  ⚫①

[[PublicBrain/Index|Index]]

El **Modo Radastan** es un modo gráfico no estándar del ZX Spectrum, que ofrece una resolución de **128x96 píxeles** con **16 colores por píxel** (sin *attribute clash*), diseñado originalmente para el **ZX-Uno** y con soporte parcial o adaptado en el **ZX Spectrum Next**. A continuación, se detalla qué máquinas soportan este modo, una comparación técnica entre el ZX-Uno y el Next, y estrategias prácticas para desarrollar juegos compatibles en ambas plataformas.

---

## Máquinas que soportan el Modo Radastan

### Soportadas directamente
- **ZX-Uno**: 
  - Clon del ZX Spectrum basado en FPGA.
  - Soporta nativamente el Modo Radastan (128x96 píxeles, 16 colores, 6 KB de memoria).
  - Activación mediante registros específicos (`port_out(0xBF3B, 64)` para ULAplus y `port_out(0xFF3B, 3)` para el modo).
- **ZX Evolution**:
  - Clon ruso basado en FPGA.
  - Ofrece un modo gráfico similar (hasta 512x512 píxeles con viewport de 320x200), compatible con contenido adaptado al Modo Radastan.
  - No es idéntico, pero puede ejecutar programas similares.

### Soportadas parcialmente
- **ZX Spectrum Next**:
  - No soporta el Modo Radastan de forma nativa, pero puede emularlo mediante el modo **Layer 2** (256x192 píxeles, 256 colores) limitando la resolución y paleta.
  - Compatible con programas diseñados para Modo Radastan, con ajustes en la configuración del hardware FPGA.

### No soportadas
- **Sinclair Vega**: No permite cambios dinámicos en la paleta, incompatible con Modo Radastan.
- **ZX Spectrum SE / Chloe 280SE**: Pueden soportar modos avanzados, pero no hay evidencia de soporte específico para Modo Radastan.

---

## Comparación técnica: ZX-Uno vs. ZX Spectrum Next

### ZX-Uno
- **Definición del Modo Radastan**:
  - **Resolución**: 128x96 píxeles.
  - **Colores**: 16 colores por píxel (paleta de 256 colores, formato RGB 3:3:2).
  - **Memoria**: 6 KB de VRAM (dirección base 0x4000).
  - **Sin *attribute clash***: Cada píxel tiene color independiente.
- **Implementación**:
  - Activación:
    ```z80
    ld bc, 0xBF3B
    ld a, 64
    out (c), a    ; Activar ULAplus
    ld bc, 0xFF3B
    ld a, 3
    out (c), a    ; Activar Modo Radastan
    ```
  - Escritura directa en VRAM para dibujar píxeles.
- **Limitaciones**:
  - Resolución baja y 6 KB de memoria limitan el detalle gráfico.
  - Sin sprites por hardware; requiere implementación por software.
  - Comunidad más pequeña, menos recursos disponibles.
- **Ventajas**:
  - Soporte nativo, configuración simple.
  - Ideal para juegos retro con gráficos pixelados.

### ZX Spectrum Next
- **Definición del Modo Radastan (emulado)**:
  - **Resolución**: 128x96 píxeles (emulada en Layer 2, nativo 256x192).
  - **Colores**: 16 colores (emulados, paleta ULAplus) o 256 colores (Layer 2, RGB 3:3:3).
  - **Memoria**: 48 KB (Layer 2 completo) o 6 KB (emulando Radastan).
- **Implementación**:
  - Configuración de Layer 2 para emular Radastan:
    ```z80
    ld bc, 0x123B
    ld a, 0x02
    out (c), a    ; Activar Layer 2
    ld bc, 0x243B
    ld a, 0x40
    out (c), a    ; Seleccionar paleta
    ld bc, 0x253B
    ld a, 0x00
    out (c), a    ; Configurar colores
    ```
  - Limitar el área de dibujo a 128x96 píxeles manualmente.
- **Limitaciones**:
  - Emulación no nativa, requiere ajustes para replicar el Modo Radastan.
  - Configuración de Layer 2 más compleja que en ZX-Uno.
  - Menos soporte comunitario para Modo Radastan frente a modos nativos del Next.
- **Ventajas**:
  - Hardware más avanzado: sprites, scrolling y procesador Copper.
  - Mayor resolución y paleta en Layer 2 para versiones mejoradas.
  - Comunidad activa con herramientas como **CSpect** y **Z88DK**.

### Resumen técnico

| **Aspecto**                | **ZX-Uno**                              | **ZX Spectrum Next**                        |
|----------------------------|-----------------------------------------|---------------------------------------------|
| **Soporte nativo**         | Sí (Modo Radastan).                    | No, emulado vía Layer 2.                   |
| **Resolución**             | 128x96 píxeles.                        | 128x96 (emulado) o 256x192 (Layer 2).      |
| **Colores**                | 16 colores (RGB 3:3:2).                | 16 colores (emulado) o 256 (Layer 2).      |
| **Memoria gráfica**        | 6 KB.                                  | 48 KB (Layer 2) o 6 KB (emulado).          |
| **Sprites**                | Por software.                          | Por hardware (hasta 128 sprites).           |
| **Configuración**          | Simple (puertos 0xBF3B, 0xFF3B).       | Compleja (puertos TBBlue).                 |
| **Comunidad**              | Menor, centrada en ZX-Uno.             | Mayor, enfocada en modos nativos.          |

---

## Desarrollo práctico de juegos para ambos sistemas

### Estrategias para compatibilidad
1. **Diseño gráfico optimizado**:
   - **Resolución común**: Diseña gráficos en 128x96 píxeles para compatibilidad con ZX-Uno. En el Next, usa un subconjunto de Layer 2 para emular esta resolución.
   - **Paleta compartida**: Usa 16 colores compatibles con ULAplus (RGB 3:3:2). Asegúrate de que los colores sean válidos en la paleta de 9 bits del Next.
   - **Herramientas gráficas**: Usa **Retro Pixel** o **Multipaint** para crear gráficos exportables a ambos sistemas.

2. **Programación portable**:
   - **Ensamblador Z80**: Escribe el núcleo del juego en ensamblador para un control preciso. Usa rutinas separadas para cada plataforma:
     ```z80
     ld a, (machine_type)  ; 1 = ZX-Uno, 2 = Next
     cp 1
     jr z, setup_uno
     ; Configuración para Next (Layer 2)
     ld bc, 0x123B
     ld a, 0x02
     out (c), a
     jr continue
     setup_uno:
     ; Configuración para ZX-Uno (Radastan)
     ld bc, 0xBF3B
     ld a, 64
     out (c), a
     ld bc, 0xFF3B
     ld a, 3
     out (c), a
     continue:
     ; Código común para dibujar
     ```
   - **Bibliotecas**: Usa **Z88DK** con la biblioteca `sp1` para manejar gráficos en ambos sistemas.
   - **Detección de hardware**: "I"mplementa una rutina para detectar la máquina (por ejemplo, comprobando puertos o memoria).

3. **Gestión de memoria**:
   - **ZX-Uno**: Limita los gráficos a 6 KB, optimizando con técnicas como RLE o tiles.
   - **Next**: Usa bancos de memoria adicionales para gráficos complejos, pero incluye una versión simplificada para ZX-Uno.

4. **Sprites y animaciones**:
   - **ZX-Uno**: Implementa sprites por software, usando máscaras para evitar sobrescrituras.
   - **Next**: Aprovecha sprites por hardware, pero incluye una versión por software para compatibilidad.
   - Diseña sprites en 16x16 o 8x8 píxeles para simplicidad.

5. **Pruebas y depuración**:
   - Usa **ZEsarUX** para ZX-Uno y **CSpect** para Next.
   - Verifica paleta y resolución en ambos sistemas.
   - Participa en foros como **zxuno.com** y **specnext.com** para retroalimentación.

### Ventajas y desafíos por plataforma
- **ZX-Uno**:
  - **Ventajas**: Soporte nativo, configuración simple, ideal para juegos retro.
  - **Desafíos**: Resolución limitada, sin sprites por hardware, comunidad pequeña.
- **ZX Spectrum Next**:
  - **Ventajas**: "H"ardware avanzado (sprites, scrolling, Copper), comunidad activa.
  - **Desafíos**: Emulación no nativa, configuración compleja, ajustes para compatibilidad.

---

## Recomendaciones finales
- **Desarrolla primero para ZX-Uno**: Diseña el juego con las restricciones del Modo Radastan (128x96, 16 colores, 6 KB) para garantizar compatibilidad base.
- **Adapta para Next**: Porta el juego a Layer 2, limitando resolución y paleta. Opcionalmente, crea una versión mejorada con 256x192 y sprites por hardware.
- **Optimiza assets**: Usa gráficos simples (tiles, sprites pequeños) para minimizar carga en ZX-Uno y facilitar portabilidad.
- **Prueba en ambos sistemas**: Usa emuladores (**ZEsarUX**, **CSpect**) y hardware real para verificar compatibilidad.
- **Recursos**:
  - **ZX-Uno**: *ZX-Uno Technical Reference*, foro **zxuno.com**.
  - **Next**: *ZX Spectrum Next Reference Manual*, foro **specnext.com**.

Con este enfoque, puedes crear juegos que funcionen en el Modo Radastan del ZX-Uno y se adapten al ZX Spectrum Next, manteniendo consistencia visual y funcionalidad en ambas plataformas.




![[Plantilla - 1MT#One More Thing]]