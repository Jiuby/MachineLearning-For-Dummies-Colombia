# Interpretación de Coeficientes en Regresión Lineal 📊

¡Hola a todos! En esta clase vamos a aprender sobre la **Interpretación de Coeficientes** en un modelo de regresión lineal. Entender los coeficientes es crucial para interpretar cómo las variables independientes afectan a la variable dependiente. Vamos a desglosarlo en términos simples. 😊

## ¿Qué Son los Coeficientes? 🤔

En un modelo de regresión lineal, cada **coeficiente** representa la relación entre una variable independiente y la variable dependiente. Básicamente, nos dice cuánto cambia la variable dependiente cuando la variable independiente cambia en una unidad, manteniendo las otras variables constantes.

## ¿Por Qué es Importante? 🌟

Interpretar los coeficientes te ayuda a:
- **Comprender el Impacto**: Saber cómo cada variable afecta a la variable que estás tratando de predecir.
- **Tomar Decisiones**: Usar la información para tomar decisiones basadas en los datos.
- **Comunicar Resultados**: Explicar tus hallazgos de manera clara a otros.

## Ejemplo Sencillo 🧩

Imaginemos que estás usando un modelo de regresión lineal para predecir el precio de las casas basándote en el tamaño de la casa (en metros cuadrados) y el número de habitaciones. El modelo podría ser algo así:

\[ Precio = \beta_0 + \beta_1 \times Tamaño + \beta_2 \times Habitaciones \]

Aquí:
- \( \beta_0 \) es el **intercepto** (el precio base de la casa cuando el tamaño y el número de habitaciones son cero).
- \( \beta_1 \) es el coeficiente del tamaño (cuánto cambia el precio por cada metro cuadrado adicional).
- \( \beta_2 \) es el coeficiente del número de habitaciones (cuánto cambia el precio por cada habitación adicional).

Supongamos que obtenemos los siguientes coeficientes:

- \( \beta_0 = 50,000 \)
- \( \beta_1 = 200 \)
- \( \beta_2 = 5,000 \)

Esto significa que:
- **Intercepto (\( \beta_0 \))**: El precio base de la casa sería $50,000 si el tamaño y el número de habitaciones fueran cero (lo cual no es realista, pero es una parte del modelo).
- **Tamaño (\( \beta_1 \))**: Cada metro cuadrado adicional aumenta el precio en $200.
- **Habitaciones (\( \beta_2 \))**: Cada habitación adicional aumenta el precio en $5,000.

## Ejemplo Práctico en Código 🖥️

Vamos a ver cómo interpretar los coeficientes en un modelo simple utilizando Python.

```python
# Importar librerías necesarias
from sklearn.linear_model import LinearRegression
import numpy as np

# Crear un dataset de ejemplo
X = np.array([[1, 10], [2, 15], [3, 20], [4, 25]])  # [Tamaño, Habitaciones]
y = np.array([100000, 150000, 200000, 250000])     # Precio

# Ajustar el modelo
model = LinearRegression()
model.fit(X, y)

# Obtener coeficientes
intercepto = model.intercept_
coeficientes = model.coef_

print(f"Intercepto: {intercepto:.2f}")
print(f"Coeficientes (Tamaño, Habitaciones): {coeficientes}")

# Interpretación
print(f"Cada unidad adicional de tamaño aumenta el precio en: {coeficientes[0]:.2f}")
print(f"Cada unidad adicional de habitaciones aumenta el precio en: {coeficientes[1]:.2f}")
