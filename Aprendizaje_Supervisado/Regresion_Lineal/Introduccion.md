# Regresión Lineal 📈

¡Bienvenido a tu primer modelo de Machine Learning! 🚀 Vamos a hablar sobre la **Regresión Lineal**, uno de los modelos más sencillos y útiles para entender cómo funcionan las predicciones en ML. No te preocupes, lo haremos paso a paso. 😊

## ¿Qué es la Regresión Lineal? 🤔

La **Regresión Lineal** es un método estadístico que nos ayuda a predecir un valor numérico basado en la relación entre diferentes variables. En términos más simples, imagina que quieres predecir algo (por ejemplo, el precio de una casa) y tienes algunas pistas (como el tamaño de la casa o el número de habitaciones). La regresión lineal utiliza estas pistas para hacer una predicción.

### ¿Cómo funciona? 📊

Piensa en un gráfico con una línea recta (como cuando dibujabas una línea en matemáticas 📏). La idea detrás de la **Regresión Lineal** es encontrar una línea que mejor ajuste a los datos. Esa línea nos ayudará a hacer predicciones sobre cosas que aún no hemos visto.

La fórmula básica de la regresión lineal es esta:

y = mx + b


- **y** es el valor que estamos tratando de predecir (por ejemplo, el precio de una casa).
- **x** es la pista o característica (por ejemplo, el tamaño de la casa).
- **m** es la pendiente de la línea (esto nos dice qué tan rápido cambia el precio a medida que cambia el tamaño).
- **b** es dónde la línea cruza el eje y (esto nos da un punto de partida para la predicción).

### Ejemplo Visual 🎨

![Imagen](https://th.bing.com/th/id/OIP.Tea3FB1H8IWdYTabnazMegHaFx?rs=1&pid=ImgDetMain)

Imagina que tenemos un gráfico donde el eje X representa el tamaño de una casa en metros cuadrados, y el eje Y es el precio en dólares. La **Regresión Lineal** busca la mejor línea que conecta esos puntos y nos permite predecir el precio de una casa de un tamaño específico.

## ¿Cuándo usar la Regresión Lineal? 🏡

La **Regresión Lineal** es ideal para predecir valores numéricos basados en una o más características. Algunos ejemplos incluyen:

- Predecir el precio de una casa basado en su tamaño, ubicación, o número de habitaciones.
- Estimar el ingreso mensual de una persona basado en su nivel de educación o años de experiencia.
- Predecir la cantidad de ventas de un producto basado en el gasto en publicidad.

### ¿Por qué es útil? 😎

- **Simple**: La regresión lineal es uno de los modelos más fáciles de entender y utilizar.
- **Rápido**: Es eficiente cuando tienes pocos datos y quieres obtener resultados rápidamente.
- **Útil para empezar**: Si nunca has hecho predicciones antes, este es un buen lugar para comenzar a entender cómo los modelos de machine learning hacen su magia.

## Implementación Básica en Python 🐍

Aquí te doy una idea de cómo implementar **Regresión Lineal** en Python utilizando la librería `scikit-learn` (¡no te preocupes si esto aún te suena complicado, lo iremos viendo más adelante!):

```python
"""
Importamos la librería necesaria que nos ayuda a realizar el modelo de
regresión lineal.
"""
from sklearn.linear_model import LinearRegression

# Creamos el modelo
modelo = LinearRegression()

# Supongamos que tenemos estos datos
# X es el tamaño de la casa y y es el precio
X = [[30], [50], [70], [100]]  # Tamaño de la casa en metros cuadrados
y = [100000, 150000, 200000, 300000]  # Precio en dólares

# Entrenamos el modelo con los datos

modelo.fit(X, y) # modelo lo definimos arriba y fit es un método de la clase LinearRegression
#Con el metodo de arriba entrenamos los valores de X y Y


# Hacemos una predicción para una casa de 60 metros cuadrados
precio_predicho = modelo.predict([[60]]) #predict es un método de la clase LinearRegression el cual nos permite predecir el valor de Y para un valor de X
print(f"El precio predicho para una casa de 60 metros cuadrados es: {precio_predicho}")
