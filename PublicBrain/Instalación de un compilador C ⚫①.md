---
iaStatus: 0
iaStatus_Model: gpt-3.5-turbo
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.658Z
modified: 2024-05-15T21:45:25.622Z
supervisado: 2024-04-14T14:29:03.560Z
ACCION: 
ver_major: 0
ver_minor: 3
ver_rev: 26
nav_primary: 
nav_secondary: 
tags:
---
# Instalación de un compilador C ⚫①

[[Aprender el Lenguaje C desde Cero ⚫①]]

Claro, instalar un compilador C es el primer paso esencial para comenzar a programar en C. Aquí te proporcionaré una guía básica para instalar un compilador C en diferentes sistemas operativos:

### Instalación en Windows:

#### 1. MinGW (Minimalist GNU for Windows):
- Visita el sitio web de MinGW: [MinGW](http://www.mingw.org/)
- Descarga el instalador `mingw-get-setup.exe`.
- Ejecuta el instalador y sigue las instrucciones para completar la instalación.
- Durante la instalación, asegúrate de seleccionar al menos el paquete `mingw32-base`.
- Una vez instalado, abre el símbolo del sistema (cmd) y verifica que el compilador GCC esté instalado correctamente escribiendo `gcc --version`.

### Instalación en macOS:

#### 1. Xcode Command Line Tools:
- Abre Terminal desde la carpeta de Aplicaciones/Utilidades.
- Ejecuta el siguiente comando:
  ```
  xcode-select --install
  ```
- Esto instalará las herramientas de línea de comandos necesarias, incluido el compilador Clang.

### Instalación en Linux (Ubuntu/Debian):

#### 1. GCC (GNU Compiler Collection):
- Abre Terminal.
- Ejecuta el siguiente comando:
  ```
  sudo apt update
  sudo apt install build-essential
  ```
- Esto instalará el compilador GCC y otros paquetes esenciales para compilar programas en C.

### Verificación de la Instalación:

Una vez que hayas instalado el compilador C, puedes verificar que esté instalado correctamente abriendo una terminal y escribiendo el siguiente comando para GCC:

```
gcc --version
```

Este comando debería mostrar la versión del compilador GCC instalada en tu sistema.

Después de instalar el compilador, puedes comenzar a escribir y compilar programas en C utilizando un editor de texto simple como Notepad (en Windows), Vim, Nano o cualquier otro editor de texto que prefieras. Luego, puedes compilar tus programas utilizando el compilador que instalaste siguiendo las instrucciones proporcionadas en la documentación del compilador.

![[⚫🔴🟡🟢🔵⚪ (🔴②)#Sobre el sistema de validez de un contenido en MetsuOS]]