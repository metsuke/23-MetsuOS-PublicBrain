---
iaStatus: 8
iaStatus_Model: ""
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.463Z
modified: 2024-05-04T20:36:22.050Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 27
nav_primary: 
nav_secondary: 
tags:
---
# Funciones de activación comunes (Sigmoid, ReLU, Tanh)

[[Estructura y funcionamiento de las  redes neuronales ⚫①]]

Las funciones de activación son componentes fundamentales en las redes neuronales artificiales, ya que permiten introducir no linealidades en el modelo, lo que le da la capacidad de aprender y modelar relaciones complejas en los datos. Algunas de las funciones de activación más comunes son:

1. **Función Sigmoid**: También conocida como función logística, esta función toma un valor real como entrada y lo transforma a un rango entre 0 y 1. Su fórmula matemática es: 
\[ \sigma(x) = rac{1}{1 + e^{-x}} \]
La función sigmoid es utilizada comúnmente en capas de salida de modelos de clasificación binaria.

2. **Función ReLU (Rectified Linear Unit)**: Esta función activación toma un valor de entrada y retorna cero si el valor es negativo, o el mismo valor si es positivo. Su fórmula es:
\[ f(x) = \max(0, x) \]
La función ReLU y sus variantes (como Leaky ReLU, Parametric ReLU, etc.) son ampliamente utilizadas en redes neuronales profundas, ya que han demostrado acelerar el proceso de entrenamiento y evitar el problema de desvanecimiento del gradiente.

3. **Función Tanh (Tangente Hiperbólica)**: Esta función activación es similar a la función sigmoid, pero su rango va de -1 a 1. Su fórmula es:
\[ 	anh(x) = rac{e^x - e^{-x}}{e^x + e^{-x}} \]
La función tanh es comúnmente utilizada en capas ocultas de una red neuronal, ya que su salida está centrada en cero, lo que puede facilitar el proceso de optimización.

Estas son solo algunas de las funciones de activación comunes en redes neuronales. La elección de la función de activación adecuada dependerá del problema que se esté tratando de resolver y de la arquitectura de la red neuronal que se esté utilizando.
