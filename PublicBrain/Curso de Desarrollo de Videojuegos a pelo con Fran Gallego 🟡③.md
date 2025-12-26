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
created: 2025-12-25T15:38:00.689Z
modified: 2025-12-26T01:19:40.661Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: DesarrolloJuegosFranGallego_000.mp4
---
# Curso de Desarrollo de Videojuegos a pelo con Fran Gallego 🟡③

![Curso de Desarrollo de Videojuegos a pelo con Fran Gallego](_resources/f9331a87d84f315753172d2a1d04bf87_MD5.jpg)

[[Aprender a desarrollar videojuegos  ⚫①]]

**DISCLAIMER** En este curso trataré de condensar mi propio aprendizaje en torno al desarrollo de videojuegos a pelo insipirado en las clases de Fran Gallego publicadas online. En ningun caso es un curso oficial de Fran Gallego, sino mis "apuntes avanzados" aprendiendo con sus contenidos online.


Desarrollar "a pelo" no es lo más rápido, pero te da una comprensión profunda de cómo funcionan los videojuegos. Este curso te equipa con habilidades para crear prototipos, experimentar sin límites y, si quieres, dar el salto a motores comerciales con una base sólida. ¡Es tu oportunidad de programar como los pioneros de los 90, pero con herramientas modernas!
## Introducción

¿Alguna vez has querido crear un videojuego desde cero, sin depender de motores como Unity o Unreal? En este **Curso de Desarrollo de Videojuegos a Pelo**, te mostraré lo que vaya aprendiendo de la mano del contenido de Fran Gallego, e intentaré guíarte paso a paso para construir juegos desde sus cimientos, usando C++ y herramientas como SDL2 y OpenGL. 

Este enfoque "a pelo" te permitirá entender cómo funcionan los videojuegos por dentro - una vez lo entienda yo mismo - , desde el bucle principal hasta los gráficos 3D, dándote un control total sobre cada píxel y cada cálculo.

Este curso es ideal tanto para principiantes con conocimientos básicos de programación como para desarrolladores que quieran profundizar en los entresijos técnicos del desarrollo de videojuegos. 

A lo largo de los módulos, trabajarás en proyectos prácticos, desde un simple "Hello, Game!" hasta un plataformas 2D completo, aprendiendo con un estilo claro, directo y con un toque de humor... dado el tamaño del reto, nos hará falta a ambos xD

¡Prepárate para programar, depurar y, sobre todo, crear!

## Objetivos del Curso

- Comprender los fundamentos del desarrollo de videojuegos sin motores.
- Dominar C++ y bibliotecas como SDL2 y OpenGL para crear juegos 2D y 3D.
- Implementar mecánicas esenciales: física, colisiones, animaciones, audio e IA.
- Construir un juego publicable desde cero y aprender a optimizarlo.
- Desarrollar habilidades para crear tus propios prototipos o incluso un motor personalizado.

## Estructura del Curso

El curso está dividido en **11 módulos** progresivos, combinando teoría, ejemplos prácticos y proyectos acumulativos. Cada módulo incluye ejercicios para reforzar lo aprendido y culmina en un proyecto que integra los conceptos ¡Al lio!
### Módulo 1: Primeros Pasos en el Desarrollo de Videojuegos

1. **¿Qué es desarrollar "a pelo"?**  
   Aprende las diferencias entre programar desde cero y usar motores preexistentes, con ejemplos de juegos clásicos como *DOOM*. Descubre por qué este enfoque te da un control único.  
   - Ejemplo: Comparación entre el código de *Quake* y un proyecto en Unity.
2. **Configura tu entorno**  
   Instala las herramientas esenciales: compiladores (GCC, Clang), IDEs (Visual Studio Code) y bibliotecas como SDL2. Configura tu equipo en Windows, macOS o Linux.  
   - Práctica: Compila un programa básico en C++.  
3. **Anatomía de un videojuego**  
   Entiende los pilares de un juego: bucle principal, entrada, renderizado y lógica. Explora el ciclo de desarrollo desde el prototipo hasta el producto final.  
   - Ejemplo: Crea una ventana con SDL2 que cambie de color.  
4. **Proyecto: "Hello, Game!"**  
   Desarrolla tu primer programa: una ventana que responde al teclado (cierra con Escape).  

### Módulo 2: Fundamentos de Programación para Juegos

2.1 **Programación en C++**  
   Domina los conceptos clave: variables, funciones, clases y gestión de memoria. Aprende a escribir código limpio y modular.  
   - Ejercicio: Crea una clase `Entity` para representar objetos en el juego.  
2.2 **Matemáticas para videojuegos**  
   Descubre cómo usar vectores, matrices y trigonometría para mover objetos y calcular colisiones.  
   - Ejemplo: "I"mplementa una clase `Vector2D` con suma y producto escalar.  
   - Fórmula: Producto escalar de dos vectores \( \vec{a} \cdot \vec{b} = a_x b_x + a_y b_y \).  
2.3 **Estructuras de datos**  
   Usa arrays, listas y colas para gestionar enemigos, balas o niveles.  
   - Práctica: Crea una lista dinámica para almacenar entidades.  
2.4 **Proyecto: Juego de rebote**  
   Crea un juego donde una pelota rebota en los bordes y una paleta controlada por teclado la golpea.  

### Módulo 3: El Corazón del Juego: El Bucle Principal

3.1 **El game loop**  
   Aprende cómo funciona el bucle principal y cómo usar *delta time* para que el juego sea fluido en cualquier equipo.  
   - Ejemplo: Implementa un bucle con \( \Delta t = \frac{1}{\text{FPS}} \).  
3.2 **Gestión del tiempo**  
   Controla los FPS y sincroniza el renderizado. Muestra los FPS en pantalla.  
   - Práctica: Limita el juego a 60 FPS.  
3.3 **Entrada del jugador**  
   Gestiona teclado, ratón y gamepads con SDL2. Crea controles personalizables.  
   - Ejercicio: Añade soporte para mover la paleta con ratón.  
3.4 **Proyecto: Breakout básico**  
   Transforma el juego de rebote en un clon de *Breakout* con ladrillos y puntuación.  

### Módulo 4: Gráficos 2D
4.1 **Renderizado 2D**  
   Aprende a dibujar píxeles, sprites y texturas con SDL2. Carga imágenes (PNG).  
   - Ejemplo: Muestra un sprite estático en pantalla.  
4.2 **Animaciones**  
   Crea animaciones con spritesheets (caminar, saltar).  
   - Práctica: Anima un personaje corriendo.  
4.3 **Cámara 2D**  
   Implementa una cámara que siga al jugador o explore el nivel.  
   - Ejemplo: Transforma coordenadas del mundo a pantalla.  
4.4 **Proyecto: Plataformer 2D**  
   Desarrolla un juego de plataformas con un personaje, suelos y obstáculos animados.  

### Módulo 5: Física y Colisiones

5.1 **Física básica**  
   Añade velocidad, aceleración y gravedad a tus objetos.  
   - Fórmula: Posición con gravedad \( y_t = y_0 + v_0 t - \frac{1}{2} g t^2 \).  
5.2 **Detección de colisiones**  
   Implementa colisiones AABB y círculo-círculo.  
   - Ejemplo: Detecta si dos personajes se tocan.  
5.3 **Resolución de colisiones**  
   Evita que los objetos se atraviesen (empujar o detener).  
   - Práctica: "H"az que el jugador no atraviese paredes.  
5.4 **Proyecto: Plataformer mejorado**  
   Añade físicas realistas y colisiones al juego de plataformas.  

### Módulo 6: Sonido

6.1 **Audio en videojuegos**  
   Descubre cómo usar música y efectos de sonido con SDL2_Mixer.  
   - Ejemplo: Reproduce un sonido al saltar.  
6.2 **Gestión de audio**  
   Controla música de fondo y mezcla efectos.  
   - Práctica: Añade música al menú del juego.  
6.3 **Efectos espaciales**  
   Simula audio 2D ajustando el volumen según la distancia.  
   - Ejemplo: Sonido más fuerte cerca del jugador.  
6.4 **Proyecto: Plataformer con audio**  
   Integra música y efectos en el juego de plataformas.  

### Módulo 7: Introducción a Gráficos 3D

7.1 **Fundamentos 3D**  
   Aprende sobre vértices, polígonos y el pipeline gráfico con OpenGL.  
   - Ejemplo: Renderiza un cubo 3D.  
7.2 **Modelos y mallas**  
   Carga modelos simples (OBJ).  
   - Práctica: Muestra un objeto 3D rotando.  
7.3 **Cámara 3D**  
   Crea una cámara libre estilo FPS.  
   - Fórmula: Matriz de proyección \( P = \begin{bmatrix} \frac{1}{\tan(\theta/2)} & 0 & 0 & 0 \\ 0 & \frac{1}{\tan(\theta/2)} & 0 & 0 \\ 0 & 0 & -\frac{f+n}{f-n} & -1 \\ 0 & 0 & -\frac{2fn}{f-n} & 0 \end{bmatrix} \).  
7.4 **Proyecto: Escena 3D**  
   Construye una escena con un objeto 3D y una cámara móvil.  

### Módulo 8: Inteligencia Artificial y Lógica

8.1 **IA para enemigos**  
   Usa máquinas de estados (patrullar, atacar).  
   - Ejemplo: Enemigo que persigue al jugador.  
8.2 **Pathfinding**  
   Implementa A* para que los enemigos eviten obstáculos.  
   - Práctica: Enemigo que encuentra el camino al jugador.  
8.3 **Eventos**  
   Crea triggers para puertas o trampas.  
   - Ejemplo: Abre una puerta al tocar un objeto.  
8.4 **Proyecto: Plataformer con IA**  
   Añade enemigos inteligentes y eventos al juego.  

### Módulo 9: Optimización y Depuración

9.1 **Optimización**  
   Reduce el uso de CPU/GPU con técnicas como *frustum culling*.  
   - Ejemplo: Optimiza el renderizado de sprites.  
9.2 **Depuración**  
   Usa logs y herramientas como RenderDoc para encontrar errores.  
   - Práctica: Arregla un bug en el juego.  
9.3 **Testing**  
   Crea pruebas unitarias para la lógica del juego.  
   - Ejemplo: Testea colisiones masivas.  
9.4 **Proyecto: Juego pulido**  
   Optimiza el plataformer para 60 FPS y añade un menú.  

### Módulo 10: Publicar tu Juego

10.1 **Preparación**  
   Compila para Windows, macOS y Linux. Crea ejecutables.  
   - Ejemplo: Exporta el plataformer.  
10.2 **Distribución**  
   Sube tu juego a itch.io o Steam con capturas y descripción.  
   - Práctica: Crea una página para tu juego.  
10.3 **Mantenimiento**  
   Recoge feedback y lanza parches.  
   - Ejemplo: Añade una nueva mecánica tras comentarios.  
10.4 **Proyecto: Lanzamiento**  
   Publica el plataformer como demo en itch.io.  

### Módulo 11: Temas Avanzados

11.1 **Multijugador**  
   Crea un prototipo en red con sockets.  
   - Ejemplo: Sincroniza el movimiento de dos jugadores.  
11.2 **Shaders**  
   Escribe efectos gráficos en GLSL (luz, sombras).  
   - Práctica: Crea un efecto de agua 2D.  
11.3 **Motores personalizados**  
   Diseña un mini-motor reutilizable.  
   - Ejemplo: Refactoriza el plataformer como motor.  
11.4 **Proyecto: Prototipo libre**  
   Crea un juego pequeño aplicando todo lo aprendido (shooter, puzzle, etc.).  

## Por Qué Elegir Este Curso


---

## Referencias Bibliográficas

### Fuentes que Apoyan el Enfoque del Curso

Estas referencias respaldan el desarrollo de videojuegos desde cero con C++ y bibliotecas como SDL2/OpenGL, destacando su valor educativo y técnico.

1. [Game Programming Patterns (2014) 🟡③🌐](https://gameprogrammingpatterns.com/) .- Sitio oficial del libro de Robert Nystrom que ofrece el contenido completo online de forma gratuita, con patrones de diseño para código de videojuegos.
2. [SDL Game Development (2013) 🟡③🌐](https://www.packtpub.com/product/sdl-game-development/9781849696821) .- Página de Packt Publishing donde el libro de Shaun Mitchell está disponible para compra en formatos print y eBook.
3. ["The Cherno - OpenGL Series (YouTube, 2019-2023)  🟡③🌐](https://www.youtube.com/playlist?list=PLlrATfBNZ98foTJPJ_Ev03o2oq3-GGOS2) .- Playlist de YouTube de The Cherno con 31 vídeos tutoriales sobre OpenGL desde cero con ejemplos en C++.
4. [Matemáticas para Videojuegos (2018) 🟡③🌐](https://www.routledge.com/3D-Math-Primer-for-Graphics-and-Game-Development-2nd-Edition/Dunn-Parberry/p/book/9781568817231) .- Libro "3D Math Primer for Graphics and Game Development" (2ª edición) de Fletcher Dunn e Ian Parberry, guía esencial de matemáticas para gráficos y desarrollo de juegos. (edición tercera no localizada; enlace a la segunda edición vigente)

### Fuentes que Critican o Refutan el Enfoque del Curso

Estas referencias abogan por usar motores como Unity o Unreal Engine, argumentando que son más eficientes y accesibles, especialmente para principiantes o proyectos comerciales.

1. ["Unity in Action" (2018) 🟡③🌐](https://www.manning.com/books/unity-in-action-second-edition) .- Libro de Joseph Hocking que enseña desarrollo de juegos con Unity, destacando su facilidad para prototipos rápidos y para desarrolladores novatos.
2. ["Introduction to Game Development with Unreal Engine" (2021) 🟡③🌐](https://link.springer.com/book/10.1007/978-1-4842-9824-4) .- Guía de Jessica Plowman sobre desarrollo de juegos con Unreal Engine, destacando su potencia visual y herramientas integradas.
3. ["Learning C# by Developing Games with Unity" (2020) 🟡③🌐](https://www.amazon.com/Learning-Developing-Games-Unity-2020/dp/1800207808) .- Libro de Harrison Ferrone que enseña C# mediante el desarrollo de juegos en Unity.

---


![[Plantilla - 1MT#One More Thing]]
