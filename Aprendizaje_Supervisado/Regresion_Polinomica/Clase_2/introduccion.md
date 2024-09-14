# Clase 2: Sobreajuste, Subajuste y Selección del Grado en Regresión Polinómica

## Objetivos de la Clase
En esta clase, aprenderemos dos conceptos muy importantes al trabajar con modelos de machine learning: **sobreajuste** (overfitting) y **subajuste** (underfitting). También veremos cómo seleccionar el grado adecuado para un modelo de **regresión polinómica**.

Al final de esta clase, sabrás cómo:
1. Detectar si un modelo es demasiado simple o demasiado complejo para tus datos.
2. Elegir el grado correcto para una regresión polinómica.
3. Evaluar si un modelo es bueno usando métricas como **R²** y **RMSE**.

## Conceptos Clave

### ¿Qué es el Subajuste?
Un modelo que **subajusta** es demasiado simple para capturar los patrones en los datos. Esto pasa cuando, por ejemplo, usas una línea recta (grado 1) para predecir algo que tiene una forma curva o más compleja.


### ¿Qué es el Sobreajuste?
Un modelo que **sobreajusta** es demasiado complejo y aprende incluso el ruido de los datos. Esto pasa cuando el modelo se ajusta muy bien a los datos de entrenamiento, pero no puede generalizar cuando se le presentan datos nuevos. Un ejemplo es cuando usamos un polinomio de grado muy alto, lo que lleva a que el modelo se ajuste demasiado a los puntos específicos del dataset.

### ¿Cómo seleccionar el grado correcto?
Para elegir el grado correcto, usamos **validación cruzada**, que nos ayuda a probar diferentes grados del modelo y encontrar el que mejor se ajusta a los datos sin sobreajustarse o subajustarse.

![Imagen](https://www.fisicalab.com/sites/all/files/contenidos/matematicas/8660_funciones_polinomicas/funciones_polinomicas.jpg)
## Ejemplo de Aplicación: Predicción del Consumo de Energía

Imaginemos que queremos predecir el **consumo de energía eléctrica** en una ciudad dependiendo de la hora del día.

Supongamos que tenemos el siguiente dataset (horas del día y consumo en megavatios):

| Hora del Día | Consumo de Energía (MW) |
|--------------|-------------------------|
| 1            | 20                      |
| 4            | 22                      |
| 7            | 50                      |
| 10           | 70                      |
| 13           | 90                      |
| 16           | 75                      |
| 19           | 60                      |
| 22           | 30                      |

### Problema:
La relación entre la hora del día y el consumo de energía no es lineal. A ciertas horas (como en la mañana y el mediodía), el consumo es mucho más alto, mientras que en la noche baja. Usaremos **regresión polinómica** para modelar esta relación.

## Ejemplo Simple de Código

Aquí tienes un código para ajustar una regresión polinómica y elegir el grado adecuado:

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score

# Dataset: Horas y consumo de energía (ficticio)
horas = np.array([1, 4, 7, 10, 13, 16, 19, 22]).reshape(-1, 1)
consumo = np.array([20, 22, 50, 70, 90, 75, 60, 30])

# Dividimos los datos en entrenamiento y prueba
X_train, X_test, y_train, y_test = train_test_split(horas, consumo, test_size=0.2, random_state=42)

# Probemos con un polinomio de grado 3
poly = PolynomialFeatures(degree=3)
X_train_poly = poly.fit_transform(X_train)
X_test_poly = poly.transform(X_test)

# Creamos el modelo de regresión
modelo = LinearRegression()
modelo.fit(X_train_poly, y_train)

# Hacemos predicciones
y_pred_train = modelo.predict(X_train_poly)
y_pred_test = modelo.predict(X_test_poly)

# Evaluamos el modelo
print("Error cuadrático medio (RMSE) en entrenamiento:", np.sqrt(mean_squared_error(y_train, y_pred_train)))
print("Error cuadrático medio (RMSE) en prueba:", np.sqrt(mean_squared_error(y_test, y_pred_test)))
print("R² en prueba:", r2_score(y_test, y_pred_test))

# Visualizamos el ajuste
plt.scatter(horas, consumo, color='blue', label='Datos originales')
plt.plot(horas, modelo.predict(poly.fit_transform(horas)), color='red', label='Modelo polinómico (grado 3)')
plt.xlabel('Hora del Día')
plt.ylabel('Consumo de Energía (MW)')
plt.legend()
plt.show()
