# Feature Selection con Artificial Bee Colony (ABC)

##  Descripción
Se utilizó el algoritmo **Artificial Bee Colony (ABC)** para seleccionar las mejores características en un modelo de Machine Learning, reduciendo la cantidad de variables sin perder precisión.

---

##  Funcionamiento
El algoritmo simula una colonia de abejas:

- **Employed Bees:** exploran soluciones cercanas  
- **Onlooker Bees:** eligen soluciones según su calidad  
- **Scout Bees:** generan nuevas soluciones  

Cada solución se representa como un **vector binario**:
- `1` → característica seleccionada  
- `0` → característica descartada  

---

##  Configuración
- Dataset: Breast Cancer Wisconsin  
- Muestras: 569  
- Características: 30  
- Modelo: Random Forest  
- Validación: Cross Validation (CV=5)  

---

## Resultados
- Características seleccionadas: **6 / 30**  
- Reducción: **80%**  
- Accuracy original: **0.9561**  
- Accuracy con selección: **0.9772**  
El modelo mejora su precisión usando menos variables.

---

## ✅ Conclusión
El algoritmo ABC permite reducir la dimensionalidad del problema manteniendo e incluso mejorando el rendimiento del modelo.
