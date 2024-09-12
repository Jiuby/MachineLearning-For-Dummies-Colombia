# Regularización en Regresión Lineal 🌟

¡Hola y bienvenidos a la cuarta clase! Hoy vamos a explorar la **Regularización**, una técnica clave para mejorar nuestros modelos de regresión lineal y evitar problemas como el sobreajuste. 🚀

## ¿Qué es la Regularización? 🤔

En la regresión lineal, **regularización** es una técnica que ayuda a simplificar el modelo para que no se ajuste demasiado a los datos de entrenamiento. Esto se conoce como **sobreajuste** (overfitting). Un modelo sobreajustado funciona muy bien con los datos de entrenamiento pero falla con datos nuevos.

## ¿Cómo Funciona la Regularización? 🔧

La regularización añade un **término de penalización** a la función de costo del modelo. Este término penaliza los coeficientes del modelo si son demasiado grandes, lo que ayuda a evitar que el modelo se vuelva demasiado complejo.

### Tipos de Regularización

#### 1. **Regularización Lasso (L1)** 🧩

**Lasso** (Least Absolute Shrinkage and Selection Operator) añade una penalización proporcional a la **suma de los valores absolutos** de los coeficientes del modelo. Esto puede llevar a que algunos coeficientes se reduzcan a cero, eliminando efectivamente algunas variables del modelo.




#### 2. **Regularización Ridge (L2)** 🌐

**Ridge** añade una penalización proporcional a la **suma de los cuadrados** de los coeficientes del modelo. Esto hace que los coeficientes se reduzcan, pero rara vez a cero, ayudando a manejar problemas de multicolinealidad.



## Ejemplo Práctico en Código 🖥️

Vamos a ver cómo aplicar Lasso y Ridge en Python usando `scikit-learn`. Suponemos que ya tenemos un dataset y queremos ajustar un modelo con regularización.

```python
# Importar librerías necesarias
from sklearn.linear_model import Lasso, Ridge
from sklearn.datasets import make_regression
from sklearn.model_selection import train_test_split

# Crear un dataset de ejemplo
X, y = make_regression(n_samples=100, n_features=5, noise=0.1, random_state=42)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Ajustar modelo Lasso
lasso = Lasso(alpha=0.1)  # alpha es el parámetro de regularización
lasso.fit(X_train, y_train)

# Ajustar modelo Ridge
ridge = Ridge(alpha=0.1)  # alpha es el parámetro de regularización
ridge.fit(X_train, y_train)

# Hacer predicciones y evaluar
print(f"Coeficientes Lasso: {lasso.coef_}")
print(f"Coeficientes Ridge: {ridge.coef_}")
