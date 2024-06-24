---
iaStatus: 8
iaStatus_Model: gpt-3.5-turbo, llama3-70b-8192
iaStatus_Generado: "I"
iaStatus_Supervisado: "H"
iaStatus_Validado: "-"
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:49:00.594Z
modified: 2024-06-24T19:46:59.638Z
supervisado: ""
ACCION: S
ver_major: 0
ver_minor: 2
ver_rev: 29
nav_primary: 
nav_secondary: 
tags:
---
# Pesos y bias (Redes Neuronales) 🔴②

[[Estructura y funcionamiento de las redes neuronales ⚫①]]

## Introducción

En el contexto de las redes neuronales artificiales, los pesos y los bias son parámetros fundamentales que permiten a la red aprender y adaptarse a los datos de entrada. Estos parámetros ajustables son clave para determinar el comportamiento de la red y permiten que ésta haga predicciones o tome decisiones precisas.

## Los Pesos

Los pesos son valores numéricos asociados a las conexiones entre las neuronas. Cada neurona de una capa está conectada con todas las neuronas de la capa anterior (o de la entrada en el caso de la primera capa). Los pesos determinan la influencia y el nivel de importancia de cada conexión en la propagación de la información a través de la red. Al ajustar los pesos, se busca que la red pueda aprender y adaptarse a los datos de entrada de manera óptima.

## El Bias (Sesgo)

El bias (o sesgo) es un parámetro adicional asociado a cada neurona, que se suma a la entrada ponderada de dicha neurona antes de aplicar la función de activación. El bias permite ajustar la salida de la neurona en función de una cantidad constante. Esto es útil cuando los datos de entrada no están centrados alrededor de cero o cuando se necesita introducir algún sesgo en la salida de la neurona.

## Resumen

En resumen, los pesos y los bias son parámetros ajustables que permiten que una red neuronal aprenda a hacer predicciones o tomar decisiones en función de los datos de entrada. Mediante la adaptación de estos parámetros, la red busca encontrar un conjunto óptimo de conexiones y generar salidas que se ajusten a los datos de entrenamiento.

## Referencias Bibliográficas que Apoyan el contenido

* Goodfellow, I., Bengio, Y., & Courville, A. (2016). Deep Learning. MIT Press. (Capítulo 3: Neural Networks)
* Haykin, S. (2009). Neural Networks and Learning Machines. Prentice Hall. (Capítulo 2: Artificial Neural Networks)

## Referencias Bibliográficas que Refutan el contenido

* Zhang, C., Bengio, S., Hardt, M., Recht, B., & Vinyals, O. (2016). Understanding deep learning requires rethinking generalization. ICLR 2017. (Cuestiona la importancia de los pesos y bias en la generalización de las redes neuronales)
* Raghu, M., Poole, B., Kleinberg, J., Sohl-Dickstein, J., & Ganguli, S. (2017). On the expressive power of deep neural networks. ICML 2017. (Discute la relación entre los pesos y bias y la capacidad de expresión de las redes neuronales)


![[⚫🔴🟡🟢🔵⚪ (🔴②)#Sobre el sistema de validez de un contenido en MetsuOS]]
