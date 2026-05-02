# Actividad 03 - Algoritmos de Enjambre en Machine Learning

Este repositorio contiene los ejemplos desarrollados para la Actividad 03 del curso de Aprendizaje de Máquina. El objetivo principal es comprender cómo los algoritmos de inteligencia de enjambre pueden aplicarse a problemas de optimización dentro del aprendizaje automático.

## Objetivo

Aplicar algoritmos de enjambre en distintos problemas de Machine Learning, mostrando el ciclo completo del algoritmo:

* Representación de la partícula o solución
* Inicialización del enjambre o población
* Definición de la función de aptitud
* Comportamiento de las partículas o agentes
* Evolución iterativa del algoritmo
* Criterio de finalización y análisis de resultados

## Contenido del repositorio

.
├── abc_feature_selection.py
├── hyperparameter_tuning_con_pso_j.py
├── clustering_gruber.py
├── AlgoritmoEnjambre_Actividad3.ipynb
└── README.md

# 1. Feature Selection con Artificial Bee Colony (ABC)

##  Descripción

Este ejemplo implementa selección de características usando el algoritmo Artificial Bee Colony (ABC). El problema consiste en seleccionar el mejor subconjunto de características para entrenar un modelo de clasificación. Cada solución representa un subconjunto posible de variables del dataset.

##  Dataset utilizado

Se utiliza el dataset Breast Cancer Wisconsin incluido en scikit-learn.

## Representación de la solución

Cada fuente de alimento se representa como un vector binario donde 1 indica que la característica es seleccionada y 0 que es descartada. Por ejemplo: [1, 0, 1, 1, 0].

##  Función de aptitud

La función de aptitud usa un modelo Random Forest evaluado con validación cruzada. Además, se penaliza el uso de demasiadas características:

fitness = alpha * accuracy - beta * penalización

## Ciclo ABC aplicado

Abejas empleadas exploran soluciones vecinas, abejas observadoras seleccionan soluciones según su fitness, abejas exploradoras reemplazan soluciones estancadas, y el proceso finaliza tras un número máximo de iteraciones.

##  Resultados principales

* Reducción de características: 80%
* Features seleccionadas: 6 de 30
* Accuracy con todas: 0.9561
* Accuracy con ABC: 0.9772

El modelo logra mejorar su precisión utilizando menos variables.

# 2. Optimización de Hiperparámetros con PSO

##  Descripción

Este ejemplo utiliza Particle Swarm Optimization (PSO) para encontrar los mejores hiperparámetros de un modelo Random Forest.

## Dataset utilizado

Dataset Wine de scikit-learn.

##  Representación de la partícula

Cada partícula representa una combinación de hiperparámetros: [n_estimators, max_depth].

##  Función de aptitud

La aptitud corresponde al accuracy promedio obtenido mediante validación cruzada:

fitness = accuracy promedio

##  Ciclo PSO

Se inicializan partículas aleatorias, se evalúan, cada partícula guarda su mejor solución, el enjambre sigue la mejor global, se actualizan velocidades y posiciones, y se repite hasta convergencia.

##  Resultados principales

Se obtienen los mejores hiperparámetros, mejora del accuracy y evolución del rendimiento del enjambre.

# 3. Entrenamiento de Red Neuronal sin Backpropagation

##  Descripción

Se entrena una red neuronal utilizando PSO sin usar backpropagation, optimizando directamente los pesos y bias.

##  Representación

Cada partícula contiene todos los parámetros de la red: pesos + bias.

##  Función de aptitud

Se minimiza el error de la red neuronal.

##  Ciclo PSO

Inicialización de pesos, evaluación de la red, actualización del mejor personal y global, ajuste de parámetros y repetición hasta convergencia.

##  Importancia

Demuestra que una red neuronal puede entrenarse sin gradientes, usando optimización poblacional.

# 4. Clustering con PSO

##  Descripción

PSO se usa para encontrar centroides óptimos en problemas de clustering.

##  Dataset

Breast Cancer (WBCD) en formato CSV.

##  Representación

Cada partícula representa un conjunto de centroides: [centroide_1, ..., centroide_k].

## Función de aptitud

Se minimiza el error cuadrático:

fitness = SSE

##  Métricas utilizadas

SSE, Silhouette Score y Adjusted Rand Index.

## 📈 Resultados

Se realiza comparación con K-Means mostrando desempeño competitivo o superior.

## ⚙️ Requisitos

Python 3.10 o superior

pip install numpy pandas matplotlib scikit-learn seaborn

## Ejecución

python abc_feature_selection.py
python hyperparameter_tuning_con_pso_j.py
python clustering_gruber.py

Abrir el notebook en Colab o Jupyter para el caso de la red neuronal.

##  Conclusiones

Los algoritmos de enjambre son herramientas eficaces para resolver problemas de optimización en Machine Learning. ABC permite reducir características mejorando el rendimiento, PSO optimiza hiperparámetros de forma eficiente, también puede entrenar redes neuronales sin backpropagation y resolver problemas de clustering. En general, estos métodos destacan por su capacidad de exploración global y por no depender de derivadas, aunque implican un mayor costo computacional.

##  Autores

Equipo de trabajo - Actividad 03
* Almanza Mamani Edith Nayely 
*  Gruber Coaquira, Gian Carlos
* Quispe Caceres Juan Efrain
* Quispe Quispe Shamely Angeles


##  Curso

Aprendizaje de Máquina
