---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-08-31T19:42:49.587Z
modified: 2024-08-31T19:45:59.115Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 3
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# Diagrama de bloques del sistema operativo MetsuOS  ⚫①

[[Creando MetsuOS ⚫①]]

**DISCLAIMER Texto experimental**

```mermaid
graph TD
    subgraph Servidor
        A[API REST] --> B[Base de Datos]
        B --> C[Procesamiento de Tareas]
        C --> D[Ejecución de Tareas Automáticas]
        D --> E[Información y Estadísticas]
    end

    subgraph Cliente Local
        F[Interfaz de Usuario] --> G[Creación y Edición de Tareas]
        G --> H[Ejecución de Tareas Automáticas]
        H --> I[Información y Estadísticas]
    end

    subgraph Cliente Web
        J[Interfaz Web] --> K[Creación y Edición de Tareas]
        K --> L[Información y Estadísticas]
        L --> M[Configuración de Tareas Automáticas]
    end

    A --> F
    A --> J
    B --> G
    B --> K
    C --> H
    C --> M
    D --> I
    E --> F
    E --> J
```

En este diagrama, se pueden ver los siguientes componentes:

* **Servidor**: El corazón del sistema, que se encarga de procesar y almacenar las tareas. Está compuesto por:
 + **API REST**: La interfaz de comunicación con los clientes.
 + **Base de Datos**: El almacenamiento de las tareas y la información del usuario.
 + **Procesamiento de Tareas**: El motor que ejecuta las tareas automáticas y manuales.
 + **Ejecución de Tareas Automáticas**: El componente que ejecuta las tareas automáticas en segundo plano.
 + **Información y Estadísticas**: El componente que proporciona información y estadísticas sobre las tareas.
* **Cliente Local**: La aplicación que se instala en la máquina del usuario y se comunica con el servidor a través de la API REST. Está compuesto por:
 + **Interfaz de Usuario**: La interfaz que muestra las tareas asignadas al usuario.
 + **Creación y Edición de Tareas**: El componente que permite al usuario crear y editar tareas manuales.
 + **Ejecución de Tareas Automáticas**: El componente que ejecuta las tareas automáticas en segundo plano.
 + **Información y Estadísticas**: El componente que proporciona información y estadísticas sobre las tareas.
* **Cliente Web**: La interfaz web que permite a los usuarios gestionar las tareas de forma remota. Está compuesto por:
 + **Interfaz Web**: La interfaz que muestra las tareas asignadas al usuario.
 + **Creación y Edición de Tareas**: El componente que permite al usuario crear y editar tareas manuales.
 + **Información y Estadísticas**: El componente que proporciona información y estadísticas sobre las tareas.
 + **Configuración de Tareas Automáticas**: El componente que permite al usuario configurar las tareas automáticas.

En resumen, el diagrama de bloques del sistema operativo MetsuOS muestra la arquitectura del sistema, que se compone de un servidor que procesa y almacena las tareas, y dos clientes (local y web) que permiten a los usuarios gestionar las tareas de forma remota.

![[Plantilla - 1MT#One More Thing]]