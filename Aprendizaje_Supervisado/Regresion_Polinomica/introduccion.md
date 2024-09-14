# Regresión Polinómica

La **Regresión Polinómica** es un tipo de regresión que se usa cuando la relación entre las variables no es lineal. En vez de ajustar una línea recta como en la regresión lineal, la regresión polinómica ajusta una curva que puede seguir mejor la tendencia de los datos.

## ¿Qué es la Regresión Polinómica?

En términos simples:
- **Regresión Lineal**: Ajusta una línea recta a los datos.
- **Regresión Polinómica**: Ajusta una curva que sigue mejor las variaciones en los datos.

### Ecuación Básica

La ecuación de una regresión polinómica de grado \(n\) es:

\[
y = \beta_0 + \beta_1 X + \beta_2 X^2 + \beta_3 X^3 + \dots + \beta_n X^n + \epsilon
\]

Donde:
- \( y \) es la variable dependiente que queremos predecir.
- \( X \) es la variable independiente.
- \( \beta_0, \beta_1, \beta_2, \dots, \beta_n \) son los coeficientes.
- \( n \) es el grado del polinomio (cuántas curvas puede tener nuestra gráfica).
- \( \epsilon \) es el error o residuo.

## ¿Cómo Funciona?

1. **Transformación Polinómica**: Convertimos la variable independiente \( X \) en términos polinómicos (\( X, X^2, X^3, ... \)).
2. **Ajuste del Modelo**: El modelo trata de encontrar los mejores coeficientes \( \beta \) que minimicen el error entre los valores reales y los predichos.
3. **Predicción**: El modelo utiliza la fórmula para predecir valores futuros.

### ¿Por qué usar Regresión Polinómica?

- **Relaciones no lineales**: Es útil cuando los datos no siguen una tendencia recta.
- **Curvas más complejas**: Permite modelar curvas para capturar mejor la naturaleza de los datos.

#una imagen de regresion polinomica
![Imagen](https://sensoricx.com/wp-content/uploads/2017/12/regresion_polinomial.png)
## Ejemplo Básico en Python

Aquí hay un ejemplo práctico usando `scikit-learn`:

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression

# Datos de ejemplo (tiempo en segundos, velocidad en km/h)
X = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9]).reshape(-1, 1)
y = np.array([3, 7, 13, 25, 40, 60, 90, 120, 150])

# Transformamos los datos a términos polinómicos (grado 2)
poly = PolynomialFeatures(degree=2)
X_poly = poly.fit_transform(X)

# Creamos el modelo de regresión lineal
model = LinearRegression()
model.fit(X_poly, y)

# Predicción
y_pred = model.predict(X_poly)

# Gráfica
plt.scatter(X, y, color='blue')  # Datos originales
plt.plot(X, y_pred, color='red')  # Predicción
plt.title('Regresión Polinómica (Grado 2)')
plt.xlabel('Tiempo (s)')
plt.ylabel('Velocidad (km/h)')
plt.show()

