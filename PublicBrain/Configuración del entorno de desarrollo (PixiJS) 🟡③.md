---
iaStatus: 8
iaStatus_Model: Grok-3, Raúl Carrillo aka Metsuke
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.031Z
modified: 2025-06-20T15:54:31.910Z
supervisado: 2024-05-27T13:38:00.774Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 19
nav_primary: 
nav_secondary: 
tags:
---
# Configuración del entorno de desarrollo (PixiJS) 🟡③

![Crea juegos 2D Increibles!](PublicBrain/_resources/49b733e9330b37e5403f93a3ad5632d6_MD5.jpg)

* [[Curso de PixiJS ⚫①]]
* [[Qué es PixiJS y su historia 🟡③|<< Anterior]] | [[Creación de un lienzo (canvas) en PixiJS 🟡③|Siguiente >>]]

PixiJS es una biblioteca potente y ligera para crear gráficos 2D interactivos en la web, ideal para desarrollar juegos y aplicaciones visuales. Configurar un entorno de desarrollo para PixiJS es sencillo si sigues estos pasos claros y actualizados. ¡Prepárate para dar vida a tus ideas!

## 1. Configura un Servidor Local 🌐

Anteriormente se recomendaba instalar el servidor local luego integrar Pixi, actualmente, existe una herramienta que automatiza el proceso completo, ampliando las opciones enormemente.
  
```bash
npm create pixi.js@latest
```
    
En mi caso he seleccionado Vite (JS) de entre las opciones de "Bundler Templates", hay muchas, puedes explorarlas, por mi parte quiero centrarme en el desarrollo del juego en si, por lo que dejaré esto en manos de los creadores de Pixi salvo que necesitemos algo especifico mas adelante.

Una vez hecho esto, entramos en la carpeta y consolidamos la instalación:

```bash
cd mi-proyecto
npm install
```

## 2. La Estructura inicial de tu Proyecto 📂

Una buena organización es clave para que tu proyecto sea escalable. Esta es la que nos ofrece el instalador inicialmente:

```
mi-proyecto/
├── eslint.config.mjs
├── index.html
├── node_modules/
├── package.json
├── public/
│   ├── assets/
│   │   ├── bunny.png
│   │   └── logo.svg
│   ├── favicon.png
│   └── style.css
├── src/
│   └── main.js
└── vite.config.js
```
## 3. Lanza tu Proyecto 🚴‍♂️

Ahora puedes lanzar tu proyecto con: 

```bash
npm run dev
```

Se lanzara el servidor local y se abrirá directamente un navegador que jecutará el ejemplo por defecto.

En el proximo capítulo, veremos el codigo por defecto de nuestro lienzo y os enlazaré la lista de parametros que podeis usar en el init().

## Referencias Bibliográficas 📚

- [PixiJS. (2025). Guías oficiales de PixiJS 🌐🟡③](https://pixijs.com/guides/)
	- La página oficial de PixiJS ofrece guías actualizadas para la versión 8.x, vigentes a 2025.
- [npm. (2025). pixi.js 🌐🟡③](https://www.npmjs.com/package/pixi.js)
	- El paquete oficial en npm está activo y documenta la instalación de la versión 8.3.3.
- [MDN Web Docs. (2024). Elemento Canvas de HTML 🌐🟡③](https://developer.mozilla.org/es/docs/Web/HTML/Element/canvas)
	- MDN es una fuente confiable y actualizada para estándares web, incluyendo el uso de `<canvas>`.
- [Vite. (2025). Guía de inicio rápido 🌐🟡③](https://vite.dev/guide/) 
	- La documentación de Vite está actualizada y es la referencia oficial para configurar proyectos con módulos ES.
## Referencias que Refutan o Complementan 🔍

- **Ninguna fuente verificable disponible**. 


![[Plantilla - 1MT#One More Thing]]