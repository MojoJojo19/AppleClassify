# Plan de Implementación para la Entrega Final: Proyecto AppleClassify

Este documento detalla las tareas y características que deben implementarse para completar la entrega final del proyecto de clasificación de manzanas.

## 1. Comparación de Técnicas de Preprocesamiento
El proyecto actual realiza extracción de características visuales (color, forma, textura GLCM) con OpenCV. Se debe expandir la metodología para evaluar cómo distintas técnicas de preprocesamiento afectan el rendimiento.

*   **Evaluación de Zonas Oscuras:**
    *   Entrenar y evaluar modelos incluyendo la detección de *Zonas oscuras* (defectos).
    *   Entrenar y evaluar modelos *Sin zonas oscuras* (imágenes estándar o desactivando el pipeline de defectos).
    *   Realizar una comparación cuantitativa de ambas estrategias.
*   **Normalización Distinta:**
    *   Probar al menos dos métodos de escalado distintos sobre el vector de características (por ejemplo, `StandardScaler` vs. `MinMaxScaler` o `RobustScaler`).
    *   Registrar el impacto de la normalización en el tiempo de convergencia y la precisión final.

## 2. Ampliación de los Modelos de Clasificación
Actualmente se utiliza Random Forest. Se requiere integrar nuevos algoritmos para tener un benchmark más robusto.

*   **Modelos de Aprendizaje Tradicional:**
    *   Implementar un modelo **SVM (Support Vector Machine)** o **KNN (K-Nearest Neighbors)** utilizando las mismas características tabulares que recibe el Random Forest.
*   **Modelos de Deep Learning:**
    *   Implementar una **CNN Simple (Red Neuronal Convolucional)**. Esta red tomará las imágenes redimensionadas (no las características GLCM/OpenCV) y aprenderá los patrones de forma automática. 

## 3. Análisis de Errores y Matriz de Confusión
Se debe profundizar en el análisis de las métricas obtenidas.

*   **Matriz de Confusión:**
    *   Generar una matriz de confusión detallada para los 30 tipos de manzanas.
*   **Análisis de Confusión entre Clases:**
    *   Identificar específicamente **qué clases se confunden más entre sí**.
    *   Extraer y visualizar ejemplos de estas confusiones (Falsos Positivos / Falsos Negativos) para tratar de comprender visualmente por qué los modelos fallan (por ejemplo, variedades que tienen colores y formas casi idénticas).

## 4. Discusión Teórica y de Limitaciones
Como parte de la entrega, el documento o notebook debe incluir una reflexión crítica sobre los datos utilizados.

*   **Limitaciones del Dataset de Kaggle (Fruits 360):**
    *   Discutir la falta de variabilidad de fondo (las imágenes suelen tener fondos blancos perfectos que facilitan demasiado la segmentación).
    *   Analizar las condiciones de iluminación controlada versus escenarios de la vida real (ej. iluminación variable en una fábrica).
    *   Concluir sobre la capacidad real de generalización del modelo si este fuera desplegado en un entorno productivo real.
