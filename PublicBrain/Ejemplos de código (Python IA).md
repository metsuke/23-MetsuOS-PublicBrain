---
iaStatus: 0
iaStatus_Model: ""
a11y: 0
checked: 0
lang: ES
translations: 
created: 2024-01-28T01:53:10.924Z
modified: 2024-04-03T20:19:14.710Z
supervisado: ""
ACCION: ""
ver_major: 0
ver_minor: 1
ver_rev: 23
nav_primary: []
nav_secondary: []
tags: []
---
# Ejemplos de código (Python IA)

[[Aprender sobre Inteligencia Artificial]]

¡Por supuesto! Aquí te presento algunos ejemplos básicos de código en Python que ilustran conceptos fundamentales de inteligencia artificial:

### 1. Clasificación de Imágenes con TensorFlow/Keras:

```python
import tensorflow as tf
from tensorflow.keras import datasets, layers, models

# Cargar y preprocesar datos
(train_images, train_labels), (test_images, test_labels) = datasets.cifar10.load_data()
train_images, test_images = train_images / 255.0, test_images / 255.0

# Definir modelo de red neuronal convolucional
model = models.Sequential([
    layers.Conv2D(32, (3, 3), activation='relu', input_shape=(32, 32, 3)),
    layers.MaxPooling2D((2, 2)),
    layers.Conv2D(64, (3, 3), activation='relu'),
    layers.MaxPooling2D((2, 2)),
    layers.Conv2D(64, (3, 3), activation='relu'),
    layers.Flatten(),
    layers.Dense(64, activation='relu'),
    layers.Dense(10)
])

# Compilar y entrenar el modelo
model.compile(optimizer='adam',
              loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True),
              metrics=['accuracy'])

model.fit(train_images, train_labels, epochs=10, validation_data=(test_images, test_labels))
```

Este código utiliza TensorFlow y Keras para crear y entrenar una red neuronal convolucional para clasificar imágenes del conjunto de datos CIFAR-10.

### 2. Clasificación de Texto con Scikit-Learn:

```python
from sklearn.datasets import fetch_20newsgroups
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.naive_bayes import MultinomialNB
from sklearn.pipeline import make_pipeline
from sklearn.metrics import accuracy_score

# Cargar datos
categories = ['alt.atheism', 'soc.religion.christian', 'comp.graphics', 'sci.med']
train_data = fetch_20newsgroups(subset='train', categories=categories, shuffle=True, random_state=42)
test_data = fetch_20newsgroups(subset='test', categories=categories, shuffle=True, random_state=42)

# Crear modelo de clasificación de texto
model = make_pipeline(TfidfVectorizer(), MultinomialNB())

# Entrenar modelo
model.fit(train_data.data, train_data.target)

# Predecir y evaluar precisión
predicted_labels = model.predict(test_data.data)
accuracy = accuracy_score(test_data.target, predicted_labels)
print("Accuracy:", accuracy)
```

Este ejemplo utiliza Scikit-Learn para crear un clasificador de texto basado en Naive Bayes Multinomial y lo entrena para clasificar mensajes de noticias en una de las cuatro categorías.

Estos son solo dos ejemplos básicos de cómo se pueden implementar algoritmos de inteligencia artificial en Python. La inteligencia artificial es un campo vasto y diverso, y hay muchas bibliotecas y herramientas disponibles para implementar una amplia gama de algoritmos y técnicas.