# Percepción del Consumidor y Análisis de Sentimientos en Reseñas de E-Commerce

Este proyecto tiene como objetivo analizar la percepción del consumidor a través del análisis de sentimientos en las reseñas de productos en plataformas de comercio electrónico. Utilizamos modelos de análisis de sentimientos como VADER y RoBERTa para evaluar el sentimiento expresado en las reseñas y compararlos para determinar cuál proporciona una mejor comprensión de la satisfacción del cliente.

## Contenido

1. [Descripción del Proyecto](#descripción-del-proyecto)
2. [Metodología](#metodología)
3. [Resultados](#resultados)
4. [Métricas](#métricas)

## Descripción del Proyecto

El proyecto analiza las reseñas de productos de Amazon utilizando técnicas de procesamiento de lenguaje natural (NLP). Se utilizan dos modelos principales de análisis de sentimientos: VADER y RoBERTa. Los resultados de ambos modelos se comparan utilizando métricas como la curva ROC y el área bajo la curva (AUC).

## Instalación

Para ejecutar este proyecto, necesitas tener instalado Python 3 y las siguientes bibliotecas:

- pandas
- numpy
- matplotlib
- seaborn
- nltk
- tqdm
- transformers
- scipy

## Metodología 

### Preparación de Datos
- Se cargan las reseñas de productos desde un archivo CSV.
- Se seleccionan las primeras 500 reseñas para el análisis inicial.
### Análisis de Sentimientos
Con VADER
- Se utiliza la clase SentimentIntensityAnalyzer de NLTK para calcular las puntuaciones de sentimiento de cada reseña.
- Las puntuaciones se almacenan en un DataFrame para su posterior análisis.
Con RoBERTa
- Se utiliza el modelo preentrenado de RoBERTa para calcular las puntuaciones de sentimiento de cada reseña.
- Las puntuaciones se almacenan en un DataFrame y se comparan con las puntuaciones de VADER.
### Visualización de Resultados
- Se generan gráficos de barras para visualizar la distribución de las puntuaciones de sentimiento.
- Se crea un pairplot para comparar las puntuaciones de sentimiento de VADER y RoBERTa.

## Resultados
Los resultados muestran cómo varían las puntuaciones de sentimiento según las diferentes puntuaciones de las reseñas (de 1 a 5 estrellas). Se observa una mayor consistencia en las puntuaciones de sentimiento positivas y negativas cuando se utilizan ambos modelos, aunque RoBERTa tiende a proporcionar una mejor discriminación entre las reseñas positivas y negativas.

## Métricas Usadas

### Área Bajo la Curva (AUC)

- **Descripción**: El AUC es una métrica utilizada para evaluar la capacidad de un modelo de clasificar correctamente las muestras. Representa el área bajo la curva ROC (Receiver Operating Characteristic).
- **Interpretación**: Un AUC más cercano a 1 indica un mejor rendimiento del modelo, ya que refleja una mayor capacidad para distinguir entre clases positivas y negativas. Un AUC de 0.5 indica que el modelo no tiene capacidad discriminativa mejor que el azar.

### Curva ROC (Receiver Operating Characteristic)

- **Descripción**: La curva ROC es una representación gráfica del rendimiento de un modelo de clasificación binaria. Muestra la relación entre la tasa de verdaderos positivos (TPR) y la tasa de falsos positivos (FPR) a diferentes umbrales de clasificación.
- **Interpretación**: Una curva ROC que se acerca más a la esquina superior izquierda indica un mejor rendimiento del modelo. La diagonal (línea de 45 grados) representa un rendimiento aleatorio.

### F1 Score

- **Descripción**: El F1 Score es la media armónica de la precisión y el recall. Es una métrica balanceada que considera tanto falsos positivos como falsos negativos.
- **Interpretación**: Un F1 Score alto indica que el modelo tiene tanto una alta precisión como un alto recall, lo que refleja un buen rendimiento general.

### Recall (Sensibilidad)

- **Descripción**: El recall es la proporción de verdaderos positivos que son correctamente identificados por el modelo.
- **Interpretación**: Un recall alto indica que el modelo es capaz de identificar la mayoría de las muestras positivas.

### Accuracy (Exactitud)

- **Descripción**: La accuracy es la proporción de predicciones correctas (tanto verdaderos positivos como verdaderos negativos) entre el total de predicciones.
- **Interpretación**: Una alta accuracy indica que el modelo clasifica correctamente la mayoría de las muestras.

### Precision (Precisión)

- **Descripción**: La precisión es la proporción de verdaderos positivos entre el total de predicciones positivas.
- **Interpretación**: Una alta precisión indica que la mayoría de las predicciones positivas del modelo son correctas.

## Datos 

Los datos empleados los podrán encontrar en Kaggle en el siguiente link: https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews
