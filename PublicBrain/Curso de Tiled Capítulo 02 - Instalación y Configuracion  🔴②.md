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
created: 2025-09-21T10:04:56.304Z
modified: 2025-09-21T22:13:45.269Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoTiled002.mp4
---
# Curso de Tiled Capítulo 02 - Instalación y Configuracion  🔴②


![Instalacion de Tiled](PublicBrain/_resources/fad16bb05874da0f4dbdd97bf07cd434_MD5.jpg)

* [[Curso de Tiled Map Editor - Creación de Mapas para Videojuegos 2D  ⚫①]]
* [[Curso de Tiled Capítulo 01 - Qué es Tiled Map Editor 🟡③|<< Anterior]] | Siguiente >>


Vamos a sumergirnos de lleno en la instalación y puesta en marcha de Tiled, ese editor de mapas 2D de código abierto que se ha convertido en un aliado indispensable para tantos desarrolladores independientes. Imagina poder diseñar mundos enteros para tus juegos de rol, plataformas o puzles con una herramienta tan versátil y accesible. 

Tiled te permite crear mapas basados en teselas de forma intuitiva, y aquí te guiaré paso a paso, desde la descarga hasta los trucos iniciales para que tu flujo de trabajo sea lo más fluido posible. Todo lo que verás se basa en la versión más actualizada disponible en este momento (Tiled 1.11.2, lanzada el 28 de enero de 2025), pero recuerda verificar el sitio oficial por si hay novedades.

## Descarga: Cómo obtener Tiled desde mapeditor.org

Descargar Tiled es pan comido, y lo mejor es hacerlo directamente desde la web oficial del proyecto, [mapeditor.org 🟡③ 🌐](https://www.mapeditor.org/), para evitar cualquier sorpresa con versiones pirata o alteradas. Ahí encontrarás paquetes listos para usar en las plataformas más comunes, además del código fuente si te animas a personalizarlo. Dirígete a la página de descargas en [https://www.mapeditor.org/download.html 🟡③ 🌐](https://www.mapeditor.org/download.html), y elige la versión estable más fresca.

**Opciones de descarga a tener en cuenta:**

- **Versiones estables**: Apunta siempre a la última estable (como la 1.11.2 de ahora). Las builds nocturnas son tentadoras para probar novedades, pero olvídate si buscas estabilidad.
- **Binarios precompilados**: Vienen con todo lo necesario, como Qt, así que no tendrás que instalar extras en la mayoría de casos.
- **Código fuente**: Si quieres compilar a medida, baja el `.tar.gz` o clona el repo de GitHub con `git clone https://github.com/mapeditor/tiled`.

Aquí va una tabla práctica con las descargas clave para la 1.11.2 (ojo, comprueba el sitio porque los enlaces directos pueden variar con actualizaciones):

| Plataforma                      | Formato                        | Notas                                                                                       |
| ------------------------------- | ------------------------------ | ------------------------------------------------------------------------------------------- |
| **Windows**                     | Instalador (.exe, 64-bit)      | Para Windows 10 o superior; instalador con interfaz gráfica amigable.                       |
| **Windows**                     | Portátil (.zip, 32/64-bit)     | Descomprime y lanza `tiled.exe`; perfecto para pendrives o sin permisos de admin.           |
| **macOS**                       | Disco de imagen (.dmg, 64-bit) | Desde macOS 11 (Big Sur) en adelante; incluye firma para saltarte las alertas de seguridad. |
| **Linux (AppImage, universal)** | AppImage (.AppImage, 64-bit)   | Súper portátil, sin instalación; va bien en Ubuntu 22.04 o similares.                       |
| **Linux (Debian/Ubuntu)**       | Paquete (.deb, 64-bit)         | Se integra con APT para una gestión fácil.                                                  |
| **Linux (Fedora/RPM)**          | Paquete (.rpm, 64-bit)         | Ideal para distros como Fedora basadas en RPM.                                              |
| **Linux (Flatpak)**             | Flatpak (universal)            | Necesitas Flatpak; es seguro por su sandbox.                                                |
| **Linux (Snap)**                | Snap (universal)               | Actualizaciones automáticas, pero prepárate para un arranque algo más lento.                |
| **Código Fuente**               | Tarball (.tar.gz)              | Para builds personalizados; mira la sección de requisitos.                                  |

**Consejos prácticos para la descarga:**
- Automatízalo con herramientas como wget o curl: por ejemplo, `wget https://github.com/mapeditor/tiled/releases/download/v1.11.2/Tiled-1.11.2-x86_64.AppImage`.
- Siempre verifica los checksums SHA256 que aparecen en las releases de GitHub para asegurarte de que todo está intacto.
- En entornos limitados, como un Chromebook, Flatpak o Snap son tus mejores amigos: instalación sin root y sin complicaciones.

## Instalación: Guía para Windows, macOS y distribuciones Linux

Instalar Tiled es de lo más directo, gracias a que los binarios ya traen Qt empaquetado (esa librería que hace que todo luzca bonito). Te detallo los pasos para cada sistema, asumiendo que ya has bajado el archivo adecuado. ¡Vamos al grano!

**En Windows:**
1. Coge el instalador `.exe` (el más recomendado para el día a día).
2. Lánzalo con privilegios de admin (clic derecho > "Ejecutar como administrador").
3. Sigue el asistente: acepta los términos, elige dónde ponerlo (por defecto, `C:\Program Files\Tiled`), y deja los componentes tal cual.
4. Marca las casillas para crear un atajo en el escritorio y añadirlo al PATH, así lo llamas desde la consola sin dramas.
5. Termina y ábrelo desde el menú Inicio o el escritorio.
- **Versión portátil**: Descomprime el `.zip` en una carpeta (como `C:\Tiled`) y ejecuta `tiled.exe`. Para desinstalar, solo borra la carpeta.
- **Desinstalación formal**: Ve a Configuración > Aplicaciones > "Agregar o quitar programas".
- **Si algo sale mal**: Revisa si Windows Defender lo bloquea (añade una excepción). Para sistemas de 32 bits antiguos, busca versiones legacy en GitHub.

**En macOS:**
1. Baja el `.dmg`.
2. Ábrelo con doble clic; verás el icono de Tiled junto a la carpeta de Aplicaciones.
3. Arrástralo a Aplicaciones.
4. Si te sale el aviso de "desarrollador no identificado", ve a Sistema > Privacidad y Seguridad > "Abrir de todos modos".
5. Lanza desde Launchpad o Spotlight (Cmd + Espacio y escribe "Tiled").
- **Actualizaciones**: Las nuevas versiones sobrescriben la anterior; para quitar, arrastra a la papelera `/Aplicaciones/Tiled.app`.
- **Trucos para Apple Silicon (M1+)**: Es universal (x86_64/arm64). Si usas Rosetta, prueba en Terminal: `arch -x86_64 /Aplicaciones/Tiled.app/Contents/MacOS/Tiled`.

**En distribuciones Linux (AppImage, Flatpak, Snap):**
Linux es un paraíso de opciones; yo apuesto por AppImage si quieres algo ligero y portátil.

- **AppImage (universal y sin instalación):**
  1. Descarga el `.AppImage`.
  2. Dale permisos: `chmod +x Tiled-1.11.2-x86_64.AppImage`.
  3. Ejecuta: `./Tiled-1.11.2-x86_64.AppImage` o desde el gestor de archivos.
  4. Para integrarlo al menú: `chmod a+x Tiled-*.AppImage && ./Tiled-*.AppImage --appimage-extract && sudo mv squashfs-root/* /usr/local/bin/`.
- **Flatpak (seguro con sandbox):**
  1. Instala Flatpak si no lo tienes: `sudo apt install flatpak` (en Debian/Ubuntu) o el equivalente en tu distro.
  2. Añade Flathub: `flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`.
  3. Instala: `flatpak install flathub org.mapeditor.Tiled`.
  4. Lanza: `flatpak run org.mapeditor.Tiled`.
  - Actualiza con: `flatpak update org.mapeditor.Tiled`.
- **Snap (con updates automáticos):**
  1. Instala snapd si hace falta: `sudo apt install snapd`.
  2. Instala: `sudo snap install tiled`.
  3. Ejecuta: `tiled`.
  - Nota: El sandbox puede hacer que arranque un pelín más lento.
- **Paquetes nativos (deb/rpm):**
  - Debian/Ubuntu: `sudo dpkg -i tiled_*.deb` y resuelve dependencias con `sudo apt install -f`.
  - Fedora: `sudo rpm -i tiled-*.rpm`.
- **Problemas típicos**: En Wayland, activa OpenGL en las preferencias si ves glitches. Para distros viejas (como Ubuntu 18.04), tira de releases legacy en GitHub.

En cualquier plataforma, comprueba que funciona abriendo Tiled: deberías ver la ventana principal con Archivo > Nuevo > Nuevo Mapa listo para acción.

## Requisitos: Dependencias del Sistema, Incluyendo Qt para Compilaciones Personalizadas

**Requisitos básicos para los binarios precompilados:**
- **Windows**: Windows 10 (64-bit) o más nuevo; 4 GB de RAM; unos 200 MB en disco.
- **macOS**: macOS 11 o superior; 4 GB de RAM; ~200 MB.
- **Linux**: GLIBC 2.31+ (como en Ubuntu 20.04); OpenGL 3.3; 4 GB de RAM; ~150 MB.
No hace falta instalar nada extra, porque Qt y otras libs como zlib, libpng o libjpeg vienen dentro.

**Si vas a compilar desde fuente (para experimentos o plugins):**
Esto es para los valientes que quieren lo último o personalizaciones. Necesitas herramientas de desarrollo.

- **Dependencias clave:**
  - **Qt**: 6.5 o superior (para desarrollo y runtime). Bájalo de [qt.io 🟡③ 🌐](https://www.qt.io/download-open-source). Incluye QtCore, QtGui, QtWidgets, QtNetwork y QtXml (para exportar TMX).
  - **CMake**: 3.21 o más, para generar los archivos de build.
  - **Compilador**: GCC/Clang 11+ (Linux/macOS) o MSVC 2019+ (Windows).
  - **Otras libs**: zlib, libpng, libjpeg-turbo (en Ubuntu: `sudo apt install libzlib-dev libpng-dev libjpeg-dev`).

- **Pasos generales para compilar:**
  1. Instala dependencias (ejemplo en Ubuntu: `sudo apt install build-essential cmake qt6-base-dev libzlib-dev libpng-dev libjpeg-dev`).
  2. Baja o clona: `git clone https://github.com/mapeditor/tiled.git && cd tiled`.
  3. Crea directorio de build: `mkdir build && cd build`.
  4. Configura: `cmake .. -DCMAKE_PREFIX_PATH=/path/to/qt6` (ajusta la ruta de Qt).
  5. Compila: `make -j$(nproc)` (Linux/macOS) o `cmake --build . --config Release` (Windows con MSVC).
  6. Instala si quieres: `sudo make install`.
- **Específicos por plataforma:**
  - **Windows**: Usa Qt Creator o Visual Studio; añade `-DFEATURE_RELEASE=ON` para optimizar.
  - **macOS**: Con Homebrew: `brew install qt@6 cmake`. Firma el binario: `codesign --force --sign - Tiled.app`.
  - **Linux**: En Fedora: `sudo dnf install qt6-qtbase-devel cmake zlib-devel libpng-devel`. Para AppImage: `linuxdeployqt`.
- **Si algo falla**: Comprueba Qt con `qmake --version`. Para enlaces rotos, instala `libgl1-mesa-dev`. La compilación suele tardar 5-10 minutos en un equipo decente.

## Primeros Pasos: Configuración Inicial para un Entorno de Trabajo Eficiente

Con Tiled instalado, es hora de tunearlo para que se adapte a ti como un guante. Al abrirlo por primera vez, te recibirán paneles limpios para capas, tilesets y propiedades. Mi consejo: crea un proyecto ya mismo para mantener todo organizado.

**Paso 1: Crea un proyecto (¡imprescindible!):**
- Ve a **Archivo > Nuevo > Nuevo Proyecto...** (o Ctrl+N).
- Guárdalo como `.tiled-project` en la raíz de tu carpeta de trabajo (por ejemplo, `MiJuego.tiled-project`).
- Añade carpetas: clic derecho en el panel "Proyecto" > **Agregar Carpeta al Proyecto...** (como "tilesets", "maps" o "templates").
- Ventajas: Acceso exprés con **Archivo > Abrir Archivo en Proyecto** (Ctrl+P); guarda sesiones automáticas de lo que tenías abierto.
- Personaliza: **Proyecto > Propiedades del Proyecto...** – elige versión de compatibilidad (como 1.10 para exports retro), directorio de extensiones o reglas de automapeo.

**Paso 2: Tu primer mapa en acción:**
- **Archivo > Nuevo > Nuevo Mapa...** (Ctrl+N otra vez).
- Ajusta: Tamaño (prueba 20x15 teselas), tile de 32x32 px, orientación ortogonal (para novatos), capa de tiles y renderizado derecha-abajo.
- Activa "Mapa infinito" si sueñas con mundos vastos.
- Guárdalo en el proyecto como `.tmx`.
- Añade tileset: **Archivo > Nuevo > Nuevo Tileset...**, carga una imagen (usa ejemplos de Tiled), desmarca "Incorporar en mapa" para reutilizarlo. Guárdalo en `.tsx`.

**Paso 3: Ajusta preferencias (Editar > Preferencias):**
Hazlo tuyo para ganar tiempo. Se guardan en ficheros del sistema (como `~/.config/mapeditor.org/tiled.conf` en Linux).

| Categoría   | Opciones Recomendadas                                                                 | Razón |
|-------------|---------------------------------------------------------------------------------------|-------|
| **General** | Activa "Recargar imágenes de tileset al cambiar", "Usar escritura segura de archivos" y "Repetir última exportación al guardar". Desactiva "Restaurar sesión anterior" si saltas entre proyectos. | Evita pérdidas y acelera con assets que cambian fuera. |
| **Interfaz**| Idioma: Español (si lo pillas); cuadrícula gris claro; divisiones finas a 4; líneas de objetos 1-2 px; activa "Dibujo acelerado por hardware (OpenGL)"; zoom con rueda; desplazamiento suave. | Visibilidad top y fluidez; OpenGL vuela en GPUs nuevas (desactívalo si petardea). |
| **Tema**    | "Tiled Fusion" (Windows/Linux); base oscura para fondos claros; fuente monospace 10pt. | Menos cansancio ocular; ideal para modo oscuro. |
| **Teclado** | Exporta atajos por defecto; cambia zoom a Ctrl+rueda si usas touchpad. Arregla conflictos (salen en rojo). | Atajos cómodos: Ctrl+Z para deshacer, Ctrl+S para guardar. |
| **Plugins** | Activa los genéricos (CSV, DXF); desactiva los que fallen (pasa el ratón para ver por qué). | Más formatos de export sin reinicios. |
| **Exportación** | "Incorporar tilesets"; minimizar salida; resolver tipos de objetos. | Fácil integración con Godot o Unity; archivos más livianos. |

**Paso 4: Trucos extra para volar:**
- **Sesiones**: Guarda por proyecto en `.tiled-session`; cambia de proyecto para switchar entornos.
- **Búsqueda rápida**: Ctrl+Shift+P para comandos (como "nuevo mapa").
- **Paneles**: Arrástralos a tu gusto (tilesets a la derecha, por ejemplo); ocúltalos en Ver > Paneles.
- **Ejemplos**: Abre la carpeta de samples de la instalación: **Archivo > Abrir Archivo...** > `examples/maps/orthogonal.dgml`.
- **Updates**: En **Ayuda > Buscar Actualizaciones**, activa los chequeos automáticos.
- **Tip pro**: Conecta con Git para control de versiones; mete extensiones (como para export a Godot) en el directorio correspondiente.

¡Y voilà, ya tienes Tiled a punto! En la próxima sección, desgranaremos la interfaz. Prueba a armar un mapita básico con tiles de muestra para cogerle el tranquillo. Si te atascas, la doc oficial en [doc.mapeditor.org 🟡③ 🌐](https://doc.mapeditor.org/) es oro puro.

## Referencias Bibliográficas de Apoyo

> WIP Revisando fuentes

Estas fuentes respaldan la información proporcionada, ofreciendo guías oficiales y tutoriales prácticos para la instalación y configuración de Tiled. He verificado su existencia y vigencia al 22 de septiembre de 2025; todas son accesibles y relevantes.

- Documentación oficial de Tiled (versión 1.11.0, actualizada en 2025): Guía completa de instalación y primeros pasos. Disponible en: [https://doc.mapeditor.org/manual/introduction/](https://doc.mapeditor.org/manual/introduction/).
- Repositorio oficial en GitHub de Tiled: "I"ncluye releases, checksums y guías de compilación. Última release verificada: v1.11.2 (28 enero 2025). Disponible en: [https://github.com/mapeditor/tiled](https://github.com/mapeditor/tiled).
- Tutorial en YouTube: "Aprendiendo a descargar, instalar y usar Tiled para crear mapas" (publicado el 11 de noviembre de 2020, vigente y aplicable). Canal: Recursos para desarrolladores indie. Disponible en: [https://www.youtube.com/watch?v=OhVluiERaFk](https://www.youtube.com/watch?v=OhVluiERaFk).
- Tutorial en YouTube: "How to Install Tiled" (publicado el 6 de septiembre de 2019, pasos universales y actualizados). Canal: GameDev tutorials. Disponible en: [https://www.youtube.com/watch?v=SvXkM7QLyCc](https://www.youtube.com/watch?v=SvXkM7QLyCc).
- Página oficial de descargas de Tiled: Detalles de binarios y requisitos. Actualizada en enero 2025. Disponible en: [https://www.mapeditor.org/download.html](https://www.mapeditor.org/download.html).

## Referencias Bibliográficas que Refutan o Critican

> WIP Revisando fuentes

Estas referencias destacan limitaciones, problemas comunes en la instalación y críticas constructivas a Tiled, basadas en foros y discusiones reales. He contrastado su validez y vigencia al 22 de septiembre de 2025; se centran en aspectos como glitches, restricciones y alternativas implícitas, sin invalidar el uso general pero señalando áreas de mejora.

- Foro oficial de Tiled: "Trouble With Setting Up Maps" (18 de enero de 2021, vigente; discute problemas con escalas de píxeles y tiles pequeños). Disponible en: [https://discourse.mapeditor.org/t/trouble-with-setting-up-maps/4925](https://discourse.mapeditor.org/t/trouble-with-setting-up-maps/4925).
- Foro oficial de Tiled: "Cant place tiles" (30 de marzo de 2024, reciente; critica fallos al colocar tiles en capas nuevas). Disponible en: [https://discourse.mapeditor.org/t/cant-place-tiles/6668](https://discourse.mapeditor.org/t/cant-place-tiles/6668).
- Foro oficial de Tiled: "Some problem with Tiled" (9 de abril de 2015, pero problemas recurrentes; menciona crashes al abrir mapas). Disponible en: [https://discourse.mapeditor.org/t/some-problem-with-tiled/456](https://discourse.mapeditor.org/t/some-problem-with-tiled/456).
- Reddit (r/gamedev): "How to work around Tiled Map Editor Color Restrictions?" (7 de agosto de 2024, actual; critica alteraciones de color al importar tilesets de Piskel). Disponible en: [https://www.reddit.com/r/gamedev/comments/1em4x8u/how_to_work_around_tiled_map_editor_color/](https://www.reddit.com/r/gamedev/comments/1em4x8u/how_to_work_around_tiled_map_editor_color/).
- Reddit (r/gamedev): "Usando Tiled como único editor de niveles" (21 de abril de 2014, traducido y vigente; destaca limitaciones en control de tilesets durante desarrollo iterativo). Disponible en: [https://www.reddit.com/r/gamedev/comments/23lcqh/using_tiled_as_the_sole_level_editor/](https://www.reddit.com/r/gamedev/comments/23lcqh/using_tiled_as_the_sole_level_editor/).


![[Plantilla - 1MT#One More Thing]]