---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2025-09-02T12:18:54.777Z
modified: 2025-09-02T12:34:16.433Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 1
nav_primary: []
nav_secondary: []
tags: []
---
# MinioQuest - Modo Radastan en ZX Spectrum- Máquinas Soportadas ⚫①

[[PublicBrain/Index|Index]]

El **Modo Radastan** es un modo gráfico no estándar para el ZX Spectrum, que ofrece una resolución de **128x96 píxeles** con **16 colores por píxel**, evitando el problema del *attribute clash* típico del ZX Spectrum original. Este modo fue desarrollado específicamente para ciertas máquinas modernas basadas en FPGA que emulan o reimplementan el hardware del ZX Spectrum. A continuación, se detallan las máquinas que soportan el Modo Radastan, junto con notas relevantes.

---

## Máquinas que soportan el Modo Radastan

### 1. ZX-Uno
- **Descripción**: Clon del ZX Spectrum basado en FPGA, diseñado para implementar el hardware del Spectrum con precisión, pero con características adicionales como el Modo Radastan.
- **Soporte**: El Modo Radastan es **exclusivo** y nativo del ZX-Uno, activado mediante registros específicos (como el registro `RADASCTRL`).
- **Configuración**: 
  - Usa la paleta ULAplus.
  - Comandos: `port_out(48955, 64)` para activar ULAplus y `port_out(65339, 3)` para habilitar el Modo Radastan.
- **Detalles**: Es la máquina principal asociada con este modo gráfico, ofreciendo una implementación directa y optimizada.
- **Referencias**:
  - [ZX-Uno FAQ](https://uto.speccy.org/zxunofaq.html)
  - [Verkami ZX-Uno](https://www.verkami.com/projects/14074-zx-uno)

### 2. ZX Spectrum Next
- **Descripción**: Máquina moderna basada en FPGA que extiende las capacidades del ZX Spectrum.
- **Soporte**: No soporta el Modo Radastan de forma nativa, pero puede ejecutar demos y programas en este modo mediante adaptaciones, gracias a las similitudes con el hardware FPGA del ZX-Uno.
- **Detalles**: Los desarrolladores han adaptado contenido para que funcione en el Next, normalmente usando el modo **Layer 2** con ajustes para emular la resolución y paleta del Modo Radastan.
- **Referencias**:
  - [ZX-Uno Forum](https://www.zxuno.com/forum/viewtopic.php?t=561)
  - [Xataka: ZX Spectrum Next Review](https://www.xataka.com/analisis/zx-spectrum-next-dispositivo-revival-definitivo-he-probado-merece-cada-euro-que-cuesta)

### 3. ZX Evolution
- **Descripción**: Clon ruso del ZX Spectrum basado en FPGA.
- **Soporte**: Ofrece un modo gráfico similar al Modo Radastan, aunque con diferencias (resolución hasta 512x512 píxeles con un viewport de 320x200 y más memoria para gráficos).
- **Detalles**: No es idéntico al Modo Radastan, pero puede soportar contenido similar con las configuraciones adecuadas.
- **Referencias**:
  - [Speccy.org Forum](https://foro.speccy.org/viewtopic.php?f=8&t=4191)

### 4. Otras implementaciones basadas en FPGA
- **Descripción**: Proyectos derivados del ZX-Uno, como **gomaDOS+**, u otras máquinas modernas que reimplementan el ZX Spectrum mediante FPGA.
- **Soporte**: Pueden soportar el Modo Radastan o modos similares si el núcleo FPGA está configurado adecuadamente.
- **Detalles**: La compatibilidad depende de la implementación específica del hardware.
- **Referencias**:
  - [Xataka: ZX Spectrum Next Review](https://www.xataka.com/analisis/zx-spectrum-next-dispositivo-revival-definitivo-he-probado-merece-cada-euro-que-cuesta)

---

## Notas importantes
- **Sinclair Vega**: **No soporta** el Modo Radastan, ya que su emulación no permite cambios dinámicos en la paleta de colores durante la generación de la imagen.
  - [Wikipedia: Modos gráficos del ZX Spectrum](https://es.wikipedia.org/wiki/Modos_gr%25C3%25A1ficos_del_ZX_Spectrum)
- **ZX Spectrum SE / Chloe 280SE**: Pueden soportar modos gráficos avanzados, pero no hay evidencia concluyente de soporte específico para el Modo Radastan.
  - [Wikipedia: Modos gráficos del ZX Spectrum](https://es.wikipedia.org/wiki/Modos_gr%25C3%25A1ficos_del_ZX_Spectrum)
- **Configuración técnica del Modo Radastan**:
  - Requiere la paleta **ULAplus**.
  - Comandos específicos en el ZX-Uno: `port_out(48955, 64)` y `port_out(65339, 3)` para activar el modo.
  - [ZX-Uno FAQ](https://uto.speccy.org/zxunofaq.html)

---

## Resumen
- **ZX-Uno**: Máquina principal con soporte **nativo** para el Modo Radastan, ideal para desarrollos enfocados en este modo.
- **ZX Spectrum Next**: Soporte **parcial** mediante emulación en el modo Layer 2, requiere adaptaciones.
- **ZX Evolution**: Soporte **similar** con modos gráficos comparables, pero no idéntico.
- **Otras FPGA**: Compatibilidad variable según la implementación.
- **No compatibles**: Sinclair Vega, ZX Spectrum SE, Chloe 280SE (sin evidencia clara).

**Referencias principales**:
- [ZX-Uno FAQ](https://uto.speccy.org/zxunofaq.html)
- [ZX-Uno Forum](https://www.zxuno.com/forum/viewtopic.php?t=561)
- [Speccy.org Forum](https://foro.speccy.org/viewtopic.php?f=8&t=4191)
- [Wikipedia: Modos gráficos del ZX Spectrum](https://es.wikipedia.org/wiki/Modos_gr%25C3%25A1ficos_del_ZX_Spectrum)


![[Plantilla - 1MT#One More Thing]]