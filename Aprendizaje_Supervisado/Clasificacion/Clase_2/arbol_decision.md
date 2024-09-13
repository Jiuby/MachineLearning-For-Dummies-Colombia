# Árboles de Decisión

![Imagen](https://blog.finxter.com/wp-content/uploads/2018/07/ML_DecisionTree.png)
Los árboles de decisión son un método de clasificación y regresión que utiliza un modelo en forma de árbol para tomar decisiones. Son fáciles de interpretar y pueden manejar tanto datos categóricos como numéricos.

## Estructura Básica

Un árbol de decisión se compone de los siguientes elementos:

1. **Nodos de Decisión**: Estos nodos representan preguntas o condiciones sobre los datos. Cada nodo toma una decisión sobre una característica particular.

2. **Ramas**: Las ramas conectan los nodos y representan las posibles respuestas a las preguntas del nodo. Cada rama lleva a un nuevo nodo o a una hoja.

3. **Hojas**: Las hojas del árbol representan la decisión final o la predicción. No hay más nodos después de una hoja; es el punto de terminación del árbol.

### Ejemplo de Árbol de Decisión

Vamos a crear un árbol de decisión simple para decidir si llevar un paraguas basándonos en el clima.

#### Dataset

Considera el siguiente conjunto de datos sobre el clima:

| Día   | Nublado | Lluvia | Llevar Paraguas |
|-------|---------|--------|-----------------|
| 1     | Sí      | No     | No              |
| 2     | Sí      | Sí     | Sí              |
| 3     | No      | Sí     | Sí              |
| 4     | No      | No     | No              |

#### Construcción del Árbol

1. **Nodo Raíz**: Comenzamos con una pregunta general. En este caso, podemos empezar con: "¿Está nublado?"
   - **Sí**: Si la respuesta es sí, avanzamos al siguiente nodo.
   - **No**: Si la respuesta es no, la decisión es "No llevar paraguas".

2. **Segundo Nivel**: Para los días nublados, la siguiente pregunta puede ser: "¿Está lloviendo?"
   - **Sí**: Si la respuesta es sí, la decisión es "Llevar paraguas".
   - **No**: Si la respuesta es no, la decisión es "No llevar paraguas".

#### Visualización

Aquí tienes un dibujo simple del árbol de decisión para este ejemplo:

![Imagen](https://www.saedsayad.com/images/Decision_tree_r1.png)
