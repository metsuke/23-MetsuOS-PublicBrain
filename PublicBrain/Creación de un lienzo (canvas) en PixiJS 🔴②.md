---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo, llama3-70b-8192
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.077Z
modified: 2024-05-27T13:38:00.861Z
supervisado: 2024-05-13T20:02:38.309Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 10
nav_primary: 
nav_secondary: 
tags:
---
# Creación de un lienzo (canvas) en PixiJS 🔴②

[[Aprender sobre PixiJS ⚫①]]

PixiJS es una potente biblioteca JavaScript para la creación de gráficos interactivos y experiencias visuales en la web. En este artículo, te mostraremos cómo crear un lienzo (canvas) utilizando PixiJS.

## Instalación

Primero, asegúrate de tener instalado Node.js y npm en tu sistema. Luego, puedes instalar PixiJS a través de npm ejecutando el siguiente comando en tu terminal:

```bash
npm install pixi.js
```

## Creación del lienzo

Una vez que hayas instalado PixiJS, puedes crear un lienzo en tu HTML donde se renderizarán los gráficos. Aquí tienes un ejemplo básico de cómo hacerlo:

```html
<!DOCTYPE html>
<html lang="es">
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

## Visualización del lienzo

Al cargar este archivo HTML en un navegador web, deberías ver un lienzo de PixiJS con el tamaño especificado y el color de fondo.

## Referencias bibliográficas que apoyan el contenido

- PixiJS. (s.f.). Pixi.js Documentation. Recuperado de [https://pixijs.com/docs/](https://pixijs.com/docs/)
- Mozilla Developer Network. (s.f.). HTML &lt;canvas&gt; Element. Recuperado de [https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)

## Referencias que refutan el contenido

* No se encontraron referencias que refuten el contenido presentado.

Esperamos que este artículo te haya sido útil para crear un lienzo con PixiJS. ¡Comienza a explorar y crear experiencias visuales y interactivas con PixiJS!

![[⚫🔴🟡🟢🔵⚪ (🔴②)#Sobre el sistema de validez de un contenido en MetsuOS]]