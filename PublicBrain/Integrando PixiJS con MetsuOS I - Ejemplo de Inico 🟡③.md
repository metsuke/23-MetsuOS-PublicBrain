---
iaStatus: 8
iaStatus_Model: Raúl Carrillo Garrido aka metsuke
iaStatus_Generado: "H"
iaStatus_Supervisado: "-"
iaStatus_Validado: "-"
a11y: 
checked: 0
lang: ES
translations: 
created: 2025-06-21T18:01:10.578Z
modified: 2025-07-04T21:38:24.980Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 15
nav_primary: 
nav_secondary: 
tags:
---
# Integrando PixiJS con MetsuOS I - Ejemplo de Inico 🟡③

![Integrando Pixi con MetsuOS](PublicBrain/_resources/19759e73f28dce00baeff950578f3cf6_MD5.jpg)

 * [[Curso de PixiJS ⚫①]]
* [[Creación de un lienzo (canvas) en PixiJS 🟡③|<< Anterior]] | Siguiente >>

> Esta serie de artículos del curso sobre integración, requieren conocimientos técnicos algo más avanzados que crear el juego, sin embargo tengan en cuenta que son ABSOLUTAMENTE OPCIONALES y no son obligatorios para poder crear juegos (aunque yo si los necesito para poder usarlo en la web)

Incluyo este capítulo intermedio en el flujo previsto originalmente, debido al uso de node y vite en el desarrollo, lo que podría afectar a la inclusión de nuestros proyectos en un entorno vanilla puro html + js, como es MetsuOS en producción.

Aunque trataremos el tema en el capítulo sobre distribución mas adelante, exploraremos como construye PixiJS el proyecto para producciçon y como podemos hacer nuestro propio "build-mos" en que compilemos de forma que se pueda correr sin necesidad node en destino.

Pretendo con ello, además, poder incluir desde ya elementos creados con esta tecnología como parte de la web y facilitar su uso también en vuestros proyectos de aquellos elementos de código o proyectos que acaben compartirdos de forma abierta en mi Github.

## Formato de Salida para JS Vanilla

Bien, empecemos, por defecto, la instalación de PixiJS compila la aplicacion en una carpeta que incluye el html y el resto de elementos. Para integrarlo con MetsuOS (o tu web) puedes usarlo tal cual con un enlace que abra ese index, en ese caso el resto del artículo probablemente no te haga falta.

Por otro lado, en el caso de esta web, lo que necesitamos es poder insertar nuestra app en cualquier documento, tal y como podrás ver al final de este artículo.

Lo primero, por tanto, es decir al proceso de compilación (que se lanza con "npm run build") que de algun modo prepare el proyecto en forma de un solo fichero js que se pueda incluir en nuestra web directamente y que funcione.

El método que he encontrado es modificar la configuración de vite.config.ts del siguiente modo:

```typescript
import { defineConfig } from "vite";

export default defineConfig({
	base: "./", // Usa rutas relativas desde la carpeta del bundle
	server: {
		port: 8080,
		open: true,
	},
	build: {
		lib: {
			entry: "src/main.js", // Cambia esto al archivo de entrada de tu proyecto (por ejemplo, src/app.js)
			name: "MOSIntegrate", // Nombre global de tu app (se expondrá en window.MyPixiApp si es necesario)
			fileName: "app-mos-integrate", // Nombre del archivo de salida (sin extensión)
			formats: ["iife"], // Formato IIFE para vanilla JS
		},
		outDir: "dist", // Carpeta de salida para el bundle
		minify: "esbuild", // Minifica el código para reducir el tamaño
		sourcemap: false, // Desactiva los sourcemaps (opcional, puedes habilitarlo con true si los necesitas)
	},
});
```

Esto indica al compilador que de como salida un formato IIFE (Esencialmente una formula para encapsular pixi y la app en una función, como si fuera una App Portable dentro de la web) para poder ejecutarlo como JS Nativo de una forma controlada.

Cada cual tendra que poner su nombre de aplicacion y de fichero de salida, que esencialmente sera el nombre de js que luego tendremos que insertar en nuestra web.

## Compilando

Compilar es tan sencillo como ejecutar "npm run build", esto arrancará todo el proceso, sin embargo a base de trabajar una y otra vez con el proyecto, he acabado haciendome dos scripts bash, uno para ejecutar en modo desarrollo (local) y otro para compilar y copiar el restulado a la carpeta (en este caso la mia) donde quiero que copie el restulado tras compilarlo y que resulta ser de donde luego se procesa y se sube a la web (aunque esa es otra historia).

El script para ejecutar en desarrollo (mos_rundev.sh):

```bash
#!/bin/bash

# Ejecutar el comando de desarrollo
echo "Ejecutando npm run dev ..."
npm run dev
```

Y el script para compilar y copiar (mos_compile):

```bash
#!/bin/bash

# Definir la carpeta de destino
DESTINATION_FOLDER="<mi ruta hasta APPS en la web>/PixiJS/002-MosIntegration"

# Prettier
echo "Ejecutando prettier..."
npx prettier --write src/main.ts

# Ejecutar el comando de compilación
echo "Ejecutando npm run build..."
npm run build

# Verificar si la compilación fue exitosa
if [ $? -eq 0 ]; then
  echo "Compilación exitosa."

  # Limpiar la carpeta de destino (crearla si no existe)
  echo "Limpiando la carpeta de destino: $DESTINATION_FOLDER"
  rm -rf "$DESTINATION_FOLDER"/* || { echo "No se pudo limpiar la carpeta de destino"; exit 1; }
  mkdir -p "$DESTINATION_FOLDER"

  # Copiar el contenido de la carpeta dist al destino
  echo "Copiando dist a $DESTINATION_FOLDER"
  cp -r dist/* "$DESTINATION_FOLDER" || { echo "No se pudo copiar dist al destino"; exit 1; }

  echo "Compilación y despliegue completados con éxito."
else
  echo "La compilación falló."
  exit 1
fi
```

Dado que encontre mucha perdida de tiempo con algunos elementos de formateo estandarizado del codigo que incluye PixiJS, añadí la ejecucion de prettier al proceso (que corrige muchos de las discrepancias de formato), en el script, ahorrando tiempo. Para que funcione tendreis que instalarlo si no lo teneis ya con:

```bash
npm install --save-dev prettier
```

y comprobar que quedó bien instalado con: (install y comproibacion desde terminal situados en la carpeta raiz del proyecto)

```bash
npx prettier --write src/main.ts
```

> Por favor, tened en cuenta que estoy aprendiendo sobre PixiJS a la vez que lo cuento, si tienes preguntas, o en tu sistema no te funciona y no logras dar con la tecla, contáctame en X/Twitter (@metsuke) e intentamos ver como arreglarlo juntos.

## Insertando el canvas

Este es el codigo que uso para insertar la app en su lugar (he puesto una X añadida a los nombres para impedir que el codigo de Pixi inyecte el canvas en medio del texto):

```html
<div class='pixi-appX' id='mos-integration'><div class='pixi-containerX' id='pixi-containerX'></div></div><script type='text/javascript' id='PixiText' async src='ruta de tus apps/PixiJS/002-MosIntegration/app-mos-integrate.iife.js'></script>;
```

El canvas lo insertará dentro de pixi-container  el codigo de la app (mas adelante entramos en eso) y aparecerá justo en la posición donde estén los divs. En mi caso he optado por poner html y ejecución del js en un mismo lugar para hacer "sencilla" su gestión. Si mejoro o ajusto el método mas adelante, ya os contare.

La primera vez posiblemente el aspecto visual del canvas y su ajuste a la pantalla sea un churro. Veamos como mejorar esto.
## Poniendo bonito el canvas:

En mi caso, he optado por trabajar el aspecto base de la "ventana" insertada con css. Soy consciente de que hay mucho que puede mejorarse a efectos de redimensionado de ventana e incluso de ejecución a fullscreen, lo abordaré en capítulos posteriores, pero por ahora vamos a la version minima viable con una dignidad aceptable.

Este es el código css que he incluido en la css *de la web*:

```css
.pixi-app {
	position: relative;
	width: 100%w;
	max-width: 100%;
	aspect-ratio: 4 / 3;
}

.pixi-container {
	position: relative;
	border: 1px solid #4a2f1f;
	border-top: 20px solid #4a2f1f;
}

.pixi-container canvas {
	width: 100%;
	height: 100%;
	display: block;
}
```

Los colores, bordes y demás son elección en base a mi diseño, puede que tu quieras variarlo, con un conocimiento suficiente de CSS podrás adaptarlo a tus necesidades.

> No voy a enseñar aqui css tampoco, pero si en algun momento tienes dificultades con esto de nuevo contactame en X/Twitter (@metsuke) y tratamos de ver que pasa juntos.
## Solucionar el problema de la rutas de los assets en produccion

Todo esto funciona casi bien, salvo por un pequeño detalle que se da en MetsuOS pero que no necesariamente se dará en tu caso concreto, en local la carpeta assets está en el raiz de la app y el sistema encontrará facilmente los recursos en assets.

No obstante en producción por defecto la ruta definida base: "./" va a apuntar a midominio/ lo cual, si tus apps están en una carpeta midominio/aplicaciones/misapps/miapp, hará que al intentar insertar recursos, como bunny.png en el ejemplo por defecto, sencillamente no funcione bien.

Para repararlo he modificado main.js (el codigo de la aplicación) para que, en caso de que detecte que estamos en producción, asegure que la ruta base que toma pixi sea la carpeta donde estña el js que incluimos (la raiz de la app) y no la raiz del dominio.

En main.ts

```typescript
import { Application, Assets, Sprite } from "pixi.js";

// Función para obtener la ruta base del script actual (usada solo en producción)
function getScriptBaseUrl() {
	const script =
	document.currentScript ||
	// Fallback para navegadores más antiguos
	(function () {
		const scripts = document.getElementsByTagName("script");
		return scripts[scripts.length - 1];
	})();
	
	// Type guard para asegurar que script es HTMLScriptElement
	if (!(script instanceof HTMLScriptElement)) {
		throw new Error("Current script is not an HTMLScriptElement");
	}
	
	const scriptUrl = new URL(script.src);
	
	// Extrae la ruta base (sin el nombre del archivo)
	return scriptUrl.pathname.substring(
		0,
		scriptUrl.pathname.lastIndexOf("/") + 1,
	);
}

(async () => {
	// Determinar la ruta base según el entorno
	const isDevelopment = import.meta.env.MODE === "development";
	const baseUrl = isDevelopment ? "/" : getScriptBaseUrl();

	// Create a new application
	const app = new Application();
	const appcontainer = document.querySelector(".pixi-app") as HTMLElement;
 
	// Initialize the application
	await app.init({ background: "#1099bb", resizeTo: appcontainer });

	// Append the application canvas to the document body
	document.getElementById("pixi-container")!.appendChild(app.canvas);
 
	// Load the bunny texture using the appropriate base URL
	const texture = await Assets.load(`${baseUrl}assets/bunny.png`);

	// Create a bunny Sprite
	const bunny = new Sprite(texture);

	// Center the sprite's anchor point
	bunny.anchor.set(0.5);

	// Move the sprite to the center of the screen
	bunny.position.set(app.screen.width / 2, app.screen.height / 2);

	// Add the bunny to the stage
	app.stage.addChild(bunny);

	// Listen for animate update
	app.ticker.add((time) => {
		// Just for fun, let's rotate mr rabbit a little.
		// * Delta is 1 if running at 100% performance *
		// * Creates frame-independent transformation *
		bunny.rotation += 0.1 * time.deltaTime;
	});
})();
```

Esencialmente la modificación es eso, reasignar la ruta base en produccion antes de empezar a añadir recursos.

## La app de prueba

Aquí podemos ver la integración en MetsuOS de la app de ejemplo de PixiJS, queda bastante por hacer, sobre todo en cuanto a la parte responsive del canvas y también dentro de nuestras apps y juegos, pero eso lo empezaremos a abordar en el próximo capítulo.

**<div class='pixi-app' id='mos-integration'><div class='pixi-container'  id='pixi-container'></div></div><script type='text/javascript' id='PixiText' async src='https://metsuke.com/assets/apps/PixiJS/002-MosIntegration/app-mos-integrate.iife.js'></script>**

## Referencias Bibliográficas

* Pruebas de campo en primera persona.

![[Plantilla - 1MT#One More Thing]]