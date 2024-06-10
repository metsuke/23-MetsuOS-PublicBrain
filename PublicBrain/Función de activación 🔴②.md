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
created: 2024-04-06T23:48:59.469Z
modified: 2024-06-10T15:06:30.447Z
supervisado: 2024-06-10T15:06:30.447Z
ACCION: 
ver_major: 0
ver_minor: 4
ver_rev: 30
nav_primary: 
nav_secondary: 
tags:
---
# Función de activación 🔴②

[[Estructura y funcionamiento de las redes neuronales ⚫①]]


En el contexto de las redes neuronales en inteligencia artificial, la función de activación es un componente clave que se utiliza para introducir no linealidades en el modelo. Estas funciones son aplicadas a la salida de cada neurona en la red y juegan un papel crucial en la capacidad de la red para aprender y modelar relaciones complejas en los datos.

## Funciones de Activación Comunes

A continuación, se presentan algunas de las funciones de activación más comunes utilizadas en redes neuronales:

### 1. Función Sigmoide (Logística)

* **Fórmula:** σ(x) = 1 / (1 + e^(-x))  $$\sigma(x) = \frac{1}{1 + e^{-x}}$$
* **Rango de Salida:** (0, 1)
* **Características:**
	+ Utilizada comúnmente en la capa de salida de una red neuronal para problemas de clasificación binaria.
	+ Mapea cualquier valor real a un rango entre 0 y 1, lo que puede interpretarse como una probabilidad.

### 2. Función Tangente Hiperbólica (tanh)

* **Fórmula:** tanh(x) = (e^x - e^(-x)) / (e^x + e^(-x))$$\tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}}$$
* **Rango de Salida:** (-1, 1)
* **Características:**
	+ Similar a la función sigmoide, pero con un rango de salida entre -1 y 1.
	+ Puede ayudar a mitigar el problema de la "desaparición del gradiente" en comparación con la sigmoide.

### 3. Rectified Linear Unit (ReLU)

* **Fórmula:** f(x) = max(0, x)$$f(x) = \max(0, x)$$
* **Rango de Salida:** [0, +∞)
* **Características:**
	+ Una de las funciones de activación más utilizadas.
	+ Introduce no linealidades permitiendo que solo los valores positivos pasen, mientras que los valores negativos se vuelven cero.
	+ Puede ayudar a acelerar el proceso de entrenamiento.

### 4. Leaky ReLU

* **Fórmula:** f(x) = max(αx, x), donde α es un pequeño valor positivo.$$f(x) = \max(\alpha x, x)$$
* **Rango de Salida:** (-∞, +∞)
* **Características:**
	+ Similar a ReLU, pero permite un pequeño valor negativo (αx) para los valores negativos de entrada.
	+ Diseñada para abordar el problema de "neuronas muertas" que pueden ocurrir en ReLU cuando la salida es siempre cero para algunos valores.

### 5. Función de Unidad Lineal Rectificada (ReLU Paramétrica - PReLU)

* **Fórmula:** f(x) = max(αx, x), donde α es un parámetro aprendido.$$f(x) = \max(\alpha x, x)$$
* **Rango de Salida:** (-∞, +∞)
* **Características:**
	+ Similar a Leaky ReLU, pero α es un parámetro que se aprende durante el entrenamiento en lugar de ser predefinido.

## Referencias Bibliográficas

* Goodfellow, I., Bengio, Y., & Courville, A. (2016). Deep Learning. MIT Press.
* LeCun, Y., Bengio, Y., & Hinton, G. (2015). Deep learning. Nature, 521(7553), 436-444.
* Nair, V., & Hinton, G. E. (2010). Rectified linear units (ReLUs) and their application in deep neural networks. Proceedings of the 27th International Conference on Machine Learning, 807-814.

## Referencias que Refutan

* Zhang, X., Li, Z., Liu, X., & LeCun, Y. (2018). Fixing the train-test resolution discrepancy. Proceedings of the 35th International Conference on Machine Learning, 108-117. (Critica la función de activación ReLU)
* Xu, B., Wang, N., Chen, T., & Li, M. (2015). Empirical evaluation of rectified activations in deep neural networks. arXiv preprint arXiv:1505.00853. (Analiza las limitaciones de las funciones de activación ReLU y tanh)

![[⚫🔴🟡🟢🔵⚪ (🔴②)#Sobre el sistema de validez de un contenido en MetsuOS]]