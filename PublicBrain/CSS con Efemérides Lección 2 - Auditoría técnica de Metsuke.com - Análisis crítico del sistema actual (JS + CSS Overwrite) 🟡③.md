---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations:
created: 2026-02-08T17:33:58.591Z
modified: 2026-02-09T01:21:12.423Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 4
nav_primary: []
nav_secondary: []
tags: []
MOS_TopImg_Video: CursoCSSEfemerides_002.mp4
---
# CSS con Efemérides Lección 2 - Auditoría técnica de Metsuke.com - Análisis crítico del sistema actual (JS + CSS Overwrite) 🟡③

![CSS Efemerides Lección 2 Auditoría técnica de Metsuke.com: Análisis crítico del sistema actual (JS + CSS Overwrite)](PublicBrain/_resources/b5a595e79fa9eaca0a0b33f9d35adcf9_MD5.jpg)

[[Curso Estructura de CSS Dinámico con Efemérides 🟡③]]

## Introducción

En esta lección vamos a sumergirnos en una auditoría técnica detallada del sistema que se usa actualmente en Metsuke.com, basado en JavaScript (JS) para la lógica y sobrescrituras de CSS para los estilos. El foco está en evaluar sus puntos fuertes y débiles, especialmente en cómo maneja los cambios visuales temporales, como efemérides (fechas especiales como aniversarios, eventos históricos o celebraciones estacionales).

Esta auditoría actúa como un diagnóstico inicial para el curso. Identificaremos problemas en el manejo de estilos dinámicos, el rendimiento, la escalabilidad, la facilidad de mantenimiento y la compatibilidad con actualizaciones frecuentes. Al final, sugeriremos mejoras que nos guiarán en las próximas lecciones, como el uso de preprocesadores como Sass/SCSS, metodologías como ITCSS o BEM, y herramientas de automatización.

Para ponernos en contexto, Metsuke.com es un sitio web dedicado a promover la inclusión plena a través de los videojuegos, con énfasis en accesibilidad, usabilidad y narrativas visuales. El sistema actual permite que el sitio cambie su apariencia según efemérides, modificando colores, tipografías, imágenes o disposiciones sin alterar la estructura básica. Sin embargo, esto se logra con JS para la detección temporal y sobrescrituras de CSS para aplicar los estilos.

**Nota sobre el método:** Esta auditoría se basa en un análisis conceptual y práctico de sistemas similares (ya que el acceso al código fuente real de Metsuke.com es limitado en este entorno educativo). Usaremos ejemplos genéricos pero ilustrativos. En un caso real, recomendaría herramientas como las DevTools de Chrome, Lighthouse o WebPageTest para mediciones precisas.

## Descripción de la Arquitectura Actual

### Componente JavaScript (JS)

El corazón dinámico del sistema es JavaScript, que gestiona las efemérides. JS se ocupa de:
- **Detección de efemérides:** Usa una estructura JSON cargada manualmente dentro del propio fichero JS.
- **Lógica condicional:** Según la fecha, selecciona un "tema" (por ejemplo, "Lanzamiento Microhobby" o "Lanzamiento Sega Saturn") y aplica los cambios. El proceso agrega una css de apoyo que modifica la hoja principal para que adopte el estilo deseado.
- **Integración con el DOM:** JS se encarga de cambiar la imagen de cabecera y el claim principal por el correspondiente al evento, calculando el tiempo transcurrido en años.

Aquí el código JS actual:

```javascript
const efemerides = {
    '05-11': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Dia Lanzamiento Sega Saturn en Norteamérica' },
    '05-12': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana lanzamiento Sega Saturn en Norteamérica' },
    '05-13': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana lanzamiento Sega Saturn en Norteamérica' },
    '05-14': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana lanzamiento Sega Saturn en Norteamérica' },
    '05-15': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana lanzamiento Sega Saturn en Norteamérica' },
    '05-16': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana lanzamiento Sega Saturn en Norteamérica' },
    '05-17': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana lanzamiento Sega Saturn en Norteamérica' },
    '07-02': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Dia Lanzamiento Shinning Force II en España y Europa' },
    '07-03': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en España y Europa' },
    '07-04': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en España y Europa' },
    '07-05': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en España y Europa' },
    '07-06': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en España y Europa' },
    '07-07': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en España y Europa' },
    '07-08': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Dia Lanzamiento Sega Saturn en España y Europa' },
    '07-09': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana Lanzamiento Sega Saturn en España y Europa' },
    '07-10': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana Lanzamiento Sega Saturn en España y Europa' },
    '07-11': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana Lanzamiento Sega Saturn en España y Europa' },
    '07-12': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana Lanzamiento Sega Saturn en España y Europa' },
    '07-13': { system: 'Lanzamiento Sega Saturn', year: 1995, desc: 'Semana Lanzamiento Sega Saturn en España y Europa' },
    '07-14': { system: 'Lanzamiento MH218', year: 2025, desc: 'Dia Lanzamiento Microhobby 218' },
    '07-15': { system: 'Lanzamiento MH218', year: 2025, desc: 'Semana Lanzamiento Microhobby 218' },
    '07-16': { system: 'Lanzamiento MH218', year: 2025, desc: 'Semana Lanzamiento Microhobby 218' },
    '07-17': { system: 'Lanzamiento MH218', year: 2025, desc: 'Semana Lanzamiento Microhobby 218' },
    '07-18': { system: 'Lanzamiento MH218', year: 2025, desc: 'Semana Lanzamiento Microhobby 218' },
    '07-19': { system: 'Lanzamiento MH218', year: 2025, desc: 'Semana Lanzamiento Microhobby 218' },
    '07-20': { system: 'Lanzamiento MH218', year: 2025, desc: 'Semana Lanzamiento Microhobby 218' },
    '08-29': { system: 'Dia Mundial Videojuego', year: 2008, desc: 'Dia Mundial del Videojuego', ref: 'https://efemeridesvideojuegos.com/efemerides-videojuegos-21-de-julio/' },
    '10-01': { system: 'Lanzamiento Shinning Force 2', year: 1993, desc: 'Dia Lanzamiento Shinning Force II en Japón' },
    '10-02': { system: 'Lanzamiento Shinning Force 2', year: 1993, desc: 'Semana Lanzamiento Shinning Force II en Japón' },
    '10-03': { system: 'Lanzamiento Shinning Force 2', year: 1993, desc: 'Semana Lanzamiento Shinning Force II en Japón' },
    '10-04': { system: 'Lanzamiento Shinning Force 2', year: 1993, desc: 'Semana Lanzamiento Shinning Force II en Japón' },
    '10-05': { system: 'Lanzamiento Shinning Force 2', year: 1993, desc: 'Semana Lanzamiento Shinning Force II en Japón' },
    '10-06': { system: 'Lanzamiento Shinning Force 2', year: 1993, desc: 'Semana Lanzamiento Shinning Force II en Japón' },
    '10-07': { system: 'Lanzamiento Shinning Force 2', year: 1993, desc: 'Semana Lanzamiento Shinning Force II en Japón' },
    '10-19': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Dia Lanzamiento Shinning Force II en Norteamérica' },
    '10-20': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en Norteamérica' },
    '10-21': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en Norteamérica' },
    '10-22': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en Norteamérica' },
    '10-23': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en Norteamérica' },
    '10-24': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en Norteamérica' },
    '10-25': { system: 'Lanzamiento Shinning Force 2', year: 1994, desc: 'Semana Lanzamiento Shinning Force II en Norteamérica' },
    '11-04': { system: 'Lanzamiento Pixels', year: 2024, desc: 'Dia Lanzamiento Revista Pixels' },
    '11-05': { system: 'Lanzamiento MH218', year: 1984, desc: 'Dia Lanzamiento Revista Microhobby' },
    '11-06': { system: 'Lanzamiento Pixels', year: 2024, desc: 'Semana Lanzamiento Revista Pixels' },
    '11-07': { system: 'Lanzamiento MH218', year: 1984, desc: 'Semana Lanzamiento Revista Microhobby' },
    '11-08': { system: 'Lanzamiento Pixels', year: 2024, desc: 'Semana Lanzamiento Revista Pixels' },
    '11-09': { system: 'Lanzamiento MH218', year: 1984, desc: 'Semana Lanzamiento Revista Microhobby' },
    '11-10': { system: 'Lanzamiento Pixels', year: 2024, desc: 'Semana Lanzamiento Revista Pixels' },
    '11-11': { system: 'Lanzamiento MH218', year: 1984, desc: 'Semana Lanzamiento Revista Microhobby' },
    '11-22': { system: 'Lanzamiento Sega Saturn', year: 1994, desc: 'Dia Lanzamiento Sega Saturn en Japón' },
    '11-23': { system: 'Lanzamiento Sega Saturn', year: 1994, desc: 'Semana Lanzamiento Sega Saturn en Japón' },
    '11-24': { system: 'Lanzamiento Sega Saturn', year: 1994, desc: 'Semana Lanzamiento Sega Saturn en Japón' },
    '11-25': { system: 'Lanzamiento Sega Saturn', year: 1994, desc: 'Semana Lanzamiento Sega Saturn en Japón' },
    '11-26': { system: 'Lanzamiento Sega Saturn', year: 1994, desc: 'Semana Lanzamiento Sega Saturn en Japón' },
    '11-27': { system: 'Lanzamiento Sega Saturn', year: 1994, desc: 'Semana Lanzamiento Sega Saturn en Japón' },
    '11-28': { system: 'Lanzamiento Sega Saturn', year: 1994, desc: 'Semana Lanzamiento Sega Saturn en Japón' },
};

let eventData = "Construyendo la plena inclusión a través del videojuego";

function getEfemeridesCSS() {
    const urlParams = new URLSearchParams(window.location.search);
    const testDate = urlParams.get('test_date');
    const currentDate = testDate ? new Date(testDate) : new Date();

    const month = (currentDate.getMonth() + 1).toString().padStart(2, '0');
    const day = currentDate.getDate().toString().padStart(2, '0');
    const monthDay = `${month}-${day}`;

    let cssFile = 'default.css';
    
    if (efemerides[monthDay]) {
        const system = efemerides[monthDay].system;
        cssFile = system.toLowerCase().replace(/[^a-z0-9-]/g, '_') + '.css';
        
        const currentYear = new Date().getFullYear();
        const yearsDifference = currentYear - efemerides[monthDay].year;
        
        switch (yearsDifference) {
            case 0:
                eventData = "¡Está pasando AHORA!: " + efemerides[monthDay].desc;
                break;
            case 1:
                eventData = "¡Primer Aniversario!: " + efemerides[monthDay].desc;
                break;
            default:
                eventData = "¡" + yearsDifference + " Aniversario!: " + efemerides[monthDay].desc;
                break;
        }
    }

    return cssFile;
}

function applyEfemeridesCSS() {
    const cssFile = getEfemeridesCSS();
    const linkElement = document.createElement('link');
    linkElement.rel = 'stylesheet';
    linkElement.href = `https://metsuke.com/assets/css/z_ef_${cssFile}`;
    document.head.appendChild(linkElement);

    if (eventData !== "") {
        const h2Element = document.querySelector('header h2');
        h2Element.textContent = eventData;
    }
}

document.addEventListener('DOMContentLoaded', applyEfemeridesCSS);
```

### Componente CSS Sobrescritura

El CSS se basa en sobrescrituras, donde se definen reglas base en la hoja principal y luego se modifican con selectores más específicos basados en las caracteristicas del evento. Incluye:
- **Hojas base:** Un CSS principal (como `styles.css`) que establece la "identidad fija" (colores neutros, diseños responsivos).
- **Sobrescrituras temáticas:** Reglas como `.tema-navidad { background: red !important; }` o selectores para elementos concretos.
- **Uso de !important:** Común para forzar cambios, lo que revela un manejo no óptimo de la cascada CSS.
- **Carga dinámica de CSS:** JS carga la hoja adicional (insertar `<link rel="stylesheet" href="/temas/pepepotamo.css">`).

Ejemplo de CSS:
```css
/* Base */
body {
  background-color: white;
  color: black;
}

/* Sobrescritura temática */
body {
  background-color: green !important;
  color: white;
}

header {
  background-image: url('/images/snow.jpg');
}
```

Esta arquitectura es sencilla y rápida de implementar, pero, como veremos, tiene varias limitaciones.

## Análisis Crítico: Fortalezas

Antes de centrarnos en los problemas, reconozcamos lo bueno del sistema actual:

1. **Simplicidad para prototipos:** JS + sobrescrituras CSS permiten cambios rápidos sin herramientas complejas. Perfecto para sitios pequeños como Metsuke.com en sus inicios.
2. **Compatibilidad amplia:** Funciona en la mayoría de navegadores modernos sin dependencias extras (salvo librerías de fechas).
3. **Flexibilidad inmediata:** JS reacciona en tiempo real a cambios de fecha (como a medianoche), actualizando el DOM sin recargar la página.
4. **Integración básica con accesibilidad:** Si se gestionan bien las clases, se mantienen atributos ARIA y el foco, aunque no es algo automático.

## Análisis Crítico: Limitaciones e Ineficiencias

Ahora, desgranemos los problemas, organizados por categorías.

### 1. Rendimiento

- **Carga inicial y FOUC:** JS se ejecuta tras cargar el DOM, lo que puede causar destellos si el CSS base no cubre todo. En Metsuke.com, con efemérides frecuentes, esto afecta a usuarios con conexiones lentas.
- **Sobrecarga de JS:** La lógica temporal consume recursos del cliente (CPU y memoria), sobre todo con polling o listeners. Un array con 365 efemérides crece y ralentiza el procesamiento.
- **Carga de recursos:** La carga dinámica aumentan peticiones HTTP, impactando métricas como TTFB o LCP (Core Web Vitals). Por ejemplo, cada tema con un fondo nuevo satura la caché.
- **Medición hipotética:** En un sitio similar, Lighthouse podría dar una puntuación baja en rendimiento (menos de 70/100) por JS/CSS que bloquean el renderizado.

### 2. Escalabilidad

- **Mantenibilidad del código:** Con más efemérides, el CSS se convierte en un lío de sobrescrituras. Añadir un tema nuevo implica editar varios archivos, con riesgo de conflictos si no se diseña correctamente la css.
- **Limitado a temas fijos:** Difícil de escalar a efemérides personalizadas o algorítmicas (como basadas en APIs externas). JS no maneja herencia temática fácilmente.
- **Crecimiento del sitio:** Metsuke.com podría expandirse con más páginas o interactivos. Sobrescrituras globales afectan todo, sin modularidad (temas por sección).
- **Problemas con SSR/SEO:** En frameworks como React o Next.js, JS del cliente no renderiza temas en el servidor, afectando a rastreadores y accesibilidad inicial. 
	- SIN EMBARGO esto es una característica de diseño ya que la web TIENE QUE SER puro HTML, JS y CSS, el resto de preprocesado se realiza ANTES de subir al servidor, mediante los algoritmos de automatización de MetsuOS

### 3. Mantenibilidad y Colaboración

- **Dependencia de JS para estilos:** Viola la separación de responsabilidades. Los estilos deberían ser declarativos en CSS, no imperativos en JS.
- **Exceso de !important:** Rompe la cascada natural de CSS, complicando el depurado (¿por qué no cambia este elemento?).
- **Falta de abstracción:** Sin variables (propiedades personalizadas) o preprocesadores, se repiten colores y tipografías, dificultando cambios globales.
- **Versionado:** En equipos, los merges de JS/CSS generan conflictos frecuentes.

### 4. Compatibilidad con Cambios Temáticos Frecuentes

- **Tematización efímera:** Efemérides diarias requieren sobrescrituras diarias, insostenible. Un cambio en "Día de la Mujer" podría alterar accidentalmente estilos de accesibilidad (como contraste).
- **Accesibilidad dinámica:** Las sobrescrituras pueden violar WCAG (ratios de contraste inferiores a 4.5:1 en temas oscuros). JS no valida automáticamente.
- **Responsividad:** Los temas podrían romper diseños móviles si no consideran media queries.
- **Problemas cross-browser:** Estilos inline de JS no siempre se aplican consistentemente (aunque IE es obsoleto en 2026).

### 5. Seguridad y Robustez

- **Vulnerabilidades en JS:** Riesgo de inyecciones si efemérides vienen de fuentes externas (XSS).
	- De ahi que las efemérides vengan ya implementadas en el propio JS, con un preprocesado previo de MetsuOS
- **Fallbacks:** Sin degradación elegante, si JS falla, el sitio queda en tema base, incoherente.
	- Al contrario, solo debe cambiar si todo va bien. De inconsistente NADA.
- **Pruebas:** Difícil automatizar tests para todos los temas y efemérides.

## Puntos de Mejora Propuestos

De esta auditoría surge la necesidad de una arquitectura más sólida:
1. **Migrar a preprocesadores como Sass:** Para modularidad, variables y mixins, reduciendo sobrescrituras.
	1. OK - Totalmente de acuerdo.
2. **Adoptar metodologías como ITCSS o BEM:** Para organizar la cascada y evitar conflictos.
3. **Usar propiedades personalizadas (CSS Variables):** Para inyecciones dinámicas sin tanto JS.
4. **Automatización:** Crear un generador de CSS desde JSON de efemérides (ver Módulo 7).
5. **Mejoras en accesibilidad:** Integrar validaciones automáticas (como axe-core en JS).
6. **Optimización:** Implementar Critical CSS, lazy loading y service workers para temas.
7. **Monitoreo:** Usar herramientas como Sentry o New Relic para errores en producción.

## Conclusión

Esta auditoría muestra que, aunque el sistema JS + sobrescrituras CSS de Metsuke.com funciona para un sitio modesto, sus limitaciones en rendimiento, escalabilidad y mantenimiento lo hacen poco adecuado para una tematización efímera avanzada en 2026. Hemos identificado ineficiencias clave que afectan la usabilidad y accesibilidad, preparando el terreno para mejoras en el curso. En la próxima lección, exploraremos la "Estructura Inmune" para resolver estos retos.

## Referencias que Apoyan el Contenido

1. [OpenWebinars. (2019). Qué es Sass: ventajas, desventajas y ejemplos de desarrollo 🟡③🌐](https://openwebinars.net/blog/que-es-sass-ventajas-desventajas-y-ejemplos-de-desarrollo/) .- Artículo que explora las características de Sass, sus beneficios en la mantenibilidad del código y ejemplos prácticos de implementación.
2. [DEV Community. (2023). ITCSS - Arquitectura CSS 🟡③🌐](https://dev.to/ignacio_cuadra/itcss-arquitectura-css-3p4b) .- Guía sobre la arquitectura Inverted Triangle CSS (ITCSS), detallando su jerarquía para gestionar la especificidad y escalabilidad.
3. [Arsys. (2024). BEM: guía completa para CSS modular con ejemplos 🟡③🌐](https://www.arsys.es/blog/bem-guia-completa-para-css-modular-con-ejemplos) .- Manual detallado sobre la metodología Block Element Modifier para la creación de componentes CSS independientes y reutilizables.
4. [Smashing Magazine. (2024). !important CSS Declarations: How and When to Use Them 🟡③🌐](https://www.smashingmagazine.com/2010/11/the-important-css-declaration-how-and-when-to-use-it/) .- Reflexión crítica sobre el uso de la declaración !important, sus implicaciones en la cascada y las mejores prácticas para evitarla.
5. [MDN Web Docs. (2025). Rendimiento web 🟡③🌐](https://developer.mozilla.org/es/docs/Learn_web_development/Extensions/Performance) .- Documentación oficial que aborda estrategias de optimización para reducir tiempos de carga y mejorar la interactividad en aplicaciones web.
6. [YouTube. (2022). Curso de SASS CSS: TUTORIAL en ESPAÑOL 2022 Aprende SASS 🟡③🌐](https://www.youtube.com/playlist?list=PLJpymL0goBgFAUYDei7CoJCiHjcmgioUt) .- Lista de reproducción con formación práctica sobre el preprocesador Sass, cubriendo desde conceptos básicos hasta funciones avanzadas.
## Referencias que Refutan el Contenido

1. [InnovaSpain. (2024). *Conoce las 10 ventajas de emplear JavaScript* 🟡③🌐](https://www.innovaspain.com/10-ventajas-emplear-javascript/) .- Artículo que analiza los beneficios clave de JavaScript, como su versatilidad, escalabilidad y la capacidad de crear interfaces dinámicas y flexibles en el desarrollo web.
2. [Integra Sistemas. (s.f.). *Uso de !important en CSS* 🟡③🌐](https://www.integrasistemas.es/blog/general/uso-de-important-en-css/) .- Explicación técnica sobre la declaración !important en CSS, detallando su función para forzar la prioridad de una regla sobre la cascada natural de estilos.
3. [EngineYard. (s.f.). *Inline Styles: Yes or No?* 🟡③🌐](https://www.engineyard.com/blog/inline-styles-yes-or-no/) .- Análisis sobre el uso de estilos en línea en el desarrollo moderno de componentes, evaluando sus ventajas en especificidad y las razones por las que algunos desarrolladores los prefieren.
4. [AWS. (s.f.). *¿Qué es JavaScript?* 🟡③🌐](https://aws.amazon.com/es/what-is/javascript/) .- Guía fundamental de Amazon Web Services que define JavaScript, explicando su funcionamiento tanto en el lado del cliente como en el servidor y su importancia en la web interactiva.
5. [YouTube. (2008). *Fix your Flash of Unstyled Content FOUC* 🟡③🌐](https://www.youtube.com/watch?v=WGZ26ktyG6o) .- Video tutorial que presenta soluciones prácticas para evitar el Flash of Unstyled Content (FOUC), mejorando la percepción de carga y la experiencia de usuario.


![[Plantilla - 1MT#One More Thing]]
