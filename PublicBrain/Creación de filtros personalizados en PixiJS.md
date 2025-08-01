---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-13T12:56:20.325Z
modified: 2025-06-10T21:14:03.693Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 5
nav_primary: []
nav_secondary: []
tags: []
---
# Creación de filtros personalizados en PixiJS

[[Curso de PixiJS ⚫①]]

¡Claro! Crear filtros personalizados en PixiJS te permite llevar tus efectos visuales al siguiente nivel al permitirte definir tus propios efectos específicos. Aquí tienes los pasos básicos para crear tus propios filtros personalizados en PixiJS:

1. **Extender la clase Filter**: En PixiJS, los filtros son clases que extienden la clase base `PIXI.Filter`. Por lo tanto, para crear un filtro personalizado, primero debes definir una nueva clase que extienda `PIXI.Filter`.

```javascript
class MiFiltroPersonalizado extends PIXI.Filter {
    constructor(fragmentSource, uniforms) {
        super(null, fragmentSource, uniforms);
    }
}
```

2. **Definir el shader del filtro**: El shader es el programa de procesamiento de gráficos que se ejecuta en la GPU para aplicar el efecto deseado. Puedes escribir el código del shader en lenguaje GLSL (OpenGL Shading Language). El shader consta de dos partes: el vertex shader y el fragment shader. El fragment shader es donde se realiza la mayor parte del procesamiento.

```javascript
const fragmentShader = `
    precision mediump float;
    varying vec2 vTextureCoord;
    uniform sampler2D uSampler;
    
    void main(void) {
        vec4 color = texture2D(uSampler, vTextureCoord);
        // Aplicar tu efecto personalizado aquí
        gl_FragColor = color;
    }
`;
```

3. **Inicializar el filtro personalizado**: En el constructor de tu clase de filtro personalizado, debes llamar al constructor de la clase base `PIXI.Filter` y pasarle el código del vertex shader, el fragment shader y cualquier uniforme adicional que necesites.

```javascript
class MiFiltroPersonalizado extends PIXI.Filter {
    constructor(uniforms) {
        super(null, fragmentShader, uniforms);
    }
}
```

4. **Aplicar el filtro a un objeto**: Una vez que hayas definido tu filtro personalizado, puedes crear una instancia de él y aplicarlo a cualquier sprite, textura o contenedor en tu escena.

```javascript
const sprite = PIXI.Sprite.from('imagen.png');
const miFiltro = new MiFiltroPersonalizado({
    // Define los uniformes necesarios para tu filtro, si los hay
});
sprite.filters = [miFiltro];
```

5. **Actualizar el filtro (opcional)**: Al igual que con los filtros predefinidos, si cambias las propiedades del filtro personalizado después de aplicarlo a un objeto, es posible que necesites llamar al método `update` del objeto contenedor para reflejar los cambios en la pantalla.

```javascript
sprite.update(); // Actualiza el sprite para aplicar los cambios en el filtro
```

Crear filtros personalizados te brinda una gran flexibilidad para implementar efectos visuales únicos y creativos en tus proyectos de PixiJS. Puedes experimentar con diferentes técnicas en el shader para lograr el efecto deseado.