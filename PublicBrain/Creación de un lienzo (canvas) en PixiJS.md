---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.077Z
modified: 2024-04-06T23:49:42.223Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 2
nav_primary: []
nav_secondary: []
tags: []
---
# Creación de un lienzo (canvas) en PixiJS

[[Aprender sobre PixiJS]]

PixiJS es una potente biblioteca JavaScript para la creación de gráficos interactivos y experiencias visuales en la web. Aquí te muestro cómo puedes crear un lienzo (canvas) utilizando PixiJS:

1. **Instalación:**
   Primero, asegúrate de tener instalado Node.js y npm en tu sistema. Luego, puedes instalar PixiJS a través de npm ejecutando el siguiente comando en tu terminal:
   ```
   npm install pixi.js
   ```

2. **Creación del lienzo:**
   Una vez que hayas instalado PixiJS, puedes crear un lienzo en tu HTML donde se renderizarán los gráficos. Aquí tienes un ejemplo básico de cómo hacerlo:
   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Canvas con PixiJS</title>
       <script src="https://cdnjs.cloudflare.com/ajax/libs/pixi.js/5.3.3/pixi.min.js"></script>
       <style>
           body { margin: 0; }
           canvas { display: block; }
       </style>
   </head>
   <body>
       <script>
           // Crear una instancia de la clase Application de PixiJS
           const app = new PIXI.Application({
               width: 800,         // Ancho del lienzo en píxeles
               height: 600,        // Altura del lienzo en píxeles
               backgroundColor: 0x1099bb,   // Color de fondo del lienzo en formato hexadecimal
               antialias: true,    // Habilitar antialiasing para gráficos suaves
               transparent: false, // Lienzo transparente (false para fondo opaco)
               resolution: 1       // Resolución de píxeles del dispositivo (1 para dispositivos normales, 2 para dispositivos de alta resolución)
           });

           // Agregar el lienzo al cuerpo del documento HTML
           document.body.appendChild(app.view);
       </script>
   </body>
   </html>
   ```

   En este ejemplo, estamos creando una instancia de la clase `Application` de PixiJS con ciertas configuraciones, como el ancho y alto del lienzo, el color de fondo, la configuración de antialiasing, etc. Luego, agregamos el lienzo al cuerpo del documento HTML.

3. **Visualización del lienzo:**
   Al cargar este archivo HTML en un navegador web, deberías ver un lienzo de PixiJS con el tamaño especificado y el color de fondo.

Este es un ejemplo básico de cómo crear un lienzo con PixiJS. A partir de aquí, puedes comenzar a agregar elementos visuales como imágenes, formas y texto, y también trabajar con interacciones de usuario y animaciones para crear experiencias interactivas más complejas.