---
iaStatus: 8
iaStatus_Model: Grok-4, Raul Carrillo aka Metsuke
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations:
created: 2025-11-05T07:26:48.941Z
modified: 2025-11-05T21:43:50.452Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: "0"
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
---
# Curso de Programación de Videojuegos con Godot Engine 🔴②

> WIP
## Introducción al Curso

Este curso ofrece una formación completa y práctica en la programación de videojuegos con el motor Godot Engine, centrándonos en los lenguajes C y C++ mediante el sistema GDExtension, que permite integrar código nativo de manera eficiente en versiones de Godot 4 y superiores. 

En lugar de basarme en vídeos específicos de Fran Gallego, recurro a recursos equivalentes de Godot disponibles en YouTube, como la playlist "Using C++ in GODOT Engine Tutorial" (disponible en: https://www.youtube.com/playlist?list=PLZ2NyOcFnfQOko5ZysZeGkH3bfw2UtbOK), tutoriales de configuración de GDExtension y la documentación oficial. Para el uso de C puro, lo limitamos a módulos de bajo nivel, aunque C++ es el enfoque principal por su integración más fluida y potente.

 Los requisitos previos incluyen conocimientos intermedios de C/C++, como punteros, clases y gestión de memoria dinámica, junto con conceptos básicos de programación orientada a objetos. Las herramientas necesarias son Godot Engine (versión 4.5 o superior, gratuita), Visual Studio o VS Code con extensiones para C++, SCons para compilaciones y Git para el control de versiones.

## Unidad 1: Introducción a la Programación de Videojuegos y Godot

El objetivo general es comprender el panorama de la industria de los videojuegos y familiarizarse con el entorno de Godot, un motor ligero y open-source ideal para desarrollos independientes.

### Subtema 1.1: Panorama general de la industria

Exploramos una historia breve de los videojuegos, desde Pong hasta la realidad virtual y aumentada actual. Analizamos roles en un equipo, como programadores, artistas y diseñadores, y comparamos Godot con otros motores open-source, destacando su flexibilidad y bajo consumo de recursos.

Actividad: Investiga tres videojuegos indie desarrollados en Godot (por ejemplo, prototipos inspirados en Celeste) y analiza su arquitectura básica.

### Subtema 1.2: Instalación y primeros pasos en Godot

Descargamos e instalamos Godot Engine junto con herramientas de compilación como SCons o CMake. Revisamos la interfaz: editor de escenas, inspector, sistema de archivos y dock de nodos. Creamos un proyecto nuevo, diferenciando entre 2D y 3D.

Actividad: Genera un proyecto vacío, explora la interfaz y compila un "Hello World" simple en C++ para probar la integración.

### Subtema 1.3: Conceptos básicos de Nodes y Scenes

Entendemos la jerarquía de nodos en una escena (Node, Node2D, Node3D) y cómo las escenas actúan como recursos reutilizables, lo que facilita la modularidad.

Actividad: Añade un nodo Sprite2D y manipula su posición o transformación mediante código C++.

Referencias a recursos:
- Vídeo: "How to Setup Godot for C++" (https://www.youtube.com/watch?v=02KJouOjQ0c; duración aproximada: 20 minutos; cubre instalación y primeros nodos).
- Documentación: Introducción a GDExtension en Godot (https://docs.godotengine.org/en/stable/tutorials/scripting/gdextension/).
- Playlist principal: Vídeos 1-2 (configuración y nodos básicos).

## Unidad 2: Fundamentos de Scripting en C y C++ para Godot

Aquí dominamos los principios de programación en C y C++ integrados en Godot a través de GDExtension, que permite un rendimiento nativo sin recompilar el motor entero.

### Subtema 2.1: Introducción a C/C++ en Godot

Revisamos GDExtension: bindings, registro de clases y métodos. Estructuramos módulos en C++ (clases que heredan de Object o Node) y equivalentes al ciclo de vida (_init, _ready, _process). Compilamos con SCons y depuramos en Visual Studio.

Actividad: Crea una extensión en C++ que imprima "Hello Godot" en el método _ready().

### Subtema 2.2: Control de flujo y funciones en C/C++

Estudiamos estructuras condicionales (if, switch) y bucles (for, while) en bindings. Funciones expuestas a Godot (tipos void o Variant). Diferencias en manejo de memoria: malloc/free en C versus punteros inteligentes en C++.

Actividad: Implementa un contador de fotogramas en un script C++ adjunto a un nodo.

### Subtema 2.3: Clases y objetos avanzados

Profundizamos en herencia (extender Ref Node), polimorfismo, señales y slots en C++. Encapsulación con getters y setters.

Actividad: Desarrolla una clase base en C++ para un objeto de juego sencillo.

Referencias a recursos:
- Vídeo: "Godot GDExtensions PART 1: Setup on Windows and Linux" (https://www.youtube.com/watch?v=0gJqBvBXMS4; duración aproximada: 30 minutos; bindings básicos).
- Playlist principal: Vídeos 3-5 (scripting en C++, control de flujo).
- Documentación: Ejemplos de GDExtension en C++ (https://docs.godotengine.org/en/stable/tutorials/scripting/gdextension/gdextension_cpp_example.html).

## Unidad 3: Manejo de Entradas y Controles del Jugador

Implementamos interacciones del usuario de forma natural y eficiente en C y C++.

### Subtema 3.1: Input System de Godot en C++

Manejamos InputEvent y mapeo de acciones para teclado, ratón y mandos. Polling en _process() versus eventos en C++.

Actividad: Crea un script en C++ para mover un nodo RigidBody2D con teclas WASD.

### Subtema 3.2: Controles avanzados

Raycasting y detección de clics en C++ (usando PhysicsDirectSpaceState). Manejo de gestos táctiles en bajo nivel con C.

Actividad: Desarrolla un selector de nodos basado en eventos de entrada en C++.

### Subtema 3.3: Optimización de inputs

Eventos asíncronos y threading básico en C++. Configuración para múltiples plataformas mediante plantillas de exportación.

Actividad: Adapta controles para entrada táctil en un build para móvil.

Referencias a recursos:
- Vídeo: "C++ in Godot with Jenova" (https://www.youtube.com/watch?v=mCLhAet7TvI; duración aproximada: 25 minutos; manejo de entradas en GDExtension, actualizado en 2025).
- Playlist principal: Vídeos 6-7 (manejo de entradas).
- Documentación: Clase Input en C++ (https://docs.godotengine.org/en/stable/classes/class_input.html#class-input).

## Unidad 4: Física y Colisiones en Godot

Simulamos comportamientos físicos realistas, aprovechando la velocidad de C y C++ para cálculos intensivos.
### Subtema 4.1: Componentes de física

RigidBody2D/3D, CollisionShape en C++. Tipos de formas y uniones.

Actividad: Lanza una bola con física usando _integrate_forces en C++.
### Subtema 4.2: Detección de colisiones y triggers

Señales de colisión (body_entered) en callbacks de C++. Capas y máscaras en PhysicsBody.

Actividad: Implementa un sistema de puntuación en C al colisionar con ítems.

### Subtema 4.3: Fuerzas y torque

ApplyForce y ApplyTorque en C++. Configuración de masa y fricción.

Actividad: Crea un vehículo simple con aceleración en C++.

Referencias a recursos:
- Playlist principal: Vídeos 8-9 (física en C++).
- Documentación: Física en GDExtension (https://docs.godotengine.org/en/stable/tutorials/physics/index.html).
- Vídeo adicional: Busca "Godot C++ Physics Tutorial" en la playlist principal.

## Unidad 5: Animación y Modelado Básico

Integramos assets 2D/3D y animaciones, optimizando con código nativo.

### Subtema 5.1: Importación de assets

Modelos GLTF/FBX desde Blender, texturas. Carga dinámica en C++ con ResourceLoader.

Actividad: Importa un modelo y aplica material en C++.

### Subtema 5.2: Sistema de animación

AnimationPlayer y árboles en C++. Espacios de mezcla y parámetros.

Actividad: Configura animaciones de caminar/correr para un personaje en C++.

### Subtema 5.3: Rigging y skinning introductorio

Skeleton3D e IK en C++.

Actividad: Configura un rig humanoid en bajo nivel con C.

Referencias a recursos:
- Playlist principal: Vídeos 10-11 (animación).
- Vídeo: "Make C++ Games using Godot!!" (https://www.youtube.com/watch?v=8I_G-3Nii4k; duración aproximada: 15 minutos; básicos de assets).
- Documentación: AnimationPlayer en C++ (https://docs.godotengine.org/en/stable/classes/class_animationplayer.html).

## Unidad 6: Inteligencia Artificial y Pathfinding

Creamos comportamientos inteligentes para NPCs, donde C++ brilla en algoritmos complejos.

### Subtema 6.1: IA básica (Finite State Machines)

Estados en C++ (patrulla, persecución) con enums. Transiciones basadas en distancias (Vector2/3).

Actividad: Desarrolla un NPC que persiga al jugador en C++.

### Subtema 6.2: Pathfinding con Navigation

NavigationAgent2D/3D y mallas. Consultas de rutas en C++.

Actividad: Implementa una ruta automática en C++.

### Subtema 6.3: Comportamientos avanzados

Implementación básica de A* en C. Flocking con vectores.

Actividad: Crea un grupo de enemigos coordinados en C++.

Referencias a recursos:
- Playlist principal: Vídeos 12-14 (IA y pathfinding).
- Documentación: NavigationServer en C++ (https://docs.godotengine.org/en/stable/classes/class_navigationagent2d.html).

## Unidad 7: Interfaz de Usuario (UI) y Audio

Desarrollamos elementos visuales y sonoros para una experiencia inmersiva, integrados en C y C++.

### Subtema 7.1: Canvas y UI Elements

Nodos de control (Button, Label) en C++. Anclajes y diseños.

Actividad: Crea un menú principal en C++.

### Subtema 7.2: Audio en Godot

AudioStreamPlayer y mixer en C++. Sonidos 2D/3D.

Actividad: Añade efectos de sonido en colisiones con C.

### Subtema 7.3: Integración UI-Audio

HUD dinámico.

Actividad: Implementa una barra de vida con audio en C++.

Referencias a recursos:
- Playlist principal: Vídeos 15-16 (UI y audio).
- Documentación: GUI en C++ (https://docs.godotengine.org/en/stable/tutorials/ui/index.html).

## Unidad 8: Optimización, Testing y Publicación

Preparamos el juego para su distribución, enfocándonos en el rendimiento que ofrece el código nativo.

### Subtema 8.1: Profiling y optimización

Monitor de rendimiento en C++. Pooling de objetos en memoria con C.

Actividad: Optimiza una escena con muchos nodos en C++.

### Subtema 8.2: Testing y debugging

Pruebas unitarias con GTest en C++. Builds para plataformas.

Actividad: Prueba un script de IA.

### Subtema 8.3: Publicación y monetización

Exportaciones a Web, Android, PC. Integración con tiendas.

Actividad: Exporta y sube un prototipo.

Referencias a recursos:
- Vídeo: "C++ Scripting Comes to Godot!" (https://www.youtube.com/watch?v=Y2fbxkMrlCI; duración aproximada: 20 minutos; optimización actualizada en 2024).
- Playlist principal: Vídeos finales (builds).
- Documentación: Exportación (https://docs.godotengine.org/en/stable/tutorials/export/index.html).

## Unidad 9: Accesibilidad en Godot 4.5+

**Objetivo general:** Implementar funcionalidades de accesibilidad recién añadidas en Godot 4.5, como soporte para lectores de pantalla vía AccessKit, para hacer juegos inclusivos.
### Subtema 9.1: Introducción a la accesibilidad

AccessKit, soporte experimental para screen readers en nodos Control. Bindings para customizar en cualquier Node.

**Actividad:** Configura descripciones accesibles en un menú UI.

### Subtema 9.2: Elementos UI accesibles

FoldableContainer, efectos apilados en labels, overrides recursivos, iconos DPI-aware.

**Actividad:** Crea un acordeón accesible con descripciones.

### Subtema 9.3: Customización en C/C++

Extiende accessibility_tree y handlers en GDExtension para nodos custom.

**Actividad:** Nodo custom con accesibilidad en C++.

### Subtema 9.4: Mejores prácticas y testing

Opciones editor, TouchActionsPanel, detección de screen readers. Pruebas con herramientas externas.

**Actividad:** Integra accesibilidad en proyecto de Unit 7 y prueba.

**Referencias:**

- Release notes: "Godot 4.5, making dreams accessible".
- Vídeo: "Godot 4.5 is HERE! -- What's New?".
- Docs: UI y clases Control[](https://docs.godotengine.org/en/stable/tutorials/ui/index.html).
## Proyecto Final y Recursos Adicionales

Para el proyecto final, desarrolla un videojuego corto (por ejemplo, un platformer 2D) integrando al menos cinco unidades en C y C++. Duración: 12-18 horas. Rúbrica de evaluación: funcionalidad (40%), eficiencia en C++ (30%), optimización (20%) y documentación (10%).

Recursos adicionales:
- Playlist principal en YouTube (más de 20 vídeos para C++ en Godot).
- Documentación oficial de Godot (https://docs.godotengine.org/en/stable/).
- Comunidad: Foro de Godot o subreddit r/godot.
- Para C puro: Extiende GDExtension con bindings manuales (ver hilo en Reddit: https://www.reddit.com/r/godot/comments/lcdrex/how_to_learn_godotc/).

Actualizaciones: Consulta Godot 4.3+ para novedades en GDExtension (vigentes en 2025).

Este temario es exhaustivo y flexible. ¡Éxito en tu aprendizaje! Si quieres profundizar en alguna unidad, házmelo saber.

## Referencias bibliográficas que apoyan el contenido

> WIP: Revisando Fuentes

Estas fuentes respaldan el uso de C y C++ en Godot mediante GDExtension, destacando beneficios como mayor rendimiento en algoritmos complejos, integración con bibliotecas nativas y ejemplos prácticos.

- Godot Engine. (2025). Godot 4.5, making dreams accessible. https://godotengine.org/releases/4.5/. (Destaca integración AccessKit y screen readers).
- - Godot Engine. (2025). GDExtension (4.5). [https://docs.godotengine.org/en/4.5/tutorials/scripting/gdextension/index.html](https://docs.godotengine.org/en/4.5/tutorials/scripting/gdextension/index.html). (Soporte C++ nativo).
- ItsFoss. (2025). Godot 4.5 Release. [https://news.itsfoss.com/godot-4-5-release/](https://news.itsfoss.com/godot-4-5-release/). (Mejoras accesibilidad y workflow).
- Game Developer. (2025). Godot 4.5 accessibility. [https://www.gamedeveloper.com/programming/godot-4-5-ushers-in-accessibility-features-including-screen-reader-support](https://www.gamedeveloper.com/programming/godot-4-5-ushers-in-accessibility-features-including-screen-reader-support). (Beneficios screen readers).
- Godot Engine. (2024). GDExtension — Godot Engine (4.4) documentation in English. Disponible en: https://docs.godotengine.org/en/4.4/tutorials/scripting/gdextension/index.html. (Apoya la integración nativa y su compatibilidad con lenguajes como C++).

- Godot Engine. (2024). GDExtension C++ example. Disponible en: https://docs.godotengine.org/en/4.4/tutorials/scripting/gdextension/gdextension_cpp_example.html. (Proporciona tutoriales prácticos para configurar y usar C++ en proyectos).

- Snopek, D. (2024). C++ for Godot with GDExtension – David Snopek – GodotCon 2024 [Vídeo]. YouTube. Disponible en: https://www.youtube.com/watch?v=4R0uoBJ5XSk. (Explica ventajas como integración con bibliotecas externas y extensiones del motor sin recompilación).

- Gamefromscratch. (2024). Choosing Your Godot Programming Language: C#, C++, GDScript,... [Vídeo]. YouTube. Disponible en: https://www.youtube.com/watch?v=1VUDMFBpdZQ. (Compara lenguajes y resalta el control y velocidad de C++ para tareas intensivas).

- Reddit Community. (2025). What can C++ do better that Godot GDScript would have real difficulty with. Disponible en: https://forum.godotengine.org/t/what-can-c-do-better-that-godot-gdscript-would-have-real-difficulty-with/126005. (Discute beneficios en procesamiento de datos grandes y algoritmos avanzados).

## Referencias bibliográficas que refutan el contenido

> WIP: Revisando Fuentes

Estas fuentes critican o cuestionan el uso predominante de C y C++ en Godot, argumentando mayor complejidad, tiempo de desarrollo prolongado y que GDScript suele ser suficiente para la mayoría de proyectos, con rendimiento similar en casos no intensivos.

- GitHub Issue. (2025). Accessibility screen reader false positive. [https://github.com/godotengine/godot/issues/112247](https://github.com/godotengine/godot/issues/112247). (Problemas visuales por detección errónea).
- Reddit. (2024). C++ support in Godot. [https://www.reddit.com/r/godot/comments/1f0hwu6/how_good_is_c_support_in_godot/](https://www.reddit.com/r/godot/comments/1f0hwu6/how_good_is_c_support_in_godot/). (Complejidad innecesaria).
- Reddit. (2023). GDScript vs C++. [https://www.reddit.com/r/godot/comments/15ybgvn/is_it_advantageous_to_change_gdscript_to_c/](https://www.reddit.com/r/godot/comments/15ybgvn/is_it_advantageous_to_change_gdscript_to_c/). (Rendimiento similar para mayoría).
- Reddit Community. (2024). How Good is C++ Support in Godot? Disponible en: https://www.reddit.com/r/godot/comments/1f0hwu6/how_good_is_c_support_in_godot/. (Indica que usar C++ no siempre vale la pena debido a su complejidad, recomendando GDScript para la mayoría de casos).

- Reddit Community. (2024). Is there any reason to use GDScript if I'm very comfortable with C++. Disponible en: https://www.reddit.com/r/godot/comments/1dirbq0/is_there_any_reason_to_use_gdscript_if_im_very/. (Señala que C++ ralentiza el desarrollo y es mejor para módulos específicos, no para todo el código).

- Reddit Community. (2023). Is it advantageous to change GDScript to C++? Disponible en: https://www.reddit.com/r/godot/comments/15ybgvn/is_it_advantageous_to_change_gdscript_to_c/. (Argumenta que para el 99% del código, el rendimiento es similar y C++ añade complejidad innecesaria).

- Facebook Community. (2024). What has been your experience using C++ in Godot? Disponible en: https://www.facebook.com/groups/godotengine/posts/3158494324287140/. (Critica la falta de recolección de basura en C++, requiriendo gestión manual de memoria, lo que complica el desarrollo).

- Chickensoft. (2023). GDScript vs C# in Godot 4. Disponible en: https://chickensoft.games/blog/gdscript-vs-csharp. (Aunque enfocado en C#, menciona penalizaciones en llamadas al motor desde código nativo, aplicable a C++, y favorece GDScript por simplicidad).

![[Plantilla - 1MT#One More Thing]]