---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:48:59.469Z
modified: 2024-04-06T23:49:42.122Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 24
nav_primary: []
nav_secondary: []
tags: []
---
# Función de activación

[[Estructura y funcionamiento de las  redes neuronales]]

En el contexto de las redes neuronales en inteligencia artificial, la función de activación es un componente clave que se utiliza para introducir no linealidades en el modelo. Estas funciones son aplicadas a la salida de cada neurona en la red y juegan un papel crucial en la capacidad de la red para aprender y modelar relaciones complejas en los datos. Aquí hay información sobre las funciones de activación comunes:

1. **Función Sigmoide (Logística):**
   - **Fórmula:** \( \sigma(x) = \frac{1}{1 + e^{-x}} \)
   - **Rango de Salida:** (0, 1)
   - **Características:**
     - Utilizada comúnmente en la capa de salida de una red neuronal para problemas de clasificación binaria.
     - Mapea cualquier valor real a un rango entre 0 y 1, lo que puede interpretarse como una probabilidad.

2. **Función Tangente Hiperbólica (tanh):**
   - **Fórmula:** \( \tanh(x) = \frac{e^{x} - e^{-x}}{e^{x} + e^{-x}} \)
   - **Rango de Salida:** (-1, 1)
   - **Características:**
     - Similar a la función sigmoide, pero con un rango de salida entre -1 y 1.
     - Puede ayudar a mitigar el problema de la "desaparición del gradiente" en comparación con la sigmoide.

3. **Rectified Linear Unit (ReLU):**
   - **Fórmula:** \( f(x) = \max(0, x) \)
   - **Rango de Salida:** [0, +∞)
   - **Características:**
     - Una de las funciones de activación más utilizadas.
     - Introduce no linealidades permitiendo que solo los valores positivos pasen, mientras que los valores negativos se vuelven cero.
     - Puede ayudar a acelerar el proceso de entrenamiento.

4. **Leaky ReLU:**
   - **Fórmula:** \( f(x) = \max(\alpha x, x) \), donde \(\alpha\) es un pequeño valor positivo.
   - **Rango de Salida:** \((-\infty, +\infty)\)
   - **Características:**
     - Similar a ReLU, pero permite un pequeño valor negativo (\(\alpha x\)) para los valores negativos de entrada.
     - Diseñada para abordar el problema de "neuronas muertas" que pueden ocurrir en ReLU cuando la salida es siempre cero para algunos valores.

5. **Función de Unidad Lineal Rectificada (ReLU Paramétrica - PReLU):**
   - **Fórmula:** \( f(x) = \max(\alpha x, x) \), donde \(\alpha\) es un parámetro aprendido.
   - **Rango de Salida:** \((-\infty, +\infty)\)
   - **Características:**
     - Similar a Leaky ReLU, pero \(\alpha\) es un parámetro que se aprende durante el entrenamiento en lugar de ser predefinido.

Estas son solo algunas de las funciones de activación comunes. La elección de la función de activación puede depender del problema específico, la arquitectura de la red y las propiedades de los datos. Experimentar con diferentes funciones de activación es una parte esencial del ajuste fino de modelos de redes neuronales.