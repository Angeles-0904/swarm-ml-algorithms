##Algoritmos de Enjambre en Machine Learning

## Integrantes

* Quispe Quispe Shamely Angeles
* 

---

# 1. Feature Selection con Artificial Bee Colony (ABC)

##  Introducción

En Machine Learning, no siempre utilizar todas las características disponibles mejora el rendimiento del modelo. En muchos casos, un exceso de variables puede provocar **sobreajuste (overfitting)**, aumentar el tiempo de entrenamiento y reducir la capacidad de generalización.

Por ello, la **selección de características** es un proceso fundamental que permite identificar el subconjunto óptimo de variables más relevantes.

---

##  Descripción del algoritmo ABC

El algoritmo **Artificial Bee Colony (ABC)**, propuesto por Dervis Karaboga, simula el comportamiento de una colonia de abejas en la búsqueda de alimento.

El modelo se basa en tres tipos de agentes:

* **Employed Bees (Abejas empleadas):** exploran soluciones cercanas a una fuente actual
* **Onlooker Bees (Abejas observadoras):** seleccionan soluciones basándose en su calidad (fitness)
* **Scout Bees (Abejas exploradoras):** generan nuevas soluciones aleatorias cuando una fuente es abandonada

Este enfoque permite equilibrar dos procesos clave:

* **Exploración** (buscar nuevas soluciones)
* **Explotación** (mejorar soluciones existentes)

---

## Representación de la solución

Cada solución se representa como un **vector binario**, donde cada posición indica si una característica es seleccionada o no:

```
[1, 0, 1, 1, 0, 0, 1, ...]
```

* `1` → característica seleccionada
* `0` → característica descartada

Esta representación permite recorrer eficientemente el espacio de posibles combinaciones.

---
##  Función de aptitud (Fitness)

La calidad de cada solución se evalúa mediante una función de aptitud que combina:

* Precisión del modelo (accuracy)
* Penalización por número de características

Esto permite encontrar un equilibrio entre rendimiento y simplicidad del modelo, evitando soluciones con demasiadas variables.

---

##  Ciclo del algoritmo

El algoritmo sigue un proceso iterativo compuesto por las siguientes fases:

1. Inicialización de soluciones aleatorias
2. Fase de abejas empleadas (exploración local)
3. Fase de abejas observadoras (selección probabilística)
4. Fase de abejas exploradoras (reinicio de soluciones)
5. Actualización de la mejor solución global

Este ciclo se repite hasta alcanzar el número máximo de iteraciones.

---

##  Implementación del modelo

Para evaluar cada solución se utiliza un enfoque tipo **wrapper**, empleando un modelo real de Machine Learning:

* Clasificador: Random Forest
* Validación: Cross-validation (CV=5)
* Preprocesamiento: normalización de datos

El algoritmo evalúa múltiples combinaciones de características y selecciona aquellas que maximizan el rendimiento.

---

##  Dataset utilizado

Se utilizó el dataset **Breast Cancer Wisconsin**, el cual contiene:

* 569 muestras
* 30 características
* Clasificación binaria (benigno / maligno)

Este dataset es ampliamente utilizado para problemas de clasificación.

---

## Resultados obtenidos

Los resultados muestran que el algoritmo ABC logra:

* Reducir significativamente el número de características
* Mantener o incluso mejorar la precisión del modelo
* Disminuir la complejidad del sistema

Esto demuestra la eficacia del algoritmo en problemas de optimización combinatoria.

---

##  Visualizaciones

El modelo genera diferentes gráficos para el análisis:

* Evolución del fitness (convergencia)
* Comparación de precisión (antes vs después)
* Importancia de características seleccionadas

Estos resultados permiten interpretar el comportamiento del algoritmo.

---

##  Conclusión de la sección ABC

El algoritmo Artificial Bee Colony se presenta como una técnica eficiente para la selección de características, ya que logra un equilibrio entre exploración y explotación del espacio de soluciones.

Su aplicación permite mejorar el rendimiento de modelos de Machine Learning reduciendo la dimensionalidad sin perder precisión.

---
