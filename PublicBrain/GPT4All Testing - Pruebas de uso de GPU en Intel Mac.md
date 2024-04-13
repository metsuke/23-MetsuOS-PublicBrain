---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:49:00.624Z
modified: 2024-04-13T11:45:39.616Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 5
nav_primary: []
nav_secondary: []
tags: []
---
# GPT4All Testing - Pruebas de uso de GPU en Intel Mac

[[GPT4All Testing]]

Veremos si lo acaban incorporando y en que condiciones. De nuevo, como en otros muchos proyectos OS, resulta irritante la mania de los devs de decidir por el usuario si usar determinada opcion, se deberia poner y punto que cada cual decida, como mínimo (incluso a igualdad de rendimiento), a que procesador manda que...

En todo caso, hora de abrir una linea de trabajo para implementar un equivalente a bajo nivel de GPT4All para su ejecución por linea de comandos y que haga uso de lo disponible en cada plataforma, incluso ejecutando modelos agregando CPU+GPU si es posible.

[[MosGPT project]] iniciado.

* [Feature Support Vulkan on Intel Macs · Issue #2114 · nomic-ai/gpt4all · GitHub](https://github.com/nomic-ai/gpt4all/issues/2114)
* [Tools | Vulkan | Cross platform 3D Graphics](https://www.vulkan.org/tools#vulkan-gpu-resources)
* [How To Check if Your GPU Driver Supports Vulkan | DeviceTests](https://devicetests.com/check-gpu-driver-supports-vulkan)
* [Reports for AMD Radeon Pro 580X - Vulkan Hardware Database by Sascha Willems (gpuinfo.org)](https://vulkan.gpuinfo.org/listreports.php?devicename=AMD+Radeon+Pro+580X&platform=macos)
