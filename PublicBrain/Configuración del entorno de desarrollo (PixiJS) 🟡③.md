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
modified: 2025-06-17T21:06:43.502Z
supervisado: 2024-05-27T13:38:00.774Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 16
nav_primary: 
nav_secondary: 
tags:
---
# Configuración del entorno de desarrollo (PixiJS) 🟡③

![Crea juegos 2D Increibles!](PublicBrain/_resources/49b733e9330b37e5403f93a3ad5632d6_MD5.jpg)

[[Curso de PixiJS ⚫①]]

PixiJS es una biblioteca potente y ligera para crear gráficos 2D interactivos en la web, ideal para desarrollar juegos y aplicaciones visuales. Configurar un entorno de desarrollo para PixiJS es sencillo si sigues estos pasos claros y actualizados. ¡Prepárate para dar vida a tus ideas!

## 1. Configura un Servidor Local 🌐

Para evitar restricciones de seguridad del navegador, como las políticas de CORS, PixiJS debe ejecutarse desde un servidor web local. Aquí tienes algunas opciones modernas y fáciles de usar:

- **Vite**: Un servidor de desarrollo rápido y eficiente, perfecto para proyectos modernos. Instálalo con:
    
    ```bash
    npm create vite@latest
    ```
    
    Elige la plantilla "Vanilla" y sigue las instrucciones en pantalla.
    
- **Node.js con http-server**: Una solución ligera y directa. Instálalo globalmente:
    
    ```bash
    npm install -g http-server
    ```
    
    Luego, ejecuta `http-server` desde la carpeta de tu proyecto.
    
- **Otras opciones**: Si prefieres herramientas tradicionales, puedes usar XAMPP, WAMP o MAMP, aunque son menos recomendadas para proyectos ágiles.
    

**Consejo**: Vite es la opción ideal por su velocidad y compatibilidad con módulos ES, lo que facilita trabajar con PixiJS.

## 2. Instala PixiJS 📦

Incorpora PixiJS a tu proyecto de la forma que mejor se adapte a tus necesidades:

- **Con npm (recomendado)**:  
    Instala PixiJS como dependencia de tu proyecto:
    
    ```bash
    npm install pixi.js
    ```
    
    Luego, impórtalo en tu código JavaScript:
    
    ```javascript
    import * as PIXI from 'pixi.js';
    ```
    
- **Desde CDN**:  
    Si no quieres instalar nada, incluye PixiJS directamente en tu HTML:
    
    ```html
    <script src="https://cdnjs.cloudflare.com/ajax/libs/pixi.js/8.3.3/pixi.min.js"></script>
    ```
    
- **Descarga manual**:  
    Descarga la biblioteca desde la página oficial de PixiJS y enlázala en tu HTML:
    
    ```html
    <script src="path/to/pixi.min.js"></script>
    ```
    

**Nota**: La versión 8.3.3 es la más reciente a junio de 2025. Verifica la última versión en [npmjs.com/package/pixi.js 🌐🟡③](https://www.npmjs.com/package/pixi.js).

## 3. Organiza la Estructura de tu Proyecto 📂

Una buena organización es clave para que tu proyecto sea escalable. Esta es una estructura sugerida:

```
mi-proyecto/
├── index.html
├── src/
│   ├── main.js
│   └── assets/
│       └── imagen.png
├── package.json
└── node_modules/
```

### Crea el archivo HTML (`index.html`)

Configura un archivo HTML limpio y optimizado para tu juego:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mi Juego con PixiJS</title>
  <style>
    body { margin: 0; display: flex; justify-content: center; align-items: center; min-height: 100vh; background: #000; }
    canvas { border: 1px solid #fff; }
  </style>
</head>
<body>
  <canvas id="game-canvas"></canvas>
  <script type="module" src="src/main.js"></script>
</body>
</html>
```

**Detalles**:

- El atributo `lang="es"` mejora la accesibilidad.
- El `viewport` asegura compatibilidad con dispositivos móviles.
- Los estilos centran el canvas y le dan un fondo oscuro para destacar.

## 4. Inicializa PixiJS en JavaScript 🎨

Crea un archivo `main.js` en la carpeta `src` para empezar a usar PixiJS:

```javascript
import * as PIXI from 'pixi.js';

// Configura la aplicación PixiJS
const app = new PIXI.Application({
  view: document.getElementById('game-canvas'),
  width: 800,
  height: 600,
  backgroundColor: 0x1099bb,
  antialias: true,
});

// Carga una textura y crea un sprite
const texture = await PIXI.Assets.load('assets/imagen.png');
const sprite = new PIXI.Sprite(texture);
sprite.x = app.screen.width / 2;
sprite.y = app.screen.height / 2;
sprite.anchor.set(0.5); // Centra el sprite
app.stage.addChild(sprite);

// Animación básica
app.ticker.add(() => {
  sprite.rotation += 0.01;
});
```

**Notas**:

- Usa `PIXI.Application` para configurar el canvas y el renderer automáticamente.
- `PIXI.Assets.load` carga recursos de forma asíncrona, ideal para imágenes o sonidos.
- Asegúrate de que el archivo `assets/imagen.png` exista en tu proyecto.

## 5. Lanza tu Proyecto 🚴‍♂️

1. Inicia tu servidor local:
    
    - Con Vite: `npm run dev`.
    - Con http-server: `http-server`.
    - Con XAMPP: Activa Apache y accede a `http://localhost/tu-proyecto`.
2. Abre tu navegador y visita la URL proporcionada (por ejemplo, `http://localhost:5173` para Vite).
    
3. Comprueba que el canvas se muestre y que el sprite rote suavemente.
    

## 6. Trucos para Mejorar tu Flujo de Trabajo 🛠️

- **TypeScript**: PixiJS es compatible con TypeScript, lo que te ayuda a detectar errores más rápido. Instala los tipos con:
    
    ```bash
    npm install @pixi/js
    ```
    
- **PixiJS DevTools**: Usa esta extensión para Chrome para inspeccionar y depurar tu escena gráfica.
    
- **Carga de recursos**: Aprovecha `PIXI.Assets` para gestionar imágenes, sonidos o datos JSON de forma eficiente.
    
- **Despliegue**: Cuando estés listo, compila tu proyecto con `npm run build` (si usas Vite) y súbelo a plataformas como Netlify o Vercel.

En el proximo capítulo, haremos la prueba y afinaremos este documento en consecuencia. Usare la formula standard con Vite.
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

- **No siempre es necesario un servidor local**: Como se menciona en la documentación de PixiJS ([https://pixijs.com/guides/basics/getting-started 🌐🟡③](https://pixijs.com/guides/basics/getting-started)), puedes abrir un archivo HTML directamente en el navegador usando la bandera `--allow-file-access-from-files` en Chrome. Sin embargo, esto no es práctico para proyectos reales, ya que limita la carga de recursos externos como imágenes o sonidos.
- **Alternativas a Vite para servidores locales**: La documentación de Node.js ([https://nodejs.org/en/docs/guides/getting-started-guide 🌐🟡③](https://nodejs.org/en/docs/guides/getting-started-guide)) sugiere otras herramientas como `express` para crear servidores locales, lo que puede ser útil para proyectos más complejos.


![[Plantilla - 1MT#One More Thing]]