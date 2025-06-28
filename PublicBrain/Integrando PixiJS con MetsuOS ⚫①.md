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
modified: 2025-06-27T11:18:53.596Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 7
nav_primary: 
nav_secondary: 
tags:
---
# Integrando PixiJS con MetsuOS ⚫①

> WIP

Incluyo este capítulo intermedio en el flujo previsto originalmente, debido al uso de node y vite en el desarrollo, lo que podría afectar a la inclusión de nuestros proyectos en un entorno vanilla puro html + js, como es MetsuOS en producción.

Aunque trataremos el tema en el capítulo sobre distribución mas adelante, exploraremos como construye PixiJS el proyecto para producciçon y como podemos hacer nuestro propio "build-mos" en que compilemos de forma que se pueda correr sin necesidad node en destino.

Pretendo con ello, además, poder incluir desde ya elementos creados con esta tecnología como parte de la web y facilitar su uso también en vuestros proyectos de aquellos elementos de código o proyectos que acaben compartirdos de forma abierta en mi Github.

## El proceso de compilación para producción base

Veamos lo que hace PixiJS por defecto al compilar para producción nuestro proyecto.  Sirva decir que, por ahora, nos limitaremos a proyectos cuyo único requisito sea el propio PixiJS, en caso necesario ya completaremos esta información más adelante.

**<div class='pixi-app' id='mos-integration'><div class='pixi-container'  id='pixi-container'></div></div><script type='text/javascript' id='PixiText' async src='https://metsuke.com/assets/apps/PixiJS/002-MosIntegration/app-mos-integrate.iife.js'></script>**

![[Plantilla - 1MT#One More Thing]]