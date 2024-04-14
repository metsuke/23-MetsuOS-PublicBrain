---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-07T07:33:01.572Z
modified: 2024-04-14T14:29:03.211Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 2
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
---
# Variational Autoencoders (VAEs)

[[Estructura y funcionamiento de las  redes neuronales]]

Los Variational Autoencoders (VAEs) son un tipo de modelo generativo en el campo de la inteligencia artificial que se utiliza para aprender la distribución de datos de entrada complejos y generar nuevas muestras similares a los datos de entrada. 

Un VAE es una combinación de un autoencoder y un modelo probabilístico que se basa en la teoría de probabilidad para generar nuevas muestras de datos. En un VAE, la capa central del modelo aprende una distribución latente de los datos de entrada, lo que permite al modelo generar muestras de datos similares pero no idénticas a los datos de entrenamiento.

Para entrenar un VAE, se minimiza una función de pérdida que consta de dos términos: el término de reconstrucción que mide la capacidad del modelo para reconstruir los datos de entrada, y el término de divergencia KL (Kullback-Leibler) que mide la diferencia entre la distribución latente aprendida por el modelo y una distribución de referencia, generalmente una distribución normal estándar.

Los VAEs son especialmente útiles en problemas de generación de imágenes y datos complejos, como la generación de caras de personas o la creación de nuevos diseños de ropa. Al aprender una distribución latente de los datos de entrada, los VAEs pueden capturar las características intrínsecas de los datos y generar muestras nuevas y realistas de manera probabilística.

En resumen, los Variational Autoencoders son un tipo de modelo generativo en inteligencia artificial que combina la capacidad de reconstrucción de un autoencoder con la interpretación probabilística de una distribución latente, lo que los hace útiles para la generación de datos complejos y realistas.
