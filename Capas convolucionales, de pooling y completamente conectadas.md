# Capas convolucionales, de pooling y completamente conectadas

[[Estructura y funcionamiento de las  redes neuronales]]

Las redes neuronales convolucionales (CNN) son un tipo de red neuronal especialmente diseñada para el procesamiento de datos que tienen una forma de cuadrícula, como imágenes. Las capas convolucionales son una parte fundamental de las CNN y se utilizan para detectar patrones en los datos de entrada.

En una capa convolucional, se aplican filtros sobre la imagen de entrada para extraer características relevantes. Estos filtros son pequeñas matrices que se desplazan a lo largo de la imagen y realizan una operación de convolución para producir un mapa de características. Cada filtro está diseñado para detectar ciertas características, como bordes, colores o texturas.

Después de la capa convolucional, es común utilizar una capa de pooling para reducir la dimensionalidad de los datos y hacer que el modelo sea más rápido y eficiente. La capa de pooling toma pequeñas secciones de la imagen y aplica alguna operación de resumen, como el máximo o el promedio, para obtener una representación más compacta de la imagen.

Finalmente, las capas completamente conectadas se utilizan para combinar las características extraídas por las capas convolucionales y de pooling para realizar la clasificación final. En estas capas, cada neurona está conectada a todas las neuronas de la capa anterior, lo que permite al modelo aprender relaciones complejas entre las características.

En resumen, las capas convolucionales se encargan de extraer características de los datos de entrada, las capas de pooling reducen la dimensionalidad de los datos y las capas completamente conectadas se utilizan para realizar la clasificación final. Juntas, estas capas forman una red neuronal convolucional efectiva para tareas de reconocimiento de patrones en datos de forma de cuadrícula, como imágenes.
