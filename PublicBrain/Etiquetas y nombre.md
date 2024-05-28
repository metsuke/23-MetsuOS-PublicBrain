---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.190Z
modified: 2024-05-28T17:55:03.301Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 5
nav_primary: 
nav_secondary: 
tags:
---
# Etiquetas y nombre

[[WCAG 2.0 ⚫①]] | [[WCAG 2.1 ⚫①]]

Las Directrices de Accesibilidad para el Contenido Web (WCAG) 2.1 proporcionan un conjunto de normas y recomendaciones para hacer que el contenido web sea más accesible para personas con discapacidades. Uno de los aspectos importantes que abordan las WCAG 2.1 es la utilización adecuada de etiquetas y nombres para mejorar la accesibilidad. A continuación, se detallan los principios y recomendaciones relacionadas con este tema:

## Principio 2: Operable
### Directriz 2.5: Modalidades de Entrada
El principio de "Operable" se refiere a que los componentes de la interfaz de usuario y la navegación deben ser operables. La Directriz 2.5 se centra en las modalidades de entrada, y uno de sus criterios de éxito relevantes es el criterio 2.5.3 "Etiqueta en el Nombre".

### Criterio de Éxito 2.5.3: Etiqueta en el Nombre
Este criterio requiere que, para todos los componentes de la interfaz de usuario (incluyendo pero no limitándose a: formularios, enlaces y componentes generados por scripts), las etiquetas incluyan el nombre accesible. El propósito es asegurar que las etiquetas visibles a los usuarios coincidan con el nombre programático utilizado por las tecnologías de asistencia, como los lectores de pantalla.

#### Requisitos del Criterio 2.5.3:
- **Consistencia entre Etiqueta y Nombre**: La etiqueta visible de un elemento de la interfaz de usuario debe coincidir o contener el texto exacto del nombre accesible programático. Esto mejora la experiencia de usuarios que dependen de tecnologías de asistencia, ya que asegura que el texto que ven coincide con el que oyen.
- **Uso de Atributos Semánticos**: Utilizar atributos HTML adecuados como `aria-label`, `aria-labelledby` junto con etiquetas visibles (`<label>`, `alt` en imágenes, etc.) para garantizar que la información sea accesible.
  
#### Ejemplo:
Si un botón tiene la etiqueta visible "Enviar", el nombre accesible programático debería ser también "Enviar". Esto se puede lograr de la siguiente manera:

```html
<!-- Incorrecto -->
<button aria-label="Enviar el formulario">Enviar</button>

<!-- Correcto -->
<button aria-label="Enviar">Enviar</button>
```

## Otros Criterios Relacionados con Etiquetas y Nombres:
### Criterio de Éxito 1.1.1: Contenido No Textual
Este criterio establece que todo contenido no textual (como imágenes, gráficos y otros elementos multimedia) debe tener un texto alternativo que sirva el mismo propósito. El uso adecuado de `alt` en imágenes es crucial para cumplir con este criterio.

#### Ejemplo:
```html
<!-- Incorrecto -->
<img src="imagen.jpg">

<!-- Correcto -->
<img src="imagen.jpg" alt="Descripción de la imagen">
```

### Criterio de Éxito 1.3.1: "I"nformación y Relaciones

Este criterio busca asegurar que la estructura y las relaciones entre la información sean explícitas, mediante el uso de etiquetas y elementos semánticos de HTML. Por ejemplo, el uso de `<label>` para asociar una etiqueta de texto con un campo de formulario.

#### Ejemplo:

```html
<!-- Incorrecto -->
<input type="text" id="nombre">
<label for="nombre_usuario">Nombre:</label>

<!-- Correcto -->
<label for="nombre">Nombre:</label>
<input type="text" id="nombre">
```

## Beneficios de Cumplir con las Normas de Etiquetas y Nombres:
- **Mejora de la Experiencia de Usuario**: Los usuarios que dependen de tecnologías de asistencia podrán navegar e interactuar con el contenido de manera más eficiente y efectiva.
- **Acceso Universal**: Garantiza que todos los usuarios, independientemente de sus discapacidades, puedan acceder a la información y las funcionalidades de la página.
- **Cumplimiento Legal**: Ayuda a cumplir con las leyes y regulaciones de accesibilidad web, evitando posibles problemas legales.
## Conclusión
Las etiquetas y nombres desempeñan un papel crucial en la accesibilidad web según las WCAG 2.1. Asegurar que las etiquetas visibles y los nombres programáticos coincidan no solo mejora la usabilidad para las personas con discapacidades, sino que también contribuye a una experiencia web más inclusiva y equitativa para todos los usuarios.

![[⚫🔴🟡🟢🔵⚪ (🔴②)#Sobre el sistema de validez de un contenido en MetsuOS]]