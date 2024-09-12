# Clasificación 📊

¡Bienvenido a la siguiente etapa de tu viaje en Machine Learning! 🚀 Ahora vamos a explorar la **Clasificación**, un tipo de modelo que te ayudará a tomar decisiones basadas en categorías. No te preocupes, lo desglosaremos de manera sencilla. 😊

## ¿Qué es la Clasificación? 🤔

La **Clasificación** es una técnica que nos permite predecir a qué categoría pertenece una nueva observación. En lugar de predecir un número como en la regresión lineal, la clasificación nos ayuda a asignar una etiqueta o categoría a los datos.

### ¿Cómo funciona? 🛠️

Imagina que tienes un montón de frutas y quieres clasificar cada una como manzana, plátano o naranja. Usando la clasificación, entrenas un modelo con ejemplos de frutas (y sus etiquetas) para que el modelo aprenda a reconocer las características de cada tipo de fruta.

La **Clasificación** utiliza un conjunto de datos de entrenamiento con ejemplos ya etiquetados para construir un modelo que pueda clasificar nuevas observaciones. Una vez entrenado, el modelo puede predecir a qué categoría pertenece una nueva muestra.

### Ejemplo Visual 🎨

![Imagen](https://aprendeia.com/wp-content/uploads/2018/03/12.png) <!-- Puedes reemplazar esta URL con una imagen que muestre ejemplos de clasificación -->

Supongamos que tienes un dataset con imágenes de frutas etiquetadas como "manzana", "plátano" y "naranja". El modelo de clasificación analizará las características de estas imágenes (como el color, la forma, y el tamaño) y aprenderá a identificar a qué categoría pertenece cada fruta.

## ¿Cuándo usar la Clasificación? 🍎🍌🍊

La **Clasificación** es útil cuando necesitas asignar una categoría a una observación. Algunos ejemplos incluyen:

- **Diagnóstico Médico**: Clasificar pacientes como "con enfermedad" o "sin enfermedad" basado en síntomas y pruebas.
- **Correo Electrónico**: Identificar si un email es "spam" o "no spam".
- **Reconocimiento de Imágenes**: Etiquetar fotos de animales como "gato", "perro" o "pájaro".

### ¿Por qué es útil? 😎

- **Decisiones Basadas en Categorías**: La clasificación te ayuda a tomar decisiones basadas en categorías específicas, en lugar de valores continuos.
- **Aplicaciones del Mundo Real**: Es ampliamente utilizada en diversas áreas, desde la medicina hasta el marketing.

## Implementación Básica en Python 🐍

Aquí te mostramos cómo puedes empezar con un modelo de clasificación en Python usando la librería `scikit-learn`. Vamos a usar un ejemplo simple para clasificar flores en dos categorías.

```python
# Importar las librerías necesarias
import numpy as np
from sklearn.datasets import make_classification # Generar un dataset de ejemplo
from sklearn.model_selection import train_test_split # Dividir los datos en entrenamiento y prueba
from sklearn.neighbors import KNeighborsClassifier # Clasificador de vecinos más cercanos
from sklearn.metrics import accuracy_score # Métrica de precisión

# Crear un dataset de ejemplo
# `make_classification` genera un dataset simple para clasificación
X, y = make_classification(n_samples=100, n_features=2, n_classes=2, random_state=42)

""" 
(La Estructura es la siguiente
n_samples: Número de muestras 
(El número total de muestras o datos que se generarán en el dataset.)
n_features: Número de características
(El número de características o variables que se generarán en el dataset.)
n_classes: Número de clases
(El número de clases o etiquetas que se generarán en el dataset.)
random_state: Semilla aleatoria
(El valor de la semilla aleatoria para generar los datos de manera reproducible.)
""" 

# Dividir el dataset en datos de entrenamiento y prueba
# `train_test_split` divide los datos en conjuntos de entrenamiento y prueba
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Crear y entrenar el modelo
# Usamos el clasificador de vecinos más cercanos (KNeighborsClassifier)
modelo = KNeighborsClassifier(n_neighbors=3)  # n_neighbors indica cuántos vecinos considerar
"""
El clasificador de vecinos más cercanos (KNeighborsClassifier) es un algoritmo simple de clasificación que se basa en la idea de que los puntos de datos similares tienden a estar en la misma clase. 
n_neighbors es un hiperparámetro que indica cuántos vecinos considerar al hacer una predicción.
Descripción: Es un parámetro que indica cuántos vecinos más cercanos se deben considerar para tomar una decisión sobre la clasificación de una muestra. En otras palabras, es el número de vecinos que el algoritmo buscará alrededor de un punto de datos para decidir a qué clase pertenece.
Por ejemplo, si 2 de los 3 vecinos pertenecen a la clase "A" y 1 pertenece a la clase "B", el nuevo punto se clasificará como clase "A".

"""
modelo.fit(X_train, y_train)  # Entrenamos el modelo con los datos de entrenamiento

# Hacer predicciones
# `predict` se usa para hacer predicciones sobre el conjunto de prueba
y_pred = modelo.predict(X_test)

# Evaluar el modelo
# `accuracy_score` calcula la precisión del modelo comparando las predicciones con las etiquetas verdaderas
precisión = accuracy_score(y_test, y_pred)
print(f"La precisión del modelo es: {precisión:.2f}")