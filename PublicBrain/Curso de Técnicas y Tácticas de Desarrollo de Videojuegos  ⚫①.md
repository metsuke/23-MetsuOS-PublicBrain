---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-10-09T23:32:21.388Z
modified: 2025-10-14T12:12:15.744Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
---
# Curso de Técnicas y Tácticas de Desarrollo de Videojuegos  ⚫①

Este índice está diseñado para un curso integral sobre técnicas y tácticas de desarrollo de videojuegos, cubriendo desde fundamentos históricos hasta prácticas modernas. El enfoque combina teoría, análisis de casos y ejercicios prácticos. El curso se divide en **8 módulos**, con un total de **120 horas** (60 teóricas, 40 de laboratorios, 20 de proyectos). 

Se integra un **módulo dedicado (Módulo 4)** sobre la era de escalado de sprites de Sega y la transición a sistemas poligonales, basado en un análisis cronológico histórico de las innovaciones de Sega, con ejemplos prácticos de emulación y recreación en herramientas modernas.


## Módulo 1: Introducción al Desarrollo de Videojuegos (10 horas)
- **Objetivos**: Entender el panorama del desarrollo de videojuegos, roles del equipo y ciclos de vida del proyecto.
- **Temas**:
  - Historia breve: De *Pong* (1972) a la era actual.
  - Equipos: Diseñadores, programadores, artistas, productores.
  - Herramientas: Unity, Unreal Engine, Godot.
- **Actividades**: Análisis de un GDD (Game Design Document) simple.
- **Evaluación**: Ensayo corto sobre el impacto de un juego icónico.
- **Lecturas**: *The Ultimate History of Video Games* (excerptos).

---

## Módulo 2: Fundamentos de Diseño de Juegos (15 horas)
- **Objetivos**: Aprender principios de mecánicas, narrativa y jugabilidad.
- **Temas**:
  - Mecánicas core: Loop de juego, progresión, balance.
  - Narrativa interactiva: Ramas, elecciones, *world-building*.
  - Monetización: Free-to-play vs. premium.
- **Actividades**: Prototipo de un juego simple (e.g., *endless runner*) en Godot.
- **Evaluación**: Presentación de un *pitch* de juego.
- **Lecturas**: *Rules of Play* de Katie Salen y Eric Zimmerman.

---

## Módulo 3: Evolución Histórica de las Técnicas Gráficas (12 horas)
- **Objetivos**: Contextualizar el desarrollo gráfico desde los orígenes hasta la era 16-bit.
- **Temas**:
  - Generaciones tempranas: 8-bit (NES/Master System), tiles, sprites básicos.
  - Arcades: Scrolling, parallax, pseudo-3D inicial.
  - Caso: SNES vs. Sega Genesis en 2D avanzado.
- **Actividades**: Recreación de un nivel *parallax* en Aseprite y Unity.
- **Evaluación**: *Timeline* comparativa de consolas (ensayo ilustrado).
- **Lecturas**: Artículos sobre la "guerra de los 16 bits".
- **Integración con Módulo 4**: Puente hacia la era de sprites escalados de Sega.

---

## Módulo 4: La Era de Escalado de Sprites y la Transición a Sistemas Poligonales (18 horas)
- **Objetivos**: Analizar la evolución de técnicas gráficas (sprites, escalado, pseudo-3D, polígonos, ray tracing) en consolas, microordenadores y ordenadores desde 1972 hasta 2025, con énfasis en tácticas de optimización. Implementar efectos históricos y modernos en proyectos prácticos.
- **Temas**:
  - **Contexto histórico**: Desde sprites 2D (1970s) hasta ray tracing y rendering con IA (2020s), destacando innovaciones hardware (chips gráficos, GPUs) y software (ensamblador, APIs, DLSS).
  - **Diversidad de plataformas**: Consolas (Atari, Nintendo, Sega, Sony, Microsoft), microordenadores (ZX Spectrum, Commodore, Amiga, Atari ST) y PC; desglose de técnicas como Filmation (ZX Spectrum), Super Scaler (Sega), Mode 7 (SNES), raycasting (*Doom*), y upscaling con IA (PC 2020s).
  - **Lista histórica y cronológica**:
    - **1972 - Magnavox Odyssey (Consola)**  
      - **Hito Técnico**: Primera consola doméstica; gráficos analógicos con overlays físicos.  
      - **Tácticas de Desarrollo**: Sin CPU, usa lógica discreta para sprites básicos; posicionamiento manual (*Pong*).  
      - **Impacto**: Inicia la industria doméstica; *Pong* establece mecánicas arcade.
    - **1977 - Atari 2600 (VCS) (Consola)**  
      - **Hito Técnico**: Cartuchos ROM, chip TIA (128 colores, 2 sprites).  
      - **Tácticas de Desarrollo**: Ensamblador para ciclos de CPU; paletas limitadas (*Pitfall!*).  
      - **Impacto**: 30M unidades; populariza consolas; sprites simples definen 2D arcade.
    - **1978 - Apple II (Microordenador)**  
      - **Hito Técnico**: Gráficos 280x192, 6 colores.  
      - **Tácticas de Desarrollo**: Bitmaps en BASIC; *Ultima* usa tiles para mapas.  
      - **Impacto**: Inicia juegos en PC; flexibilidad para desarrolladores indie.
    - **1979 - Atari 400/800 (Microordenadores)**  
      - **Hito Técnico**: Chip ANTIC para sprites, 256 colores.  
      - **Tácticas de Desarrollo**: Scrolling hardware; *Star Raiders* usa wireframe pseudo-3D.  
      - **Impacto**: Pionero en simuladores 3D; inspira géneros espaciales.
    - **1980 - Sinclair ZX80/ZX81 (Microordenadores)**  
      - **Hito Técnico**: 1 KB RAM, gráficos monocromáticos (32x22 bloques).  
      - **Tácticas de Desarrollo**: Ensamblador para pseudo-3D (*3D Monster Maze*); optimización extrema.  
      - **Impacto**: Escena *homebrew* en Europa; pseudo-3D en hardware limitado.
    - **1981 - IBM PC (CGA) (Ordenador)**  
      - **Hito Técnico**: CGA (320x200, 4 colores).  
      - **Tácticas de Desarrollo**: Sprites simples o ASCII; *Microsoft Flight Simulator* usa wireframe.  
      - **Impacto**: PC como plataforma de juegos; gráficos vectoriales iniciales.
    - **1982 - Sinclair ZX Spectrum 48K (Microordenador)**  
      - **Hito Técnico**: 256x192, 15 colores, *color clash* (2 colores por bloque 8x8).  
      - **Tácticas de Desarrollo**: Atributos por bloque; *Manic Miner* optimiza memoria.  
      - **Variaciones**: Ensamblador para scrolling suave (*Jet Set Willy*); Filmation (*Knight Lore*) para pseudo-3D isométrico.  
      - **Impacto**: 5M unidades; escena indie; Filmation impulsa perspectivas 3D.
    - **1982 - Commodore 64 (Microordenador)**  
      - **Hito Técnico**: VIC-II (320x200, 16 colores), 8 sprites.  
      - **Tácticas de Desarrollo**: Multitarea para animaciones; *International Karate* usa sprites hardware.  
      - **Impacto**: 17M unidades; estándar 8-bit; sprites avanzados.
    - **1983 - Nintendo Famicom (NES) (Consola)**  
      - **Hito Técnico**: PPU (52 colores, 64 sprites).  
      - **Tácticas de Desarrollo**: Tiles y scrolling (*Super Mario Bros.*); mappers para memoria.  
      - **Impacto**: 62M unidades; estandariza 2D; scrolling suave define plataformas.
    - **1983 - Sega SG-1000 (Consola)**  
      - **Hito Técnico**: Sprites básicos, sin escalado hardware.  
      - **Tácticas de Desarrollo**: Ensamblador para scrolling; *Flicky* optimiza paleta.  
      - **Impacto**: Inicio 8-bit de Sega; compite con NES.
    - **1984 - ZX Spectrum 48K (Filmation y Wireframe) (Microordenador)**  
      - **Hito Técnico**: Pseudo-3D avanzado.  
      - **Tácticas de Desarrollo**: *Elite* usa wireframe 3D; Filmation (*Knight Lore*) para isométrico; compresión en 48 KB.  
      - **Impacto**: Wireframe e isométrico inspiran 3D temprano.
    - **1985 - Commodore Amiga 1000 (Microordenador)**  
      - **Hito Técnico**: Chip Agnus (4096 colores, 320x200), blitter.  
      - **Tácticas de Desarrollo**: Blitter para animaciones (*Defender of the Crown*); copper para efectos dinámicos.  
      - **Impacto**: 7M unidades; pionero en 2D multimedia.
    - **1985 - Sega Master System (Consola)**  
      - **Hito Técnico**: VDP para pseudo-3D, parallax.  
      - **Tácticas de Desarrollo**: Tiles para profundidad (*Zoom 909*); escalado software.  
      - **Impacto**: 13M unidades; pseudo-3D en 8-bit.
    - **1985 - Atari ST (Microordenador)**  
      - **Hito Técnico**: 512 colores, 320x200.  
      - **Tácticas de Desarrollo**: GEM para interfaces; *Dungeon Master* usa raycasting.  
      - **Impacto**: Popular en Europa; impulsa RPGs con perspectiva 3D.
    - **1985 - Sega *After Burner* (Arcade)**  
      - **Hito Técnico**: Super Scaler para escalado/rotación sprites.  
      - **Tácticas de Desarrollo**: Chips dedicados; pre-renderizado para fluidez.  
      - **Impacto**: Populariza pseudo-3D en arcades.
    - **1986 - Sega *Out Run* (Arcade)**  
      - **Hito Técnico**: Escalado de fondos/sprites para carreteras.  
      - **Tácticas de Desarrollo**: Frames pre-renderizados; CPU 68000.  
      - **Impacto**: Fórmula *racing* pseudo-3D.
    - **1986 - ZX Spectrum 128K (Microordenador)**  
      - **Hito Técnico**: 128 KB RAM, gráficos 256x192.  
      - **Tácticas de Desarrollo**: *The Great Escape* combina isométrico y sprites; compresión para cintas.  
      - **Impacto**: Mejora juegos complejos; pseudo-3D fluido.
    - **1987 - NEC PC Engine (TurboGrafx-16) (Consola)**  
      - **Hito Técnico**: 482 colores, sprites avanzados.  
      - **Tácticas de Desarrollo**: HuCards; *R-Type* optimiza sprites hardware.  
      - **Impacto**: 10M unidades; 2D de alta calidad.
    - **1987 - IBM PC (VGA) (Ordenador)**  
      - **Hito Técnico**: VGA (640x480, 256 colores).  
      - **Tácticas de Desarrollo**: Bitmaps y scrolling (*Commander Keen*); *Wolfenstein 3D* usa raycasting.  
      - **Impacto**: PC lidera 2D avanzado; raycasting impulsa FPS.
    - **1988 - Sega Genesis (Mega Drive) (Consola)**  
      - **Hito Técnico**: 16-bit, 512 colores, sin escalado hardware.  
      - **Tácticas de Desarrollo**: Software para escalado (*Road Rash*); VDP para parallax.  
      - **Impacto**: 35M unidades; ports arcade optimizados.
    - **1989 - Sega *Galaxy Force II* (Arcade)**  
      - **Hito Técnico**: Escalado avanzado para entornos espaciales.  
      - **Tácticas de Desarrollo**: Sprites como *billboards*; múltiples CPUs.  
      - **Impacto**: Zoom dinámico; influye en *shooters*.
    - **1990 - SNES (Super Nintendo) (Consola)**  
      - **Hito Técnico**: Mode 7 para escalado/rotación.  
      - **Tácticas de Desarrollo**: Pseudo-3D (*F-Zero*); paleta de 32K colores.  
      - **Impacto**: 49M unidades; Mode 7 compite con Super Scaler.
    - **1988 - Sega Genesis (Mega Drive) (Consola)**  
      - **Hito Técnico**: 16-bit, 512 colores, sin escalado hardware.  
      - **Tácticas de Desarrollo**: Software para escalado (*Road Rash*); VDP para parallax.  
      - **Impacto**: 35M unidades; ports arcade optimizados (*Golden Axe*).  
    - **1989 - Sega *Galaxy Force II* (Arcade)**  
      - **Hito Técnico**: Escalado avanzado para entornos espaciales.  
      - **Tácticas de Desarrollo**: Sprites como *billboards* para perspectiva 3D; múltiples CPUs.  
      - **Impacto**: Zoom dinámico; influye en *shooters* modernos.  
    - **1990 - SNES (Super Nintendo) (Consola)**  
      - **Hito Técnico**: Mode 7 para escalado/rotación hardware.  
      - **Tácticas de Desarrollo**: Pseudo-3D (*F-Zero*); paleta de 32K colores.  
      - **Impacto**: 49M unidades; Mode 7 compite con Super Scaler de Sega.  
    - **1991 - Sega CD add-on (Consola)**  
      - **Hito Técnico**: Chip ASIC para escalado/rotación hardware.  
      - **Tácticas de Desarrollo**: Buffer para FMV y escalado suave (*Sonic CD*).  
      - **Impacto**: 6M unidades; extiende Genesis con pseudo-3D y multimedia.  
    - **1992 - Sega *Virtua Racing* (Arcade)**  
      - **Hito Técnico**: 3D poligonal (50K polígonos/seg).  
      - **Tácticas de Desarrollo**: Texturas en polígonos; *motion capture* inicial.  
      - **Impacto**: Revolución *racing* 3D; sprites reemplazados por polígonos.  
    - **1992 - Amiga 1200 (AGA) (Microordenador)**  
      - **Hito Técnico**: Chipset AGA (256K colores).  
      - **Tácticas de Desarrollo**: Blitter avanzado; *Cannon Fodder* combina 2D y efectos 3D.  
      - **Impacto**: Último esfuerzo de Commodore; 2D compite con consolas.  
    - **1993 - Atari Jaguar (Consola)**  
      - **Hito Técnico**: 64-bit híbrido (2D/3D).  
      - **Tácticas de Desarrollo**: Tom chip para polígonos; *Doom* usa raycasting optimizado.  
      - **Impacto**: Fracaso (250K unidades); transición 3D limitada.  
    - **1993 - Sega *Virtua Fighter* (Arcade)**  
      - **Hito Técnico**: Primer *fighter* 3D (<1.2K polígonos).  
      - **Tácticas de Desarrollo**: Renderizado triangle-based; *low-poly* para framerates.  
      - **Impacto**: Populariza 3D en *fighting games*; táctica *low-poly*.  
    - **1993 - 3DO Interactive Multiplayer (Consola)**  
      - **Hito Técnico**: 32-bit con 3D y FMV.  
      - **Tácticas de Desarrollo**: Polígonos texturizados (*Need for Speed*); CD-ROM para almacenamiento.  
      - **Impacto**: 2M unidades; pionera en 3D doméstico, pero cara.  
    - **1994 - Sony PlayStation (Consola)**  
      - **Hito Técnico**: 32-bit (1M polígonos/seg).  
      - **Tácticas de Desarrollo**: Renderizado 3D con CD-ROM; *Ridge Racer* usa texturas avanzadas.  
      - **Impacto**: 102M unidades; estandariza 3D en consolas domésticas.  
    - **1994 - Sega Saturn (Consola)**  
      - **Hito Técnico**: Dual-CPU, 200K polígonos/seg, soporte 2D/3D híbrido.  
      - **Tácticas de Desarrollo**: Bibliotecas gráficas; *Virtua Fighter 2* usa sprites y polígonos.  
      - **Impacto**: 9M unidades; transición híbrida sprites/polígonos.  
    - **1995 - Nintendo 64 (Consola)**  
      - **Hito Técnico**: Reality Coprocessor (150K polígonos/seg).  
      - **Tácticas de Desarrollo**: Texturas filtradas (*Super Mario 64*); cartuchos para carga rápida.  
      - **Impacto**: 33M unidades; define mundos 3D abiertos en consolas.  
    - **1996 - PC (3dfx Voodoo) (Ordenador)**  
      - **Hito Técnico**: Aceleradoras 3D (1M polígonos/seg).  
      - **Tácticas de Desarrollo**: Glide API; *Quake* usa polígonos texturizados y BSP trees.  
      - **Impacto**: PC lidera en 3D; *Tomb Raider* populariza 3D en PC.  
    - **1998 - Sega Dreamcast (Consola)**  
      - **Hito Técnico**: PowerVR (3M polígonos/seg).  
      - **Tácticas de Desarrollo**: Vulkan-like API; *bump mapping* (*SoulCalibur*); soporte online.  
      - **Impacto**: 9M unidades; pionera en multiplayer 3D online.  
    - **2000 - Sony PlayStation 2 (Consola)**  
      - **Hito Técnico**: Emotion Engine (6.2M polígonos/seg).  
      - **Tácticas de Desarrollo**: Shaders básicos; *Gran Turismo 3* usa iluminación avanzada.  
      - **Impacto**: 155M unidades; estandariza 3D fotorrealista en consolas.  
    - **2001 - Microsoft Xbox (Consola)**  
      - **Hito Técnico**: GPU NVIDIA (125M píxeles/seg).  
      - **Tácticas de Desarrollo**: DirectX para 3D; *Halo* usa *normal mapping*.  
      - **Impacto**: 24M unidades; arquitectura PC-like; impulsa online (*Xbox Live*).  
    - **2005 - Xbox 360 (Consola)**  
      - **Hito Técnico**: GPU Xenos (500M polígonos/seg).  
      - **Tácticas de Desarrollo**: Shaders unificados; *Gears of War* usa Unreal Engine 3.  
      - **Impacto**: 84M unidades; introduce HD y rendering complejo.  
    - **2006 - Sony PlayStation 3 (Consola)**  
      - **Hito Técnico**: Cell Processor, RSX GPU.  
      - **Tácticas de Desarrollo**: Multithreading para física; *Uncharted* usa animaciones dinámicas.  
      - **Impacto**: 87M unidades; empuja límites de rendering 3D.  
    - **2013 - PlayStation 4/Xbox One (Consolas)**  
      - **Hito Técnico**: APU AMD (1.8-4.2 TFLOPS).  
      - **Tácticas de Desarrollo**: Compute shaders; *The Witcher 3* usa mundos abiertos detallados.  
      - **Impacto**: 117M/58M unidades; estándar 1080p, física avanzada.  
    - **2017 - Nintendo Switch (Consola)**  
      - **Hito Técnico**: Tegra X1 (1 TFLOPS).  
      - **Tácticas de Desarrollo**: Optimización para portabilidad; *Breath of the Wild* usa cel-shading dinámico.  
      - **Impacto**: 141M unidades; hibridez consola/portátil; 3D optimizado.  
    - **2020 - PlayStation 5/Xbox Series X (Consolas)**  
      - **Hito Técnico**: 10-12 TFLOPS, ray tracing hardware.  
      - **Tácticas de Desarrollo**: SSD para streaming; *Demon’s Souls* usa ray tracing parcial.  
      - **Impacto**: 61M/30M unidades; fotorrealismo y carga mínima; ray tracing mainstream.  
    - **2022 - Steam Deck (PC Portátil)**  
      - **Hito Técnico**: APU AMD (1.6 TFLOPS).  
      - **Tácticas de Desarrollo**: Optimización para portabilidad; *Elden Ring* usa rendering adaptativo.  
      - **Impacto**: 3M+ unidades; PC gaming portátil; optimización multiplataforma.  
    - **2025 - PC (NVIDIA RTX 5090, estimado) (Ordenador)**  
      - **Hito Técnico**: 30+ TFLOPS, ray tracing avanzado.  
      - **Tácticas de Desarrollo**: DLSS 4.0 para upscaling con IA; *GTA VI* usa path tracing parcial.  
      - **Impacto**: Lidera fotorrealismo; IA en rendering (texturas generativas).  
    - **2025 - Consolas Next-Gen (rumores)**  
      - **Hito Técnico**: Especulaciones: 20+ TFLOPS, IA integrada.  
      - **Tácticas de Desarrollo**: Rendering híbrido (rasterización + ray tracing); cloud gaming.  
      - **Impacto**: Futuro: Mundos dinámicos con IA; integración VR/AR.

  - **Análisis de tácticas**: Comparación de sprites escalados (baratos, fluidos) vs. polígonos (profundidad, CPU-intensivo) vs. ray tracing (fotorrealismo, GPU-intensivo). Lecciones: Optimización en hardware limitado (ZX Spectrum, Genesis), transiciones hardware (add-ons vs. nueva gen), y uso de IA moderna (DLSS).
  - **Tendencias**: Competencia entre consolas (Sega vs. Nintendo), microordenadores (ZX Spectrum vs. Amiga), y PC; impacto de APIs (Glide, DirectX, Vulkan) y técnicas como Filmation o raycasting.
- **Actividades**:
  - Recrear escalado de sprites en Unity (*shader* para *After Burner*-like).
  - Prototipo híbrido: Nivel pseudo-3D con polígonos en Godot (inspirado en *Knight Lore* o *F-Zero*).
  - Análisis de código fuente emulado (MAME para arcades; DOSBox para PC; ZX Spectrum emuladores para Filmation).
- **Evaluación**: Proyecto grupal: Recrear un nivel de *Virtua Racing*, *F-Zero*, o *Elite* con tácticas modernas; informe cronológico personalizado.
- **Lecturas**: *Retro Gaming Hardware* (capítulos sobre ZX Spectrum, Sega, Amiga, PC); videos de Digital Foundry (*Virtua Fighter*, *Doom*, *GTA VI*).

---

## Módulo 5: Técnicas de Programación y Optimización (15 horas)
- **Objetivos**: Dominar scripting, algoritmos y rendimiento.
- **Temas**:
  - Lenguajes: C#, C++ en motores.
  - Optimización: LOD, *occlusion culling* (lección de *low-poly* de Sega).
  - IA básica: *Pathfinding*, estados finitos.
- **Actividades**: Optimización de prototipo del Módulo 2.
- **Evaluación**: Código revisado con *benchmarks*.
- **Lecturas**: *Game Programming Patterns* de Robert Nystrom.
- **Integración con Módulo 4**: Aplicar tácticas de escalado software a un minijuego.

---

## Módulo 6: Arte y Audio en Videojuegos (12 horas)
- **Objetivos**: Crear assets visuales y sonoros inmersivos.
- **Temas**:
  - Pixel art y modelado 3D (de sprites a *low-poly*).
  - Audio: SFX, música procedural.
  - Herramientas: Aseprite, Blender, FMOD.
- **Actividades**: Assets para prototipo de Módulo 4.
- **Evaluación**: Portfolio de assets temáticos.
- **Lecturas**: *The Art of Game Design* de Jesse Schell.

---

## Módulo 7: Pruebas, Marketing y Publicación (10 horas)
- **Objetivos**: Preparar un juego para lanzamiento.
- **Temas**:
  - QA: Bugs, balance, usabilidad.
  - Marketing: Trailers, Steam pages.
  - Plataformas: Consolas, PC, mobile.
- **Actividades**: *Playtest* de prototipos grupales.
- **Evaluación**: Plan de lanzamiento simulado.
- **Lecturas**: *Blood, Sweat, and Pixels* de Jason Schreier.

---

## Módulo 8: Tendencias Futuras y Proyecto Final (18 horas)
- **Objetivos**: Explorar VR/AR, IA generativa y sostenibilidad.
- **Temas**:
  - Realidad mixta y *cloud gaming*.
  - Ética: Inclusividad, *crunch*.
  - Proyecto *capstone*: Juego completo integrando módulos.
- **Actividades**: Desarrollo iterativo del proyecto final.
- **Evaluación**: Demo jugable + presentación (30% del curso).
- **Lecturas**: Artículos sobre IA en desarrollo (e.g., NVIDIA GameWorks).

---

## Notas Generales del Curso
- **Requisitos previos**: Conocimientos básicos de programación y diseño.
- **Metodología**: 50% teórico, 50% práctico; uso de GitHub para colaboración.
- **Recursos**: Labs con hardware retro (emuladores MAME para Sega).
- **Duración**: 12 semanas, retroalimentación semanal.
- **Objetivo global**: Formar desarrolladores versátiles, inspirados en innovaciones históricas de Sega, para tácticas adaptables a hardware moderno.

---

*Fecha de creación: 10 de octubre de 2025, 08:33 AM JST*


![[Plantilla - 1MT#One More Thing]]