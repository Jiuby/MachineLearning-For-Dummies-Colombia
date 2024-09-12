# Casos de Uso Avanzados en Regresión Lineal 🌟

¡Hola a todos! En esta clase, vamos a explorar algunos **Casos de Uso Avanzados** para aplicar la regresión lineal. Veremos cómo usar la regresión en situaciones del mundo real para resolver problemas complejos y tomar decisiones basadas en datos. 🚀

## ¿Por Qué Explorar Casos de Uso Avanzados? 🤔

Los casos de uso avanzados te muestran cómo aplicar la regresión lineal en contextos reales y variados. Esto te ayudará a:
- **Resolver Problemas Reales**: Aplicar lo que has aprendido para enfrentar desafíos concretos.
- **Aumentar la Experiencia**: Ampliar tus habilidades para trabajar con datos más complejos.
- **Tomar Decisiones Basadas en Datos**: Utilizar la regresión para obtener insights valiosos.

## Ejemplos de Casos de Uso Avanzados 🌍

### 1. Predicción de Ventas 📈

Imagina que trabajas en una empresa y quieres predecir las ventas futuras basándote en factores como el gasto en publicidad, el número de empleados y el precio de los productos. Puedes usar la regresión lineal para construir un modelo que te ayude a estimar las ventas esperadas.

**Variables Independientes:**
- Gasto en publicidad
- Número de empleados
- Precio de los productos

**Variable Dependiente:**
- Ventas

### 2. Análisis de Riesgo Financiero 💸

En el sector financiero, puedes usar la regresión lineal para analizar el riesgo de crédito. Por ejemplo, puedes predecir la probabilidad de incumplimiento de un préstamo en función de factores como el ingreso del solicitante, su historial crediticio y el monto del préstamo.

**Variables Independientes:**
- Ingreso del solicitante
- Historial crediticio
- Monto del préstamo

**Variable Dependiente:**
- Probabilidad de incumplimiento

### 3. Estudio de Mercado 📊

Las empresas a menudo usan la regresión para analizar cómo factores como el precio, la competencia y las condiciones económicas afectan la demanda de sus productos. Este análisis puede ayudar a las empresas a ajustar sus estrategias de precios y marketing.

**Variables Independientes:**
- Precio del producto
- Competencia en el mercado
- Condiciones económicas

**Variable Dependiente:**
- Demanda del producto

## Ejemplo Práctico en Código 🖥️

Vamos a aplicar la regresión lineal en un caso de uso avanzado. Supongamos que queremos predecir las ventas basándonos en el gasto en publicidad y el número de empleados.

```python
# Importar librerías necesarias
from sklearn.linear_model import LinearRegression
import pandas as pd

# Crear un dataset de ejemplo
data = {
    'Gasto_Publicidad': [2000, 3000, 4000, 5000, 6000],
    'Numero_Empleados': [10, 15, 20, 25, 30],
    'Ventas': [50000, 60000, 70000, 80000, 90000]
}
df = pd.DataFrame(data)

# Definir variables independientes y dependientes
X = df[['Gasto_Publicidad', 'Numero_Empleados']]
y = df['Ventas']

# Ajustar el modelo
model = LinearRegression()
model.fit(X, y)

# Obtener coeficientes
intercepto = model.intercept_
coeficientes = model.coef_

print(f"Intercepto: {intercepto:.2f}")
print(f"Coeficientes (Gasto en Publicidad, Número de Empleados): {coeficientes}")

# Realizar predicciones
X_nuevo = [[3500, 18]]  # Gasto en publicidad, Número de empleados
ventas_prediccion = model.predict(X_nuevo)
print(f"Predicción de Ventas: {ventas_prediccion[0]:.2f}")
