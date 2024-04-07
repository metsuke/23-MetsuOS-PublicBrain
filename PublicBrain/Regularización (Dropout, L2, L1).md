---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-04-06T23:49:00.640Z
modified: 2024-04-06T23:49:41.691Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 3
nav_primary: []
nav_secondary: []
tags: []
---
# Regularización (Dropout, L2, L1)

[[Estructura y funcionamiento de las  redes neuronales]]

La regularización en el contexto de las redes neuronales en inteligencia artificial es una técnica utilizada para prevenir el sobreajuste (overfitting) del modelo a los datos de entrenamiento. El sobreajuste ocurre cuando el modelo se ajusta demasiado a los datos de entrenamiento, capturando incluso el ruido de los datos y no generalizando bien a nuevos ejemplos.

Existen diferentes técnicas de regularización utilizadas en redes neuronales, entre las cuales se encuentran Dropout, L2 (Ridge) y L1 (Lasso):

1. **Dropout**: Esta técnica consiste en desactivar aleatoriamente un porcentaje de neuronas durante el entrenamiento de la red neuronal. Al eliminar temporalmente las conexiones entre las neuronas, se evita que ciertas neuronas dependan excesivamente de otras, lo que ayuda a prevenir el sobreajuste. Aunque durante la inferencia todas las neuronas están activadas, los pesos de las conexiones se ajustan en el entrenamiento para tener en cuenta esta desactivación aleatoria.

2. **L2 (Ridge)**: La regularización L2 implica agregar un término a la función de pérdida durante el entrenamiento que penaliza los pesos grandes en la red neuronal. Este término de regularización L2 se calcula como la suma de los cuadrados de todos los pesos en la red, multiplicado por un hiperparámetro llamado factor de regularización. Al penalizar los pesos grandes, la red neuronal tiende a priorizar pesos más pequeños, lo que ayuda a prevenir el sobreajuste al reducir la complejidad del modelo.

3. **L1 (Lasso)**: Similar a la regularización L2, la regularización L1 también agrega un término a la función de pérdida durante el entrenamiento para penalizar los pesos grandes en la red neuronal. Sin embargo, en este caso, el término de regularización L1 se calcula como la suma de los valores absolutos de los pesos en la red, multiplicado por el factor de regularización. La regularización L1 favorece la dispersión de los pesos, lo que puede llevar a una mayor capacidad de selección de características al poner a cero los pesos menos importantes.

Estas técnicas de regularización son fundamentales en el entrenamiento de redes neuronales para mejorar su capacidad de generalización y evitar el sobreajuste a los datos de entrenamiento. Dependiendo de la complejidad del problema, el tamaño del conjunto de datos y otros factores, se puede ajustar el uso y la configuración de las técnicas de regularización para obtener el mejor rendimiento del modelo.
