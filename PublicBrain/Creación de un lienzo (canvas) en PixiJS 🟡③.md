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
created: 2024-04-06T23:48:59.077Z
modified: 2025-06-20T15:04:08.867Z
supervisado: 2024-05-27T13:38:00.861Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 15
nav_primary: 
nav_secondary: 
tags:
---
# Creación de un lienzo (canvas) en PixiJS 🟡③

![Instrucciones para crear un lienzo den PixiJS](PublicBrain/_resources/4f0ba2547abc282a498380f2e70654ec_MD5.jpeg)

* [[Curso de PixiJS ⚫①]]
* [[Configuración del entorno de desarrollo (PixiJS) 🟡③|<< Anterior]] | Siguiente >>

PixiJS es una biblioteca JavaScript versátil y potente que permite crear gráficos interactivos y experiencias visuales en la web de manera eficiente. En este artículo, te guiaremos paso a paso para configurar un lienzo (canvas) con PixiJS, preparando el escenario para tus proyectos gráficos.

## Configuración del lienzo

Tras instalar PixiJS ([[Configuración del entorno de desarrollo (PixiJS) 🟡③|consulta el artículo anterior sobre instalación]]), ya dispondrás de un html con un lienzo básico, y un main.js con el codigo de la app,  analicemos este código:

```html
<!doctype html>
<html lang="en">
<head>
	<meta charset="UTF-8" />
	<link rel="icon" type="image/png" href="/favicon.png" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<link rel="stylesheet" href="/style.css">
	<title>PixiJS - Template</title>
</head>

<body>
	<div id="app">
		<div id="pixi-container"></div>
	</div>
	<script type="module" src="/src/main.js"></script>
</body>
</html>
```

Aqui nada novedoso, un simple html basico que incorpora la css, el coigo de la app (main.js) y listo. 

Lo unico aqui es que quiero poder integrar programas (en plural) dentro de esta web, sin que interfiera con el resto de la web ni requerir servidores especializados para node ... eso lo exploraré en el próximo capítulo.

Veamos el js, he cambiado los comentarios del codigo originales por los mios, creo que es el modo más eficaz de explicarlo:

```js
import { Application, Assets, Sprite } from "pixi.js";
// Importación de los módulos necesarios para el funcionamiento de pixi.js

(async () => {
  // Crea una nueva aplicación
  const app = new Application();

  // Inicializa la app con el colog de fondo y asignando el tamaño del lienzo a toda la ventana.
  await app.init({ background: "#1099bb", resizeTo: window });

  // Añade la app en el contenedor que habiamos creado en el html para ello.
  document.getElementById("pixi-container").appendChild(app.canvas);

  // Carga la textura del conejo que viene por defecto.
  const texture = await Assets.load("/assets/bunny.png");

  // Crea, usando la textura, el Sprite que manejaremos
  const bunny = new Sprite(texture);

  // Centra el sprite anclandolo a un punto concreto.
  bunny.anchor.set(0.5);

  // Situa el sprite en el centro de la pantalla
  bunny.position.set(app.screen.width / 2, app.screen.height / 2);

  // Añade el sprite del conejo a la escena
  app.stage.addChild(bunny);

  // Bucle principal de animación 
  app.ticker.add((time) => {
    // Como ejemplo, rotamos el conejo en pantalla
    // * Delta sera 1 si se ejecuta al 100% de rendimiento *
    // * Crea la rotación mediante una transformación que lo gira poco  a poco *
    bunny.rotation += 0.1 * time.deltaTime;
  });
})();
```

Si quieres jugar con los parametros, aquí tienes una lista de lo que puedes asignar a un lienzo [Parametros de Application > Init (en Inglés)](https://pixijs.download/v4.8.9/docs/PIXI.Application.html)

```pre
No voy a enseñar Javascript aquí, hay muchos tutoriales y cursos online que seguramente sean mucho mejores que lo que yo pueda aportar, en cambio me centraré en crear con pixi.js
```
## Visualización del lienzo

Tan simple como ejecutar nuestro proyecto con:

```bash
npm run dev
```

En el proximo capítulo veremos como voy a integrar esta tecnología directamente en MetsuOS, mi idea es crear un script build-mos para asi faciliar, en el futuro distribuir tambien en abirto algunos de los proyectos via github, ¡pero eso será en el próximo!
## Referencias bibliográficas que apoyan el contenido

- [PixiJS. (2025). Guías oficiales de PixiJS 🌐🟡③](https://pixijs.com/guides/)
	- La página oficial de PixiJS ofrece guías actualizadas para la versión 8.x, vigentes a 2025.
    
## Referencias bibliográficas que podrían refutar el contenido

- **Ninguna fuente verificable disponible**.  
    

![[Plantilla - 1MT#One More Thing]]