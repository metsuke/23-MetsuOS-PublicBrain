---
iaStatus: 8
iaStatus_Model: Grok-4, Raul Carrillo aka Metsuke
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-10-09T20:01:15.819Z
modified: 2025-10-09T21:58:18.794Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: "0"
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoAYEXEDIT.mp4
---
# Curso de AYFXEDIT 🔴②

![Curso de AYEXEDIT](PublicBrain/_resources/f48c32212e31474740c2a7245104ac8a_MD5.jpg)

[[Aprender a desarrollar videojuegos  ⚫①]]

> WIP Revisar Fuentes

Este curso es un recurso completo y práctico sobre AYFXEDIT, un editor gratuito y de código abierto para crear efectos de sonido (SFX) en formato AYFX. Está optimizado para chips de sonido de tres canales, como el General Instrument AY-3-8910, que marcó una época en la informática retro. Con un enfoque pedagógico, combina teoría sobre computación vintage con ejercicios prácticos, perfecto para desarrolladores de juegos chiptune, fans del hardware antiguo (como ZX Spectrum, Atari ST o Amstrad CPC) y compositores de música 8-bit que buscan revivir esos sonidos nostálgicos.

El índice se organiza en **ocho módulos principales**, cada uno con sublecciones detalladas, objetivos claros, duración aproximada, recursos recomendados y evaluaciones. Para hacerlo más accesible, cada módulo empieza con un resumen ejecutivo y termina con ejercicios prácticos que te ayuden a aplicar lo aprendido.

## Módulo 1: Introducción al Mundo de los Sonidos Retro y AYFX

 * 1.1. Historia del chip AY-3-8910: Su evolución desde 1978 y su impacto en consolas 8-bit como ZX Spectrum o MSX.
 * 1.2. Diferencias entre audio muestreado y procedural: Las ventajas de AYFX, como su compresión extrema y bajo consumo de memoria.
 * 1.3. ¿Qué es AYFXEDIT?: Su origen (creado por Shiru en 2012), versiones disponibles (la original y forks como ayfxedit-improved) y licencia (GPL).
 * 1.4. Aplicaciones en la actualidad: Cómo se integra en emuladores, juegos homebrew y composiciones chiptune.

## Módulo 2: Instalación y Configuración Inicial

   - 2.1. Descarga e instalación: Desde fuentes oficiales como el GitHub de Shiru, forks mejorados o compilación desde código fuente para Linux.
   - 2.2. Requisitos del sistema: Dependencias como SDL para audio, y soluciones a problemas comunes en Windows o Mac.
   - 2.3. Configuración de audio: Cómo integrarlo con reproductores AYFX como Beepola o versiones online.
   - 2.4. Primer arranque: Verifica la interfaz y prueba un sonido básico para asegurarte de que todo funciona.
## Módulo 3: Exploración de la Interfaz de Usuario

   - 3.1. Paneles principales: El editor de formas de onda, envolventes de volumen y el mezclador de canales (A, B y C).
   - 3.2. Herramientas de dibujo: Pinceles, líneas y curvas para formas de onda, con zoom y rejilla para precisión.
   - 3.3. Controles de ruido y tono: Deslizadores para ruido blanco, modulación de frecuencia y más.
   - 3.4. Vista previa en tiempo real: Botones para reproducir, parar, repetir en bucle y previsualizar exportaciones.
   - 3.5. Atajos de teclado y personalización: Configura teclas y temas oscuros para adaptarlo a tu gusto.

## Módulo 4: Creación de Efectos Básicos

   - 4.1. Formas de onda fundamentales: Cuadrada, triangular o sierra, editadas punto por punto.
   - 4.2. Envolventes básicas: ADSR (ataque, decaimiento, sostenido y liberación) aplicadas a volumen y tono.
   - 4.3. Efectos en un solo canal: Pitidos, chirridos y ruidos estáticos.
   - 4.4. Mezcla inicial: Asigna canales (bajos en A, agudos en B o C).
   - 4.5. Optimización de longitud: Recortes y bucles para maximizar eficiencia (máximo 256 bytes por SFX).
## Módulo 5: Técnicas Avanzadas de Edición

* 5.1. Modulación y vibrato: Automatiza cambios de tono para efectos como wobble.
* 5.2. Ruido avanzado: Filtros, barridos y combinaciones con tonos.
* 5.3. Efectos multicapa: Panning, ecos simulados y armonías en varios canales.
* 5.4. Sostenido y bucles: Configura sonidos continuos, como motores o viento.
* 5.5. Edición no destructiva: Deshacer/rehacer, capas y máscaras para iterar rápido.
* 5.6. Depuración común: Corrige errores como clipping o desincronizaciones.
## Módulo 6: Exportación e Integración en Proyectos

   - 6.1. Formatos de exportación: Binario puro, ensamblador Z80/6502 o archivos de inclusión.
   - 6.2. Compresión AYFX: Algoritmos para empaquetar y reducir datos.
   - 6.3. Integración en emuladores: Como Fuse o ZX Spin, y pruebas en hardware físico.
   - 6.4. Uso en motores de juego: Plugins para Godot o Unity, o código nativo en BASIC/ASM.
   - 6.5. Bibliotecas de SFX: Organízalas en bancos y llama a ellas en tiempo de ejecución.
## Módulo 7: Estudios de Caso y Creatividad

   - 7.1. Análisis de SFX icónicos: Recreación paso a paso de sonidos de juegos como Manic Miner o Jet Set Willy.
   - 7.2. Diseño sonoro temático: SFX adaptados a géneros (plataformas, shooters, aventuras).
   - 7.3. Colaboración con música: Sincronización con trackers como Vortex o Arkos.
   - 7.4. Optimización para limitaciones: Bajo uso de CPU en hardware de los 80.
   - 7.5. Comunidad y recursos: Foros como World of Spectrum o itch.io, y concursos de chiptune.
## Módulo 8: Proyecto Final y Mejores Prácticas

* 8.1. Planificación de proyecto: Diseña más de 10 SFX para un juego ficticio.
* 8.2. Flujo de trabajo profesional: Versionado, copias de seguridad y colaboración (usa Git para assets).
* 8.3. Mejores prácticas: Accesibilidad (volúmenes consistentes) y pruebas multiplataforma.
* 8.4. Futuro de AYFX: Extensiones modernas como AYFX2 o soporte MIDI.
* 8.5. Certificación y siguientes pasos: Recursos avanzados, como libros sobre ZX Spectrum.
## Anexos del Curso

- **Glosario completo:** Términos clave como "envolvente", "período de tono" o "registro R7".
- **Bibliografía:** Documentación oficial de Shiru, libros sobre chiptune y foros retro.
- **Recursos extras:** 50 SFX de muestra y scripts básicos en Python para exportaciones en lote.
- **Soporte:** Foro virtual y sesiones de preguntas y respuestas semanales (imaginadas para este curso).
- **Certificado:** Se otorga al completar el 80% de los ejercicios y el proyecto final.

Este índice es exhaustivo pero flexible: si ya dominas alguna parte, puedes saltártela sin problemas. ¿Te apetece que desarrolle una lección concreta, como un tutorial paso a paso del Módulo 4, o que te proporcione recursos extra para arrancar?

## Referencias Bibliográficas que Apoyan el Contenido

> WIP Revisar Fuentes

Estas fuentes confirman la información histórica, técnica y práctica sobre AYFXEDIT y el chip AY-3-8910, basadas en sitios oficiales, wikis y publicaciones verificadas hasta octubre de 2025.

- Shiru. (s.f.). *Software - Shiru's Stuff*. Recuperado de https://shiru.untergrund.net/software.shtml. (Página oficial del desarrollador con descarga de AYFX Editor v0.7 y descripción de sus características).
- Threetwosevensixseven. (s.f.). *AYFX Editor Improved*. GitHub. Recuperado de https://github.com/Threetwosevensixseven/ayfxedit-improved. (Fork mejorado que añade funciones como bucles de sostenido, confirmando evoluciones del tool).
- Paleotronic. (2018, 12 de octubre). *The Noise Channel: "H"earing and Cheering the AY-3-8910*. Recuperado de https://paleotronic.com/2018/10/12/the-noise-channel-hearing-and-cheering-the-ay-3-8910/. (Historia detallada del chip AY-3-8910 desde 1978, apoyando su uso en hardware retro).
- MSX Wiki. (2025, 26 de abril). *General Instrument AY-3-8910*. Recuperado de https://www.msx.org/wiki/General_Instrument_AY-3-8910. (Descripción técnica del chip, incluyendo su diseño en 1978 y aplicaciones en consolas 8-bit).
- McAlpine, K. B. (2018). *Bits and Pieces: A History of Chiptunes*. Oxford University Press. Recuperado de https://www.amazon.com/Bits-Pieces-Chiptunes-Kenneth-McAlpine/dp/019049610X. (Libro que cubre la historia de la música chiptune, incluyendo herramientas como AYFX para SFX procedurales).
- Shiru. (2012, 13 de enero). *AYFX Editor demonstration* [Vídeo]. YouTube. Recuperado de https://www.youtube.com/watch?v=XI6aW2QSUXw. (Demostración oficial de las capacidades de AYFXEDIT).
- Remy Sharp. (2020, 28 de julio). *AY FX (web) editor for zx spectrum (next)* [Vídeo]. YouTube. Recuperado de https://www.youtube.com/watch?v=iFsbwVq8yfQ. (Tutorial sobre una versión web basada en AYFXEDIT, apoyando su integración moderna).
- SoftSpectrum 48. (2017, 28 de octubre). *Part 2: About the AY-3-8910/8912*. Recuperado de https://softspectrum48.weebly.com/notes/ay-emulation-part-2-about-the-ay-3-8912. (Explicación técnica del chip AY, confirmando su introducción en los años 70 y usos en home computers).

## Referencias Bibliográficas que Refutan el Contenido

> WIP Revisar Fuentes

Aunque el contenido es mayoritariamente preciso, estas fuentes destacan limitaciones técnicas o contextuales, como restricciones del chip AY-3-8910 (por ejemplo, envolventes compartidas no equivalentes a un ADSR completo por canal) o la obsolescencia de herramientas como AYFXEDIT (no actualizada desde 2012, requiriendo forks o emuladores para sistemas modernos). No hay contradicciones graves, pero sí puntos sobre limitaciones prácticas y alternativas más avanzadas.

- Synth DIY Wiki. (s.f.). *General Instrument AY-3-8910*. Recuperado de https://sdiy.info/wiki/General_Instrument_AY-3-8910. (Señala que el AY-3-8910 tiene un generador de envolvente compartido, no un ADSR independiente por canal, lo que limita la complejidad de SFX comparado con sistemas modernos).
- Bumbershoot Software. (2021, 2 de mayo). *Atari ST: The AY-3-8910 Sound Chip*. Recuperado de https://bumbershootsoft.wordpress.com/2021/05/02/atari-st-the-ay-3-8910-sound-chip/. (Destaca limitaciones del chip, como solo ondas cuadradas y ruido, refutando la idea de SFX "realistas" sin técnicas avanzadas de modulación).
- MSX Resource Center. (2014, 1 de abril). *AYSFX files needed*. Recuperado de https://www.msx.org/forum/msx-talk/development/aysfx-files-needed. (Discusión forera que menciona la necesidad de actualizaciones en AYFXEDIT para manejar comandos en línea, destacando su falta de flexibilidad en entornos no-Windows).
- Metsuke. (2025, 30 de agosto). Publicación en X sobre AYFXEDIT [Post en X]. Recuperado de https://x.com/metsuke/status/1961652891053105430. (Menciona el uso de Wine para ejecutar AYFXEDIT en Linux, refutando su compatibilidad nativa universal y sugiriendo dependencias de emuladores).
- O'Reilly. (s.f.). *Chiptunes - Sound and Music for Games*. Recuperado de https://www.oreilly.com/library/view/sound-and-music/9781484286616/html/529953_1_En_8_Chapter.xhtml. (Libro que discute cómo el chiptune temprano, basado en chips como AY, es limitado frente a software moderno como Famitracker, cuestionando la optimización para hardware de los 80 en contextos actuales).

![[Plantilla - 1MT#One More Thing]]