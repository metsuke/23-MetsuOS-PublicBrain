---
iaStatus: 8
iaStatus_Model: Gemini, Grok, Raul Carrillo aka metsuke
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: -3
lang: ES
translations:
created: 2026-06-04T21:13:17.460Z
modified: 2026-06-14T19:07:52.187Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 8
nav_primary: []
nav_secondary: []
tags: []
---
# Curso de GNU-Linux  🟡③

![Curso GNU Linux](_resources/2578748872e4e1a7128a1cae5cb508f4_MD5.jpg)

[[KB]]

> OJO: Este es uno de los cursos mas a largo plazo que he abordado nunca, es integral , a gran escala y dependiente de mi propio proceso de aprendizaje e implmentación. Tómese más del lado "mis apuntes" que del lado "mi curso". Quizá una vez completo y avanzado llegue a publicarlo como obra en físico, ya veremos.

Este itinerario formativo está diseñado para transformar la comprensión técnica del estudiante, partiendo de los fundamentos éticos y arquitectónicos hasta alcanzar el control total de la administración de servidores y la automatización de procesos.

DISCLAIMER: en este curso no somos ni extremistas radicales del GNU ni liberales absolutos del lado Linux, aquí aplica [[Blog - El Antiintromisionismo, una propuesta filosófica y práctica 🟡③|Antiintromisionismo 🟡③]] y  [CPS 🟡③🌐](https://www.youtube.com/watch?v=X9vwT8lLkhI). Si eres un taliban de cualquiera de los bandos, o un extremista religioso/ideológico a secas, este no es tu lugar, te insto a que des media vuelta y marches a casa. Si decides continuar, pierde toda esperanza.

## 1. Fundamentos y Arquitectura del Sistema

### 1.1. El Manifiesto del Software Libre

--- start-multi-column: BloqueMicrohobbit01\
```column-settings  
Number of Columns: 2
Border: off
```

![Ética y Libertades de la FS](PublicBrain/_resources/dbc6f193b8a6fe8b432af824703c8b19_MD5.jpg)

## Ética y Libertades de la FSF

Análisis de las cuatro libertades de la FSF y el impacto de la licencia GPL en el desarrollo tecnológico moderno.

Continua leyendo en ... [[Ética y Libertades de la FSF 🟡③]]: 

 --- column-end ---

- **La simbiosis GNU+Linux:** Entendiendo la distinción entre el kernel (Linux) y el sistema operativo (GNU).
- **Criterios de selección de Distribuciones:** Comparativa técnica entre familias (Debian/Ubuntu, RHEL/Fedora, Arch Linux) y la filosofía _Rolling Release_ frente a _LTS_.
- Distribuciones Linux centradas en Ciberseguridad.

 --- column-end ---
--- multi-column-end

### 1.2. El Proceso de Arranque (Booting)

- **Hardware y Firmware:** Del encendido al control del kernel: UEFI, GPT y la gestión de la tabla de particiones.
- **Gestores de Arranque:** Configuración avanzada de GRUB2 y recuperación de sistemas críticos.
- **Sistemas de Archivos:** Rendimiento y resiliencia en EXT4, Btrfs y la implementación de ZFS en Linux.
## 2. Inmersión en la Línea de Comandos (CLI)

### 2.1. El Estándar Jerárquico (FHS)

- **Navegación Estructural:** Por qué "todo es un fichero". Uso profundo de la jerarquía en `/etc`, `/proc`, `/sys`y `/var`.
- **Manipulación Atómica:** Comandos de gestión de datos (`rsync`, `find`, `grep`, `awk`) para el procesamiento de información.    

## 2.2 La Biblia de los comandos en GNU/Linux

* Comandos básicos
* (WIP)
### 2.3. Gestión de Privilegios y Seguridad Atómica

- **Modelo de Permisos:** Más allá de `chmod`: "I"mplementación de ACLs (Listas de Control de Acceso) y atributos extendidos.
    
- **Administración Delegada:** Configuración segura de `sudo` y políticas de usuarios.
    

## 3. Administración y Optimización

### 3.1. Gestión de Ciclo de Vida de Software

- **Gestores Nativos:** Dominio de `apt`, `dnf` y `pacman`. Resolución manual de dependencias y gestión de repositorios.
    
- **Paquetería Aislada:** Análisis crítico de entornos inmutables y contenedores: Flatpak, Snap y AppImage.
    

### 3.2. Control de Servicios con Systemd

- **Unidades y Objetivos:** Creación de _unit files_ personalizados, gestión de logs con `journalctl` y control de dependencias entre servicios.
    

## 4. Redes, Automatización y Shell Scripting

### 4.1. Networking y Fortificación

- **Pila de Red:** Configuración avanzada con `iproute2` y resolución de nombres.
    
- **Túneles Seguros:** Implementación de SSH con autenticación por clave pública y redirección de puertos.
    

### 4.2. Lógica de Programación en Bash

- **Automatización Industrial:** Creación de scripts robustos utilizando estructuras de control, manejo de señales y expresiones regulares.
    

## 5. Personalización del sistema

### 5.1. Distribuciones y sus posibilidades de personalización.

* Distribuciones existentes y sus posibilidades
* Distribuciones desde la perspectiva de la personalización por parte del usuario.
* Distribuciones desde la perspectiva de la creación de Distribuciones a medida.

### 5.2 El caso específico de Arch Linux: El Toolbox Definitivo

* Posibilidades de Personalización.

### 5.3 El caso específico de Debian: La Tortuga 4x4

* Creando Distribuciones personalizadas.

## Referencias Bibliográficas

### Fuentes de Apoyo y Validación

1. [Libro: The Linux Command Line: A Complete Introduction. William Shotts (2019). Editorial No Starch Press. 🟡③🌐](https://www.linuxcommand.org/tlcl.php) .- Página oficial del libro que ofrece acceso gratuito a la obra y recursos complementarios para el aprendizaje de la línea de comandos. 
2. [Linux desde CERO: Mi guía personal para NOVATOS. Canal: Nate Gentile. 🟡③🌐](https://www.youtube.com/watch?v=knrc4q1S_q0) .- Explicación didáctica y profunda sobre el entorno Linux para principiantes
3. [Documentación Oficial: The Linux Foundation - Training Resources. 🟡③🌐](https://training.linuxfoundation.org/resources/) .- Portal oficial de recursos, guías y materiales de preparación para certificaciones profesionales de Linux Foundation.
4. [Curso sobre GNU/Linux en Hack4u  🟡③🌐](https://hack4u.iol) - Durante mi proceso de aprendizaje completo secciones que luego desarrollo usando IA, mis conocimientos previos junto a los adquiridos en eproceso y la guia de "lo que existe" que ofrece el curso. Mi sistema de apuntes elevado a la enésima potencia.
 
### Fuentes de Matización y Perspectiva Crítica

1. [Ensayo: The Cathedral and the Bazaar. Eric S. Raymond 🟡③🌐](http://www.catb.org/~esr/writings/cathedral-bazaar/) .- Aunque defiende el código abierto, critica el modelo de desarrollo excesivamente centralizado ("la catedral") que algunos proyectos de GNU han mantenido, proponiendo un modelo más descentralizado.
2. [Vídeo Crítico: "Linux is NOT for Everyone". Canal: Linus Tech Tips 🟡③🌐](https://www.youtube.com/watch?v=ZwEkKhBHbEE) .- Refuta la idea de que Linux es un reemplazo directo para cualquier usuario, señalando problemas reales de fragmentación, falta de soporte de drivers propietarios y la complejidad de la CLI para el usuario medio.
3. [Artículo Técnico: "The Systemd Controversy" 🟡③🌐](https://wiki.debian.org/Debate/initsystem/systemd) .- Resumen de la comunidad sobre la resistencia a Systemd, argumentando que rompe la filosofía Unix de "hacer una sola cosa y hacerla bien" al ser un sistema demasiado monolítico. 

 


![[Plantilla - 1MT#One More Thing]]