---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-13T12:55:20.984Z
modified: 2024-04-13T12:56:27.197Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# Uso de filtros predefinidos en PixiJS

[[Aprender sobre PixiJS]]

¡Claro! En PixiJS, los filtros predefinidos son una característica poderosa que te permite aplicar efectos visuales a tus elementos de visualización. Estos filtros son efectos listos para usar que puedes aplicar a sprites, texturas o contenedores para lograr diferentes efectos estéticos en tu aplicación o juego.

Aquí te muestro cómo puedes usar filtros predefinidos en PixiJS:

1. **Importar PixiJS y los filtros predefinidos**: Asegúrate de incluir PixiJS en tu proyecto y los módulos de filtros que deseas utilizar. Puedes importar filtros específicos según tus necesidades, por ejemplo:

```javascript
import * as PIXI from 'pixi.js';
import { BlurFilter } from 'pixi-filters';
```

2. **Crear un filtro y aplicarlo a un objeto**: Una vez que has importado el filtro deseado, puedes crear una instancia de ese filtro y aplicarlo a cualquier sprite, textura o contenedor en tu escena. Por ejemplo, para aplicar un filtro de desenfoque (BlurFilter) a un sprite:

```javascript
const sprite = PIXI.Sprite.from('imagen.png');
const blurFilter = new PIXI.filters.BlurFilter();
sprite.filters = [blurFilter];
```

3. **Configurar opciones del filtro (opcional)**: Algunos filtros pueden tener parámetros adicionales que puedes ajustar para controlar el efecto visual. Por ejemplo, con el filtro de desenfoque, puedes configurar el radio de desenfoque:

```javascript
blurFilter.blur = 5; // Ajusta el radio de desenfoque
```

4. **Actualizar el filtro (opcional)**: Si cambias las propiedades del filtro después de aplicarlo a un objeto, es posible que necesites llamar al método `update` del objeto contenedor para reflejar los cambios en la pantalla:

```javascript
sprite.update(); // Actualiza el sprite para aplicar los cambios en el filtro
```

5. **Eliminar el filtro (opcional)**: Si deseas eliminar un filtro de un objeto, simplemente asigna un arreglo vacío a la propiedad `filters` del objeto:

```javascript
sprite.filters = []; // Elimina todos los filtros del sprite
```

Los filtros predefinidos en PixiJS son una manera poderosa de agregar efectos visuales interesantes a tus proyectos de forma rápida y sencilla. Puedes experimentar con diferentes filtros y ajustar sus parámetros para lograr el efecto deseado en tus aplicaciones o juegos.