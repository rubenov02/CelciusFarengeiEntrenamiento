# 🧠 Entrenamiento de Red Neuronal: Celsius a Fahrenheit

## 1. Descripción General

Este repositorio contiene un ejemplo didáctico completo sobre el entrenamiento de una red neuronal para aprender la conversión entre grados Celsius y Fahrenheit. Utiliza Python y scikit-learn (`MLPRegressor`) para demostrar cómo un modelo de aprendizaje automático puede capturar relaciones matemáticas subyacentes con alta precisión.

El proyecto está diseñado para poder  comprendan todo el flujo de trabajo de un proyecto de IA/ML:
- Generación y preparación de datos sintéticos.
- Escalado de características con `StandardScaler`.
- Separación de datos de entrenamiento y prueba (80/20).
- Entrenamiento del modelo perceptrón multicapa utilizando `Pipeline`.
- Evaluación con métricas estándar (MAE, MSE, RMSE, R²) y visualizaciones gráficas.
- Sección avanzada: exploración de funciones de activación y extracción matemática de pesos.

## 2. Estructura del Notebook

El notebook `CelciusFareneheitSklearn.ipynb` está organizado en las siguientes secciones:

### Reporte de entrenamiento
- Importación de librerías y configuración del entorno gráfico con Seaborn.
- Generación de un conjunto de datos sintético de **120 registros** en el rango de **-40°C a 120°C**.

### 1. Datos y preparación
- Partición de datos con `train_test_split` (test_size=0.2, random_state=42).
- Entrenamiento del modelo `MLPRegressor` dentro de un `Pipeline` con `StandardScaler`.
- Configuración: `hidden_layer_sizes=(8,)`, `activation='identity'`, `solver='adam'`, `learning_rate_init=0.01`, `max_iter=1500`.
- **Resultado:** 560 iteraciones, pérdida final: 0.001541.

### 2. Entrenamiento del modelo
- Predicciones sobre el conjunto de prueba.
- Tabla comparativa de valores reales vs. predichos con errores.

### 3. Evaluación y resultados
- Gráfica de **Predicción vs Real** para evaluación visual.
- Curva de pérdida por iteración.
- Distribución de errores (histograma con KDE).
- **Métricas obtenidas:**

| Métrica | Valor |
|---------|-------|
| MAE     | 0.048142 |
| MSE     | 0.003241 |
| RMSE    | 0.056927 |
| **R²**  | **0.999999** |

### 4. Oportunidades de Mejora (Sección Avanzada)
1. **Ruido en los datos:** Se agrega ruido gaussiano para simular datos provenientes de sensores reales.
2. **Exploración de Activaciones:** Comparación entre `identity`, `relu` y `tanh`:
   - `identity`: MAE=3.84, R²=0.9966, 556 iteraciones.
   - `relu`: MAE=3.96, R²=0.9964, 1500 iteraciones.
   - `tanh`: MAE=26.85, R²=0.6827, 1500 iteraciones.
3. **Extracción Matemática de Pesos:** Se demuestra que la red neuronal aprende valores cercanos a los coeficientes $1.8$ y $32$ de la fórmula $F = C \times 1.8 + 32$.

## 3. Estructura de Archivos

| Archivo | Descripción |
|---------|-------------|
| `CelciusFareneheitSklearn.ipynb` | Notebook principal con todo el flujo de entrenamiento y evaluación. |
| `comparacion_activaciones.png` | Gráfica comparativa de funciones de activación (identity, relu, tanh). |
| `loss_curves.png` | Curvas de pérdida del entrenamiento. |
| `run_improvements.py` | Script auxiliar para ejecutar mejoras avanzadas sobre el modelo. |
| `update_notebook.py` | Script auxiliar para actualizar el contenido del notebook. |
| `fix_notebook.py` | Script auxiliar para corregir el notebook. |
| `.gitignore` | Archivos y carpetas excluidos del control de versiones. |

## 4. Tecnologías y Requisitos

- **Python 3.11+**
- Bibliotecas necesarias:
  - `numpy` — Operaciones matriciales y generación de datos sintéticos.
  - `pandas` — Estructuración de resultados en DataFrames.
  - `matplotlib` y `seaborn` — Gráficas de comparación, curvas de pérdida y distribuciones.
  - `scikit-learn` — Algoritmo `MLPRegressor`, `StandardScaler`, `Pipeline` y partición de datos.
  - `ipython` — Visualización enriquecida de tablas en el notebook.

### Instalación

```bash
pip install numpy pandas matplotlib seaborn scikit-learn ipython notebook
```

## 5. Ejecución del Proyecto

Para explorar y ejecutar este proyecto:
1. Clona este repositorio o descarga los archivos.
2. Instala las dependencias con `pip install` (ver sección anterior).
3. Abre la terminal en el directorio del proyecto y ejecuta:
   ```bash
   jupyter notebook CelciusFareneheitSklearn.ipynb
   ```
4. Ejecuta las celdas secuencialmente para observar:
   - La generación del conjunto de datos y su exploración.
   - El entrenamiento del modelo y las métricas de evaluación.
   - Las gráficas de predicción vs. realidad, curva de pérdida y distribución de errores.
   - La sección avanzada con comparación de activaciones y extracción de la fórmula aprendida.

## 6. Resultados y Conclusión

El modelo `MLPRegressor` con activación `identity` y una capa oculta de 8 neuronas logra aproximar **casi a la perfección** (R² = 0.999999) la fórmula $F = C \times 1.8 + 32$ con datos limpios, convergiendo en solo **560 iteraciones**.

En la sección avanzada, al introducir ruido gaussiano en los datos, se demuestra que:
- La activación `identity` sigue siendo la más eficiente (R² = 0.9966, convergencia rápida).
- `relu` obtiene resultados similares pero requiere las 1500 iteraciones máximas.
- `tanh` no logra capturar adecuadamente la relación lineal (R² = 0.6827).

Esto confirma la capacidad de las redes neuronales para actuar como modelos de regresión lineal escalables, incluso ante datos imperfectos.

## Autor

Repositorio creado por [rubenov02](https://github.com/rubenov02) para fines educativos, demostrando el ciclo básico y avanzado de entrenamiento y evaluación de una red neuronal en problemas de regresión.
