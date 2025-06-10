---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-15T05:40:36.597Z
modified: 2025-06-10T21:14:05.613Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
---
# Precarga de recursos para una experiencia más fluida en PixiJS

[[Curso de PixiJS ⚫①]]

La precarga de recursos es una técnica esencial en el desarrollo de juegos y aplicaciones web con PixiJS para garantizar una experiencia más fluida y evitar retrasos durante la ejecución. Aquí te explico cómo puedes implementar la precarga de recursos en PixiJS:

1. **Identificar los recursos a precargar**:
   - Antes de comenzar a precargar recursos, identifica todos los archivos necesarios para tu juego o aplicación, como imágenes, archivos de audio, archivos JSON para datos de mapa, entre otros.

2. **Usar el cargador de PixiJS**:
   - PixiJS proporciona una clase llamada `Loader` que te permite cargar recursos de manera asíncrona antes de que comience la renderización de la escena.
   - Para usar el cargador, primero crea una instancia de la clase `Loader`:
     ```javascript
     const loader = PIXI.Loader.shared;
     ```
   - Luego, puedes agregar recursos a cargar utilizando el método `add()`:
     ```javascript
     loader.add("imagen1", "ruta/a/imagen1.png");
     loader.add("imagen2", "ruta/a/imagen2.png");
     // Agrega más recursos según sea necesario
     ```

3. **Escuchar eventos de progreso y completado**:
   - El cargador de PixiJS emite eventos que te permiten monitorear el progreso de carga y saber cuándo se han cargado todos los recursos.
   - Puedes escuchar el evento `'progress'` para actualizar una barra de progreso, por ejemplo:
     ```javascript
     loader.onProgress.add((loader, recurso) => {
         console.log(`Progreso: ${loader.progress}%`);
     });
     ```
   - También puedes escuchar el evento `'complete'` para realizar acciones una vez que todos los recursos se hayan cargado:
     ```javascript
     loader.onComplete.add(() => {
         console.log("¡Todos los recursos se han cargado!");
         // Aquí puedes inicializar tu juego o aplicación
     });
     ```

4. **Iniciar la carga de recursos**:
   - Una vez que hayas agregado todos los recursos y configurado los manejadores de eventos, puedes iniciar la carga utilizando el método `load()` del cargador:
     ```javascript
     loader.load();
     ```

5. **Acceder a los recursos cargados**:
   - Después de que todos los recursos se hayan cargado con éxito, puedes acceder a ellos a través del objeto `resources` del cargador:
     ```javascript
     const imagen1 = loader.resources["imagen1"].texture;
     const imagen2 = loader.resources["imagen2"].texture;
     // Usa las texturas en tu juego o aplicación
     ```

Implementar la precarga de recursos en PixiJS garantiza que tu juego o aplicación tenga acceso rápido a todos los recursos necesarios, lo que ayuda a mejorar la experiencia del usuario al evitar retrasos causados por la carga de recursos durante la ejecución.