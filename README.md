# Machine-Learning-Clustering
Flujo de Ciencia de Datos y Machine Learning que analiza a +600 estudiantes en Portugal. Combina estadística avanzada, PCA, Clustering y Redes Neuronales para predecir el rendimiento escolar, identificar perfiles de riesgo y diseñar intervenciones educativas tempranas basadas en evidencia.

## Metodología y Pipeline de Desarrollo

### 1. Manipulación y Exploración de Datos (EDA)
* **Limpieza:** Se verificó la ausencia total de registros duplicados o valores nulos (0 valores faltantes en todas las columnas), garantizando una estructura limpia y completa.
* **Tratamiento de Outliers:** Mediante diagramas de caja (*Boxplot*) se identificó un 2.00% de valores atípicos (13 casos extremos en total). Se tomó la decisión justificada de **no eliminarlos**, dado que representan realidades del entorno educativo (absentismo elevado, consumos altos de alcohol, situaciones límite) clave para la detección de perfiles de riesgo.
* **Análisis Estadístico:** * **Correlación de Pearson:** Utilizada para evaluar relaciones lineales en variables cuantitativas/ordinales. Demostró que el historial de fracasos académicos previos (failures) y las notas parciales son los predictores lineales más fuertes.
    * **Cramér's V:** Aplicado a variables cualitativas y nominales. Reveló que los factores institucionales (school), las aspiraciones del alumno (higher - deseo de cursar estudios superiores) y motivos de elección de centro (reason) presentan la mayor asociación con la categoría de la nota.
### 2. Reducción de la Dimensionalidad (PCA)
Se implementó un **Análisis de Componentes Principales (PCA)** sobre 13 variables numéricas y ordinales previamente estandarizadas (`StandardScaler`). Las variables ordinales se preservaron cuantitativamente para capturar gradientes conductuales continuos sin destruir su orden inherente mediante codificaciones artificiales. El objetivo de PCA es mapear estructuras latentes que agrupen comportamientos y hábitos estudiantiles.

### 3. Segmentación (Clustering)
Uso de técnicas no supervisadas (como K-Means) destinadas a descubrir y mapear de manera natural perfiles de estudiantes homogéneos (ej. estudiantes con alta constancia, estudiantes motivados pero con baja dedicación o perfiles de alto riesgo) sin utilizar directamente la calificación final para evitar sesgos en la construcción del grupo.

### 4. Modelado Predictivo (Clasificación Supervisada)
Implementación y evaluación de algoritmos con enfoques contrapuestos para analizar el compromiso entre precisión matemática e interpretabilidad en escenarios escolares reales:
* **Árboles de Decisión:** Priorizando la transparencia en las reglas de decisión pedagógica.
* **Redes Neuronales:** Buscando la máxima capacidad predictiva y optimización en las clasificaciones.

---

## Tecnologías Utilizadas
El proyecto se ha desarrollado íntegramente en entornos de **Python** empleando las siguientes librerías de Ciencia de Datos:
* **Pandas & NumPy:** Carga, manipulación y limpieza de estructuras de datos.
* **Matplotlib & Seaborn:** Generación de gráficos estadísticos, mapas de calor, boxplots e histogramas.
* **Scipy (scipy.stats):** Computación de pruebas estadísticas de contingencia (Cramér's V).
* **Scikit-Learn (sklearn):** Preprocesamiento de datos (`StandardScaler`), reducción de dimensiones (PCA), algoritmos de clustering y modelos de clasificación supervisada.

---

## Autor
* **Estudiante:** Miriam Gómez Arias 
* **Asignatura:** Métodos estadísticos en minería de datos 
* **Institución:** Universidad Carlos III de Madrid (4° Curso)
