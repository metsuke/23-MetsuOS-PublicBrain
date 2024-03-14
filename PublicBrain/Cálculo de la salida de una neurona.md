---
iaStatus: 0
iaStatus: 0
a11y: 0
checked: 0
lang: ES
translations: 
created: 2023-12-28T22:17:33.347Z
modified: 2024-03-13T14:33:29.781Z
ver_major: 0
ver_minor: 1
ver_rev: 21
nav_primary: []
nav_secondary: []
tags: []
---
# Cálculo de la salida de una neurona

[[Estructura y funcionamiento de las  redes neuronales]]

### Cálculo de la salida de una neurona en una red neuronal

Supongamos que tienes una neurona con \(n\) entradas \(x_1, x_2, \ldots, x_n\) y pesos correspondientes \(w_1, w_2, \ldots, w_n\). La salida \(y\) de la neurona se calcula de la siguiente manera:

1. **Combinación lineal de entradas ponderadas:**
   $$
   z = w_1 \cdot x_1 + w_2 \cdot x_2 + \ldots + w_n \cdot x_n
   $$

2. **Aplicación de la función de activación:**
   $$
   y = f(z)
   $$

   Donde \(f(\cdot)\) es la función de activación. La función de activación introduce no linealidades en la red, permitiendo que la red aprenda patrones complejos y no solo combinaciones lineales de las entradas.

### Ejemplo con una función de activación sigmoide:

La función de activación sigmoide es comúnmente utilizada en redes neuronales:
$$
f(z) = \frac{1}{1 + e^{-z}}
$$

Entonces, el cálculo completo sería:
$$
y = \frac{1}{1 + e^{-(w_1 \cdot x_1 + w_2 \cdot x_2 + \ldots + w_n \cdot x_n)}}
$$

En resumen, la neurona realiza una combinación ponderada de las entradas, pasa ese valor a través de una función de activación y produce una salida. Este proceso se repite para cada neurona en la red, y las salidas de las neuronas se utilizan como entradas para las capas subsiguientes en una red neuronal. Este tipo de arquitectura permite que la red aprenda representaciones complejas y no lineales de los datos.
