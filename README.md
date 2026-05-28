# CelciusFarengeiEntrenamiento

## Descripción

Este repositorio contiene un ejemplo didáctico de entrenamiento de una red neuronal para aprender la conversión entre grados Celsius y Fahrenheit. El proyecto utiliza Python y scikit-learn (MLPRegressor) para demostrar cómo un modelo puede capturar la relación matemática entre ambas escalas de temperatura, así como presentar el proceso de preparación de datos, entrenamiento, evaluación y análisis de resultados.

## Archivos principales

- `CelciusFareneheitSklearn.ipynb`: Notebook con todo el flujo de trabajo, incluyendo explicación teórica, preparación de datos sintéticos, entrenamiento de la red, evaluación de métricas (MAE, RMSE, R2), visualización de resultados y conclusiones.

## Características

- Generación de un dataset sintético de pares Celsius-Fahrenheit.
- Separación de datos para entrenamiento y validación.
- Implementación de una red neuronal con scikit-learn usando `MLPRegressor`.
- Evaluación con métricas de regresión estándar.
- Gráficas para comparar valores reales vs predicciones, curva de pérdida y distribución de errores.
- Análisis y visualización de los coeficientes y bias aprendidos.
- Notebook explicativo y ordenado para propósitos educativos.

## Requisitos

- Python 3.x
- Las siguientes librerías de Python:
  - numpy
  - pandas
  - matplotlib
  - seaborn
  - scikit-learn
  - jupyter

Puedes instalar las dependencias con:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn notebook
```

## Uso

1. Descarga o clona este repositorio.
2. Abre el notebook `CelciusFareneheitSklearn.ipynb` en Jupyter Notebook o Google Colab.
3. Ejecuta las celdas en orden para visualizar todo el proceso de entrenamiento y análisis de resultados.

## Resultados

El modelo logra aprender la conversión Celsius-Fahrenheit con altos niveles de precisión (R2 cercano a 1 y error muy bajo), comprobando que una red neuronal puede captar relaciones matemáticas simples. Se incluye una sección de gráficas y análisis de errores para enriquecer la presentación profesional de los resultados.

## Autor

Repositorio creado por [rubenov02](https://github.com/rubenov02) para fines educativos, demostrando el ciclo básico de entrenamiento y evaluación de una red neuronal en problemas sencillos de regresión.
