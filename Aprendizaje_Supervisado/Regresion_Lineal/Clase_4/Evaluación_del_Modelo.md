# Evaluación del Modelo de Regresión Lineal 🚀

¡Bienvenidos a la cuarta clase! Hoy exploraremos cómo evaluar un modelo de regresión lineal para asegurarnos de que esté funcionando correctamente. La evaluación es clave para verificar qué tan bien nuestro modelo hace sus predicciones. 🌟

## ¿Qué es la Evaluación del Modelo? 🤔

La evaluación del modelo nos permite medir la calidad de nuestras predicciones y entender qué tan bien nuestro modelo se ajusta a los datos. Utilizamos diferentes métricas para hacer esto. Aquí vamos a ver las más comunes:

### 1. Error Cuadrático Medio (MSE) 📉

El **Error Cuadrático Medio** mide la diferencia promedio entre las predicciones del modelo y los valores reales. Se calcula como el promedio de los cuadrados de los errores (diferencias). Menor MSE significa un mejor ajuste.

**Fórmula:**

![Imagen](https://wikimedia.org/api/rest_v1/media/math/render/svg/1d23c11997cc3031f9bd4bdeec962da63502466f)



### 2. Coeficiente de Determinación (R²) 📊

El **R²** indica qué porcentaje de la variabilidad de la variable dependiente es explicado por el modelo. Varía entre 0 y 1, donde 1 significa que el modelo explica toda la variabilidad y 0 significa que no explica nada.

**Fórmula:**

![Imagen](https://wikimedia.org/api/rest_v1/media/math/render/svg/25af69579c4de42567491bf88bd9981fa07c76e0)
### 3. Validación Cruzada 🔄

La **validación cruzada** es una técnica para evaluar la capacidad de generalización del modelo. Consiste en dividir los datos en varias partes (folds) y entrenar el modelo en una parte mientras se valida en otra. Esto ayuda a verificar si el modelo funciona bien en datos no vistos.

## Ejemplo Práctico en Código 🖥️

Vamos a ver cómo aplicar estas métricas en Python utilizando el paquete `scikit-learn`. Suponemos que ya tenemos un modelo de regresión lineal entrenado.

```python
# Importar librerías necesarias
from sklearn.metrics import mean_squared_error, r2_score
import numpy as np

# Supongamos que tenemos las siguientes predicciones y valores reales
y_true = np.array([3, -0.5, 2, 7])
y_pred = np.array([2.5, 0.0, 2, 8])

# Calcular MSE
mse = mean_squared_error(y_true, y_pred)
print(f"Error Cuadrático Medio (MSE): {mse:.2f}")

# Calcular R²
r2 = r2_score(y_true, y_pred)
print(f"Coeficiente de Determinación (R²): {r2:.2f}")
