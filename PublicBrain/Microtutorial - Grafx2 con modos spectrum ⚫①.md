---
iaStatus: 8
iaStatus_Model: ""
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-08-09T10:54:01.392Z
modified: 2025-08-09T11:05:58.864Z
supervisado: ""
ACCION: 
ver_major: 0
ver_minor: 2
ver_rev: 1
nav_primary: 
nav_secondary: 
tags:
---
# Microtutorial - Grafx2 con modos spectrum ⚫①

[[Index]]

Para usar los modos ZX Spectrum en Grafx2, un programa de edición de píxeles que emula las restricciones de máquinas retro como el ZX Spectrum, sigue estos pasos:

1. **Iniciar Grafx2 con el modo ZX Spectrum**:
   - Abre Grafx2 desde la línea de comandos para establecer un modo de paleta restringida que emule el ZX Spectrum. Usa el comando:
     ```bash
     grafx2 /rgb 2
     ```
     Esto configura una paleta de 16 colores estilo ZX Spectrum.[](http://grafx2.chez.com/index.php?article5/command-line-options)

2. **Activar el modo de restricciones de bloques ZX Spectrum**:
   - En Grafx2, el modo ZX Spectrum impone restricciones de bloque, permitiendo solo **2 colores diferentes por bloque de 8x8 píxeles**, como en el hardware original.[](https://grafx2.gitlab.io/grafX2/htmldoc/grafx2_42.html)[](https://www.slant.co/options/5469/~grafx2-review)
   - Para activar este modo, ve al menú **Settings** (atajo: Shift+F10) y selecciona una resolución compatible, como 320x200 o 256x192, típica del ZX Spectrum.[](https://manpages.ubuntu.com/manpages/questing/en/man1/grafx2.1.html)
   - Luego, en el menú de efectos de dibujo (atajo: E), selecciona **ZX Spectrum** bajo los modos de bloque para activar las restricciones de color por bloque.

3. **Configurar la paleta**:
   - Haz clic derecho en el botón **Pal** en la interfaz para ajustar la precisión RGB. Configura el valor a **2** para emular la paleta limitada del ZX Spectrum (16 colores).[](https://rpg.hamsterrepublic.com/ohrrpgce/Grafx2)
   - Asegúrate de que la paleta esté restringida a los colores disponibles en el ZX Spectrum (colores brillantes y normales, sin tonos intermedios).

4. **Dibujar con restricciones**:
   - Con el modo ZX Spectrum activado, cada bloque de 8x8 píxeles estará limitado a dos colores. Usa las herramientas de dibujo (pincel, líneas, etc.) manteniendo esta restricción.
   - Puedes usar el modo **Grid** (atajo: G) para visualizar la cuadrícula de 8x8 píxeles y asegurarte de respetar las limitaciones. Configura la cuadrícula en el menú **Grid** (Shift+G) con dimensiones 8x8.[](https://kapeli.com/cheat_sheets/Grafx2.docset/Contents/Resources/Documents/index)

5. **Comprobar colores usados**:
   - Grafx2 te permite ver cuántos colores estás usando. Esto es útil para asegurarte de no exceder la paleta limitada del ZX Spectrum. Revisa esto en la sección de paleta en la interfaz.[](https://rpg.hamsterrepublic.com/ohrrpgce/Grafx2)

6. **Exportar o guardar**:
   - Cuando termines, guarda tu imagen en un formato compatible, como PNG, asegurándote de mantener la paleta indexada. Si necesitas exportar sin fondo, ajusta la configuración de transparencia en el menú de exportación.[](https://perfectlynormalduck.wordpress.com/2016/10/26/quick-guide-to-grafx2-success/)

**Notas adicionales**:
- Puedes personalizar atajos de teclado en el menú de ayuda para agilizar el acceso a estas funciones.[](https://kapeli.com/cheat_sheets/Grafx2.docset/Contents/Resources/Documents/index)
- Si necesitas más detalles sobre cómo funcionan los modos de dibujo, consulta la documentación oficial en http://code.google.com/p/grafx2/wiki/DrawingModes.[](https://rpg.hamsterrepublic.com/ohrrpgce/Grafx2)
- Para una experiencia más auténtica, considera usar el modo **Tilemap** para propagar cambios en patrones repetitivos, útil para gráficos de juegos retro.[](https://rpg.hamsterrepublic.com/ohrrpgce/Grafx2)

Si tienes problemas al iniciar el programa o configurar el modo, revisa el archivo `stderr.txt` en [el directorio de Grafx2 para diagnosticar errores aquí](http://grafx2.chez.com/index.php?categorie1/documentation)


![[Plantilla - 1MT#One More Thing]]