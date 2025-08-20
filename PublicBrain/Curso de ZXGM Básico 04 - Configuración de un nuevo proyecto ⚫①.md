---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-08-18T21:19:19.590Z
modified: 2025-08-19T23:24:37.970Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 8
nav_primary: []
nav_secondary: []
tags: []
---
# Curso de ZXGM Básico 04 - Configuración de un nuevo proyecto ⚫①

![Y los muertos aqui lo pasamos muy bien entre flores de colores](/PublicBrain/_resources/d22667726699dac0f871e793462c3d38_MD5.jpg)

* [[Curso de ZX Game Maker ⚫①]]
* [[Curso de ZXGM Básico 03 - Explorando la estructura general del motor 🟡③|<< Anterior]] | Siguiente >>

> OJO WIP

En este cuarto capítulo del curso básico de ZX Game Maker (ZXGM), aprenderás a configurar un nuevo proyecto desde "cero" (el motor está ideado para que partas de una plantilla mínima), siguiendo un enfoque estructurado y gradual, como un escultor tallando una obra a partir de una piedra en bruto. 

Usaremos como ejemplo el desarrollo de [[MOS Games - Cursed Zapatilla - La Excéntrica Cruzada de Sir Patillas (2025)|Cursed Zapatilla: La Excéntrica Cruzada de Sir Patillas]], un juego de plataformas inspirado en _Ghosts 'n Goblins_, _Ghouls 'n Ghosts_ y _Cursed Castilla_. 

Este juego forma parte de un pack de juegos que usare para todos los cursos de Makers y creacion de juegos, de forma que - en la medida de lo posible - habra, al menos, tantas versiones del juego como motores y modos graficos soporten aquellos para los que hagamos cursos. Pretendo con ello fomentar la idea de explorar Y de la necesidad de aumentar el nivel de calidad de las producciones, una vez creada tu opera prima.

Este capítulo se centra en crear la estructura inicial del proyecto y configurar parámetros básicos en Tiled, sin modificar aún los recursos gráficos, pantallas, sonidos o músicas. En cada capítulo posterior, iremos cincelando el proyecto hasta transformarlo en nuestro juego final.

El proceso consiste en tomar una plantilla de ejemplo que viene por defecto en assets (o en su caso una de la carpeta examples), renombrar la carpeta de ZX Game Maker para reflejar nuestro juego (usando guiones en lugar de espacios para evitar problemas con los nombres) y ajustar parámetros específicos en Tiled para alinearlos con las necesidades de _Cursed Zapatilla_. 

Este tutorial está diseñado para principiantes, asumiendo que tienes el entorno configurado según [[Curso de ZXGM Básico 02 - Descarga e instalación del software 🟡③|el Capítulo Básico 02]] y conoces [[Curso de ZXGM Básico 03 - Explorando la estructura general del motor 🟡③|la estructura del motor del Capítulo Básico 03]].

Al final, tendrás un proyecto base listo para iterar en los siguientes capítulos.

## Requisitos previos

Antes de comenzar, verifica lo siguiente (basado en el _Capítulo Básico 02_):

- ZXGM instalado con dependencias (Python, Tiled versión 1.11.2 o superior, ZX Paintbrush).
- Scripts de instalación ejecutados (install.windows.bat o install.sh).
- Carpeta principal de ZXGM organizada con subcarpetas assets, src y examples. 
- Conocimiento de la estructura: assets para mapas y gráficos, src para dependencias como Boriel Basic y GuSprites (no modificar), examples para plantillas adicionales.
- Emulador de ZX Spectrum (como Zesarux o Fuse) de tu elección para pruebas.   
- Acceso a la documentación oficial de ZXGM cuyos enlaces puedes ver en las referencias bibliogrçaficas al final del capítulo.
    
Si algo no está listo, revisa la sección de solución de problemas del _Capítulo Básico 02_.

## Paso 1: Renombrar la carpeta de zxgm

Este paso, aunque no es obligatorio, es altamente recomendable, debemos tomar la carpeta donde hemos instalado el motor (habitualmente zx-game-maker) y renombrarla con el nombre de nuestro juego, en nuestro caso he usado "cursed-zapatilla-zxgm".

> Es una buena práctica no poner espacios en el nombre, para evitar problemas derivados de espacios dentro de las rutas, en su lugar recomiendo el uso de guiones.

## Paso 2: Seleccionar la plantilla base o usar la de assets

Por defecto, el motor contiene un juego demo en assets (que es donde estarán los datos de nuestro juego), por defecto usaremos este.

No obstante en examples hay mas plantillas que puedes usar cambiando los ficheros:

* arcade .- Ejemplo de juego en modo arcade (por pantallas a lo Snow Bros)
* overhead-view .- Ejemplo con vista cenital, al estilo Zelda
* platforms ,. Es el juego que por defecto viene en assets de estilo plataformas.

Si quieres cambiar de plantilla, copia el contenido de la carpeta de la que quieras, y copialo dentro de assets, sobreescribiendo ficheros.

Una vez elegida la plantilla, vamos a lanzar el GUI.

## Paso 2: Lanzar ZX Game Maker

1. Abre una terminal o línea de comandos y navega a la carpeta principal de ZXGM (e.g., cd /ruta/a/zx-game-maker).
    
2. Ejecuta el launcher con:
    
```bash
python zxsgm.py
```
    
    Esto abre la interfaz de ZXGM (pantalla oscura o clara, según configuración). Si aparece un error, verifica que Python esté en el PATH y usa python3 en Linux/macOS si es necesario.
    
3. Prueba a ejecutar Build / Game en el menú para asegurarte de que partimos de una plantilla funcional.
    
## Paso 3: Configuración inicial en Tiled

En este capítulo, nos enfocamos en ajustar parámetros en Tiled (lugar donde se realizan casi todas las configuraciones de nuestro juego) para alinear el proyecto con _Cursed Zapatilla_. 

Usaremos el archivo maps.tiled-project de la plantilla copiada, sin modificar gráficos aún.

1. Abre el Mapa de la plantilla en el menu Map / Open Map

2. En tiled, despliega "Maps" y haz doble click sobre el mapa para abrir el interfaz

3. Te aparecerá algo similar a esto (calma, parece mucho, pero iremos paso a paso, capitulo a capitulo):

![Tiled con el mapa de la plantilla cargado](PublicBrain/_resources/c5741151ecbfb386b36b70c866f78322_MD5.jpeg)

## Paso 4: Configuración de los parámetros

Vamos a comenzar con la chicha, en este punto, vamos a confgigurar los parámetros que permiten generar una jugabilidad específica para nuestra obra. Aunque exploraremos todos los parámetros, centraremos el foco en crear nuestro juego plataformero, ya habrá tiempo, una vez completado el ciclo base, de crear monográficos para cada uno de los juegos que queremos crear.

Organizaremos los parámetros de forma progresiva y por bloques de forma que el proceso de pensamiento creativo sea el que guie nuestros pasos en una dirección precisa. 

Los parmetros se pueden ver en Mapa > Propiedades Personalizadas o Map > Map Properties dependiendo del idioma actual en Tiled:

> WIP Organizando y definiendo estructura información de los parámetros
### Parámetros Generales

Lo primero, logicamente, es identificar nuestro juego, y el target al que va dirigido!

#### **gameName**
Establece el nombre del juego

* **Sintaxis:** `gameName` ```<nombre_del_juego>```
* **Notas:** Aparecerá en el título loading cuando carga y el tap se generará con este nombre. 10 carácteres como máximo sin carácteres especiales (acentos, ñ…)
* **Para Cursed Zapatilla**: Usaremos "CursedZapa" como identificador.

#### **128Kenabled**
Establece si el modo 128K está activo.

* **Sintaxis:** `128Kenabled` ( activado / desactivado )
* **Notas:** En modo 128k, se permite acceso a bancos de memoria adicionales para características avanzadas.
* **Para Cursed Zapatilla**: Marcaremos la opción para que genere el .tap para 128K, en 48K funcionará pero salvo configuraciones hardware especiales, funcionará sin sonido o música AY.


### Parámetros Estructurales

En este punto tomaremos decisiones en torno al mundo en el que nuestro personaje desarrollará su "vida":

#### **gameView**

Define el tipo de juego a desarrollar según la perspectiva.

- **Sintaxis:** `gameView` (side | overhead)
- **Notas:** Establece la vista del juego: "side" para un juego de plataformas lateral (ideal para _Cursed Zapatilla_, inspirado en plataformas como _Ghosts 'n Goblins_), y "overhead" para un juego de vista cenital, como un laberinto o estrategia. La elección afecta el diseño del mapa en Tiled y la lógica de movimiento en ZXGM.
- **Para Cursed Zapatilla:** Usaremos gameView = side para un desplazamiento lateral en nuestro florido cementerio.

#### **arcadeMode**

Establece si el juego se comportará en modo arcade.

- **Sintaxis:** `arcadeMode` (activado | desactivado)
- **Notas:** Si esta propiedad está activada, el juego adopta un estilo arcade clásico, en el que hay que pasarse cada pantalla y vamos avanzando por niveles (como en Snow Bross por ejemplo). Puedes [ver este comportamiento arcade aquí](https://gm.retrojuegos.org/mydoc_tiled_arcade_mode.html). 
- **Para Cursed Zapatilla:** Configuraremos arcadeMode = desactivado, ya que queremos un mapeado continuo, a falta de un sistema de fases multipantalla, tendremos uno con el mapa completo.
#### **password**

Establece un password que se pedirá al iniciar el juego.

- **Sintaxis:** `password <contraseña_de_8_caracteres>`
- **Notas:** Útil para juegos con múltiples cargas, en caso de configurarla se te pedirá la contraseña para poder jugar. La contraseña debe tener exactamente 8 caracteres alfanuméricos y no debe incluir caracteres no ingleses (e.g., ñ, acentos). 
- **Para Cursed Zapatilla:** Lo dejaremos vacio ya que no requerimos esta funcionalidad.

### Parámetros de Juego

Centremos nuestra atencion ahora en algunos aspectos generales del juego:

#### **goalItems**

Número de items necesarios para finalizar el juego.

- **Sintaxis:** `goalItems <número_de_items>`
- **Notas:** Define la cantidad de objetos (e.g., flores brillantes o llaves) que el jugador debe recolectar para completar _Cursed Zapatilla_. Este valor influye en la lógica del juego y debe ser un número entero positivo. 
- **Para Cursed Zapatilla:** Configuraremos goalItems = 66 para un nivel inicial con cinco items en el cementerio, si mas adelante lo necesitaremos, ajustaremos este número.

#### **hiScore**

Habilita la puntuación in-game y el guardado de la misma para que aparezca en la pantalla de menú.

- **Sintaxis:** `hiScore` (activado | desactivado)
- **Notas:** Activa un sistema de puntuación que se muestra durante el juego y se guarda para exhibirse en la pantalla de menú, emulando el estilo arcade de _Ghosts 'n Goblins_. Requiere espacio adicional en memoria (recomendado modo 128k para estabilidad). Si está desactivado, no se registrará la puntuación.
- **Para Cursed Zapatilla:** Configuraremos hiScore = activado para incentivar la rejugabilidad asociada al reto extra.

#### **idleTime**

Setea el tiempo a esperar a que el personaje haga la animación idle. Si está a 0 no se activará.

- **Sintaxis:** `idleTime <segundos>`
- **Notas:** Establece el intervalo (en segundos) tras el cual Sir Patillas realiza una animación idle (e.g., ajustarse el casco) si no hay input. Un valor de 0 desactiva esta función para optimizar recursos en el ZX Spectrum. Valores típicos: 2-5 segundos.
- **Para Cursed Zapatilla:** Configuraremos idleTime = 10 para una animación idle tras 10 segundos de inactividad.

#### **livesMode**

Habilitado tu personaje morirá cada vez que reciba daño perdiendo 1 vida y volviendo al punto donde entró de la pantalla actual. A su vez sólo ganará 1 vida con los items **life**.

* **Sintaxis:** `livesMode` (disabled | instant respawn | show graveyard)
* **Notas:** Activa un sistema de vidas clásico donde Sir Patillas pierde una vida por daño y reaparece en el inicio de la pantalla, con ganancia limitada a 1 vida por item **life**. [Puedes ver este comportamiento del modo  vidas aquí](https://gm.retrojuegos.org/mydoc_tiled_lives_mode.html). 
* **Para Cursed Zapatilla:** Ideal para un estilo arcade en *Cursed Zapatilla*. Configuraremos `livesMode = show graveyard` para replicar la dificultad de *Ghosts 'n Goblins*, y mostrar la tumbita que no deja de tener su guasa en el contexto este juego.
#### **initialLife**

Cantidad de vida inicial del personaje.

- **Sintaxis:** `initialLife <cantidad_de_vida>`
- **Notas:** Define la vida inicial de Sir Patillas en _Cursed Zapatilla_, representada como un número entero (e.g., 3 vidas o 100 puntos de energía). 
- **Para Cursed Zapatilla:** Configuraremos initialLife = 5 para tres vidas iniciales, al estilo de los clásicos arcade.

#### **lifeAmount**

Cantidad de vida que incrementa al personaje los items **life**.

* **Sintaxis:** `lifeAmount` ```<cantidad_de_vida>```
* **Notas:** Define la cantidad de vida que se suma a Sir Patillas al recoger items **life** en *Cursed Zapatilla*. Debe ser un número entero positivo. 
* **Para Cursed Zapatilla:** Configuraremos `lifeAmount = 1` para que cada item **life** restaure 2 puntos de vida.

#### **shooting**

Con esto habilitamos o deshabilitamos el disparo del personaje.

* **Sintaxis:** `shooting` (activado | desactivado)
* **Notas:** Habilita o deshabilita la capacidad de Sir Patillas para disparar proyectiles (e.g., zapatillazos a distancia). Desactivado optimiza recursos en el ZX Spectrum; activado requiere configuración de `ammo` y `bulletDistance`.
* **Para Cursed Zapatilla:** Configuraremos `shooting = activado` para añadir ataques a distancia.
#### **ammo**

Cantidad de munición con la que empezará el personaje principal. Si seteas -1 el personaje tendrá munición infinita.

* **Sintaxis:** `ammo` ```<cantidad_de_munición>```
* **Notas:** Establece la munición inicial de Sir Patillas para ataques a distancia (e.g., zapatillazos proyectados). Un valor de -1 otorga munición infinita, útil para pruebas; valores positivos (e.g., 10-50) limitan los disparos en modo 48k.
* **Para Cursed Zapatilla:** Configuraremos `ammo = -1` ya que uno de los atractivos de este estilo de juegos es moverse y disparar sin parar un instante.

#### **ammoIncrement**

Cantidad de munición que se recarga cada vez que el protagonista recoja un item de recarga de munición.

* **Sintaxis:** `ammoIncrement` ```<cantidad_de_munición>```
* **Notas:** Define cuánta munición se añade al recoger un item de recarga en *Cursed Zapatilla*. Debe ser un número entero positivo.
* **Para Cursed Zapatilla:** No configuraremos `ammoIncrement porque el estilo de juego pide dis... zapatillas infinitas.

#### **bulletDistance**

Distancia que queramos que recorra la bala. El valor 0 se traduce como distancia infinita, la bala no parará hasta que choque con algún obstáculo. Si seteamos una distancia corta como de 2, da el efecto de que el personaje ataca con el arma a corta distancia como una espada.

* **Sintaxis:** `bulletDistance` ```<distancia>```
* **Notas:** Controla la distancia de los proyectiles disparados por Sir Patillas. Un valor de 0 permite trayectorias infinitas (hasta colisión); valores bajos (e.g., 2) simulan ataques cuerpo a cuerpo, como un zapatillazo de corto alcance en *Cursed Zapatilla*.
* **Para Cursed Zapatilla:** Configuraremos `bulletDistance = 0` para un efecto de ataque Cocodrilo Dundee profesional con zapatillas voladoras.

### Parámetros de Interacción

Una vez llegados a este punto, configuraresmos las interacciones con enemigos y otros elementos del escenario:


#### **  
damageAmount**

Cantidad de daño que los enemigos infligen al personaje.

- **Sintaxis:** damageAmount <cantidad_de_daño>
- **Notas:** Define la cantidad de daño que los enemigos causan al personaje en _Cursed Zapatilla_. Debe ser un número entero positivo.
- **Para Cursed Zapatilla:** Configuraremos damageAmount a 1 para reflejar un desafío progresivo y mantener la esencia retro del juego.

#### **enemiesRespawn**

Indica si los enemigos (no invencibles) reaparecen después de ser eliminados al volver a entrar en la habitación.

- **Sintaxis:** enemiesRespawn <verdadero/falso>
- **Notas:** Configura si los enemigos vuelven a generarse. Útil para habitaciones con oleadas continuas.
- **Para Cursed Zapatilla:** Estableceremos enemiesRespawn a false para evitar repeticiones innecesarias y enfocarnos en un avance lineal.

#### **jetPackFuel**

Cantidad de combustible disponible para el jetPack; si es distinto de 0, el personaje usará el jetPack en lugar de saltar.

- **Sintaxis:** jetPackFuel <cantidad_de_combustible>
- **Notas:** Define la cantidad de combustible para el jetPack. Debe ser un número entero no negativo; 0 desactiva el jetPack.
- **Para Cursed Zapatilla:** Configuraremos jetPackFuel a 0, ya que Sir Patillas dependerá de saltos tradicionales y zapatillazos.

#### **jumpType**

Tipo de salto del personaje, con opciones de movimiento constante o acelerado.

- **Sintaxis:** jumpType ```<constant/accelerated>`
- **Notas:** constant usa una velocidad constante hacia arriba y abajo (estilo original del motor); accelerated aplica deceleración al subir y aceleración al bajar.
- **Para Cursed Zapatilla:** Estableceremos jumpType a constant para mantener un control clásico al estilo _Ghosts 'n Goblins_.

#### **keysEnabled**

Habilita o deshabilita el uso de llaves y puertas que requieren llaves.

- **Sintaxis:** keysEnabled <verdadero/falso>
- **Notas:** Si está deshabilitado, las llaves y puertas asociadas no funcionarán en el juego.
- **Para Cursed Zapatilla:** Configuraremos keysEnabled a false, ya que el juego prioriza acción directa sin mecánicas de puertas.

#### **killJumpingOnTop**

Habilita la capacidad de matar enemigos saltando sobre ellos (solo en juegos de plataformas).

- **Sintaxis:** killJumpingOnTop <verdadero/falso>
- **Notas:** Activa la mecánica de eliminar enemigos al saltar encima, típica de plataformas.
- **Para Cursed Zapatilla:** Estableceremos killJumpingOnTop a true para añadir una mecánica divertida de zapatillazos desde arriba.

#### **messagesEnabled**

Activa la visualización de mensajes de ayuda al entrar en contacto con items, puertas u otros elementos.

- **Sintaxis:** messagesEnabled <verdadero/falso>
- **Notas:** Muestra instrucciones o pistas cuando el personaje interactúa con objetos específicos.
- **Para Cursed Zapatilla:** Configuraremos messagesEnabled a true para guiar a los jugadores en su primera experiencia.

#### **shouldKillEnemies**

Requiere eliminar a todos los enemigos en una habitación antes de poder salir de ella.

- **Sintaxis:** shouldKillEnemies <verdadero/falso>
- **Notas:** Si está activado, la salida queda bloqueada hasta que se eliminen todos los enemigos.
- **Para Cursed Zapatilla:** Estableceremos shouldKillEnemies a true para añadir un desafío al estilo arcade.

#### **useBreakableTile**

Habilita la posibilidad de usar tiles rompibles, con opciones de comportamiento.

- **Sintaxis:** useBreakableTile ```<disabled/all/individual>`
- **Notas:**
    - disabled: No hay tiles rompibles.
    - all: Todos los tiles rompibles de la habitación se destruyen al romper uno.
    - individual: Cada tile se rompe de forma independiente.
    - El tile rompible debe estar definido en la posición 63 del tileset.
- **Para Cursed Zapatilla:** Configuraremos useBreakableTile a individual para permitir romper lápidas en el cementerio de forma estratégica.




- **damageAmount**. Cuánto daño le hacen al personaje los enemigos.
- **enemiesRespawn**. Si los enemigos (no invencibles) vuelven a aparecer des pués de matarlos al volver a entrar en la habitación.
- **jetPackFuel**. La cantidad de fuel para el jetPack, se es ditinto de 0 el personaje no saltará y se impulsará con el jetPack.
- **jumpType**. **constant** Salto con una velocidad hacia arriba y hacia abajo constante, el original del motor. **accelerated**Salto con deceleración hacia arriba y acelereción hacia abajo.
- **keysEnabled**. Si no está habilitado no se podrán usar llaves ni puertas de las que se abren con llaves.
- **killJumpingOnTop**. Habilita el poder de matar a los enemigos saltando encima. (Solo juego plataformas)

- - **messagesEnabled**. Si se activa esta opción se mostrará un mensaje de ayuda cuando se entre en contacto con algún item. puerta…

- **shouldKillEnemies**. Con esta propiedad activa, si una habitación tiene enemigos, no podremos salir de ella hasta que los matemos a todos.
- **useBreakableTile**. Posibilidad de usar tiles que se rompen. Si está habilitado el tile que se romperá será el que esté definido en la posición 63 del tileset. Puedes elegir entre 3 opciones:
    - disabled. No hay tiles rompibles.
    - all. Si hay tiles rompibles y al romper uno se rompen todos los de la habitación.
    - individual. Si hay tiles rompibles y se rompen 1 a 1.
    - 
### Parámetros del HUD

- **itemsCountdown**. El marcador de items mostrará el número total de items que tiene que conseguir el jugador al principio del juego e irá descendiendo para que veas los items que te quedan por recoger.
- **itemsEnabled**. Si no está habilitado no se mostrará el marcador de items.
### Parámetros Gráficos

- **animatePeriodEnemy**. Número más alto, animación de los enemigos más lenta.
- **animatePeriodMain**. Número más alto, animación del personaje principal más lenta.
- **animatePeriodTile**. Número más alto, animación de los tiles más lenta.
- **border**. Color del borde in game. Muy útil cuando se cambia el color de fondo del juego y del hud.
-  **ink**. Color de la tinta in game. Muy útil cuando se cambia el color de fondo del juego y del hud.
- - **mainCharacterExtraFrame**. Si está habilitado, la animación del personaje usara el frame extra.
- - **paper**. Color del papel in game. Muy útil cuando se cambia el color de fondo del juego y del hud.
- - **backgroundAttribute**. Color de fondo del juego en decimal en forma de atributos de spectrum. Por ejemplo para color de fondo negro con sprites en blanco seria 7 (00000111). Para color de fondo azul con sprites en blanco seria 15 (00001111). Si no se define este atributo se pintara fondo negro sprites blancos. Podéis usar la calculadora siguiente para saber que valor tenéis que poner.

```basic
128*FLASH + 64*BRIGHT + 8*PAPER + INK
```

https://gm.retrojuegos.org/mydoc_tiled_general_configuration.html
### Parámetros Sonoros

- **VTPLAYER_INIT**. Posición de memoria inicial para la música vortex (Se verá en el capítulo de música en el juego)
- **VTPLAYER_MUTE**. Posición de memoria de mute para la música vortex (Se verá en el capítulo de música en el juego)
- **VTPLAYER_NEXTNOTE**. Posición de memoria para reproducir la próxima nota para la música vortex (Se verá en el capítulo de música en el juego)
- **musicEnabled**. Para habilitar o deshabilitar la música AY. Si se habilita la música el juego resultante sólo funcionará en 128K, para hacer una versión 48K tendrás que desmarcar guardar y volver a compilar.
- **newBeeperPlayer**. Para utilizar en nuevo reproductor de beeper mejorado para que el juego se pare mucho menos mientras suena debes activar esta opción. IMPORTANTE: Si quieres aprovechar las bondades de este nuevo player debes hacer los sonidos como se indica en [la sección de FX del manual](https://gm.retrojuegos.org/mydoc_sound_fx.html).

### Parámetros de Rendimiento

- **maxAnimatedTilesPerScreen**. Máximo de tiles animados por pantalla (10 máximo). Si utilizas menos pon un valor más bajo para ahorrar espacio.
- **maxEnemiesPerScreen**. Se puede configurar la cantidad de enemigos que aparecen en pantalla (hasta 5). Evitar poner más de los que se usan para optimizar espacio.

### Parámetros Extra

Esos pequeños detalles que están, son necesarios pero no encajan perfectamente en el resto de categorías.

- **redefineKeysEnabled**. Habilita la opción de redefinir teclas.
- **waitPressKeyAfterLoad**. Si habilitas esta opción, tras la carga el juego esperará que pulses una tecla para mostrar el menú.



## Paso 4: Verificación del proyecto

1. **Prueba inicial en ZXGM**:
    
    - Asegurate de guardar los cambios en Tiled, para que el compilador tenga oportunidad de tenerlos en cuenta.
        
    - Ve a _Game/Build_ en el GUI y ejecuta la compilación.
        
    - Si no hay errores, se generará cursed-zapatilla.tap en cursed-zapatilla/dist.
        
2. **Prueba en emulador**:
    
    - Abre el emulador de ZX Spectrum de tu elección.        
    - Carga CursedZapa.tap.        
    - Verifica que el juego carga (sin Sir Patillas ni enemigos personalizados aún).

## Solución de problemas comunes

- **Interfaz de ZXGM no carga**: Verifica Python (python3 --version) y ejecuta el script de instalación nuevamente.    
- **Errores en Tiled**: Asegúrate de usar versión 1.11.2+ y que maps.tiled-project sea compatible. Consulta la documentación de ZXGM. 
- **Build falla**: Revisa logs en la terminal o en output. Verifica que src no esté modificado y que Boriel Basic/GuSprites estén presentes.    

Consulta el grupo de Telegram de ZXGM o la documentación en el repositorio para soporte adicional.

## Conclusión

Has configurado la base de _Cursed Zapatilla: La Excéntrica Cruzada de Sir Patillas_ con una estructura de proyecto y una plantilla inicial en Tiled.

Como escultores, hemos dado el primer golpe al cincel, preparando la piedra para tallarla en capítulos futuros, donde añadiremos sprites personalizados (Sir Patillas, zombis), mecánicas de zapatillazos, y más. ¡Sigue adelante y comienza a dar forma a tu juego retro!

## Referencias Bibliográficas

* Mis pruebas de campo ⚫①
* [Documentación oficial del proyecto 🌐🟡③](https://gm.retrojuegos.org/index.html)
* [Repositorio de Github de ZX Game Maker 🌐🟡③](https://github.com/rtorralba/zx-game-maker) .
* [Página de Itch.io del proyecto 🌐🟡③](https://juntelart.itch.io/zx-game-maker)

![[Plantilla - 1MT#One More Thing]]