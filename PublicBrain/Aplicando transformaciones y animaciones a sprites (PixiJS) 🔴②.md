---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo, llama3-70b-8192
iaStatus_Generado: I
iaStatus_Supervisado: H
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-08T04:04:45.556Z
modified: 2024-05-25T21:02:46.522Z
supervisado: 2024-05-25T21:02:46.522Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 5
nav_primary: 
nav_secondary: 
tags:
---
# Aplicando transformaciones y animaciones a sprites (PixiJS) 🔴②

[[Aprender sobre PixiJS ⚫①]]

En PixiJS, puedes aplicar transformaciones y animaciones a sprites para crear efectos visuales dinámicos y atractivos en tus aplicaciones y juegos web. A continuación, te presento una explicación detallada de cómo hacerlo.

## 1. Transformaciones de Sprite

PixiJS proporciona métodos para aplicar transformaciones como traslación, rotación y escala a sprites. Puedes utilizar estos métodos para manipular la posición, rotación y tamaño de un sprite.

* **Traslación (posición):** Utiliza la propiedad `sprite.x` y `sprite.y` para cambiar la posición del sprite en el lienzo.
```javascript
sprite.x = 100; // Nueva posición en el eje X
sprite.y = 200; // Nueva posición en el eje Y
```
* **Rotación:** Utiliza la propiedad `sprite.rotation` para aplicar una rotación al sprite, medida en radianes.
```javascript
sprite.rotation = Math.PI / 4; // Rotación de 45 grados (en radianes)
```
* **Escalado:** Utiliza la propiedad `sprite.scale.x` y `sprite.scale.y` para cambiar la escala del sprite en los ejes X e Y.
```javascript
sprite.scale.x = 2; // Doble tamaño en el eje X
sprite.scale.y = 2; // Doble tamaño en el eje Y
```

## 2. Animaciones de Sprite

PixiJS también te permite crear animaciones fluidas en sprites mediante la modificación de sus propiedades en el tiempo. Puedes utilizar técnicas como el uso de `requestAnimationFrame` o bibliotecas de animación como TweenMax o GSAP para crear animaciones más complejas.

* **Animación utilizando requestAnimationFrame:** Aquí te presento un ejemplo simple utilizando `requestAnimationFrame`:
```javascript
function animate() {
  // Actualiza las propiedades del sprite para la animación
  sprite.rotation += 0.1; // Rotación gradual

  // Renderiza la escena
  renderer.render(stage);

  // Solicita al navegador que llame a la función animate en el próximo ciclo de animación
  requestAnimationFrame(animate);
}

// Comienza la animación
animate();
```

## 3. Uso de Tweening para Animaciones

También puedes utilizar bibliotecas como TweenMax o GSAP para crear animaciones más complejas y controladas. Estas bibliotecas te permiten definir animaciones con precisión y aplicar efectos como movimiento suave, interpolación de valores y secuencias de animación.

* **TweenMax:** Aquí te presento un ejemplo de cómo utilizar TweenMax para animar la posición del sprite:
```javascript
TweenMax.to(sprite.position, 2, { x: 300, y: 200, ease: Power2.easeInOut });
```

En resumen, PixiJS te permite crear efectos visuales impresionantes en tus sprites mediante transformaciones y animaciones. Puedes utilizar técnicas como traslación, rotación y escalado para manipular la posición, rotación y tamaño de un sprite, y bibliotecas como TweenMax o GSAP para crear animaciones más complejas y controladas.

## Referencias bibliográficas

* PixiJS Documentation: [Transformations](https://pixijs.com/docs/#/en/transforms)
* PixiJS Documentation: [Animations](https://pixijs.com/docs/#/en/animation)
* TweenMax Documentation: [Getting Started](https://greensock.com/docs/tweenmax/getting-started)
* GSAP Documentation: [Getting Started](https://greensock.com/docs/gsap/getting-started)

## Referencias que refutan

* "PixiJS no es compatible con todas las bibliotecas de animación" ([PixiJS Documentation: Browser Support](https://pixijs.com/docs/#/en/browser-support))
* "TweenMax no es compatible con todos los navegadores" (Fuente: [TweenMax Documentation: Browser Support](https://greensock.com/docs/tweenmax/browser-support))

