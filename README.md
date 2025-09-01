# Clasificación de Emociones en Tweets
## Los modelos explorados incluyen:

Regresión Logística + TF-IDF (Baseline): Un modelo de referencia para establecer una línea base de rendimiento.

Red Neuronal Recurrente (LSTM): Un modelo de deep learning entrenado desde cero.

BERT Multilingual: Un modelo avanzado de Transformer ajustado (fine-tuned) para esta tarea.

Modelos Ensemble: Un conjunto de modelos que combina las predicciones de los modelos anteriores para mejorar la robustez.

El análisis incluye la evaluación de métricas de rendimiento por categoría, la visualización de matrices de confusión y una comparación de los resultados para identificar el mejor modelo.

## Instrucciones de Uso
Para ejecutar el notebook, se recomienda usar Google Colab debido a la necesidad de una GPU para entrenar el modelo BERT.

Abre el archivo NLP.ipynb en Google Colab.
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Luis24M/nlp_final/blob/main/NLP.ipynb)

Asegúrate de tener un entorno con GPU activado (Entorno de ejecución -> Cambiar tipo de entorno de ejecución -> Acelerador de hardware: GPU).

Sigue los pasos en el notebook, ejecutando las celdas en orden.

## ¡Importante! Configuración para el Finetuning de BERT
El fine-tuning del modelo BERT utiliza la librería huggingface y se integra con Weights & Biases (W&B) para el seguimiento del entrenamiento. Para que el proceso funcione correctamente, el notebook te pedirá una API Key.

Para obtener tu API Key, sigue estos pasos:

Visita el sitio web de W&B: https://wandb.ai/authorize?ref=models

Crea una cuenta o inicia sesión.

Tu API Key se mostrará en la página de autorización. Cópiala y pégala en la ventana emergente que aparecerá en el notebook durante el entrenamiento.

## Conclusiones del Proyecto
Los resultados del experimento mostraron que el modelo BERT Multilingual fue el más efectivo, superando a los demás modelos en las métricas clave de rendimiento (F1-Weighted y Accuracy). Esto resalta el poder de la transferencia de aprendizaje en el procesamiento de lenguaje natural. Se concluyó que, si bien los modelos ensemble mejoraron el rendimiento de los modelos base, no lograron superar la calidad de las predicciones del modelo pre-entrenado.

El principal desafío en el dataset fue el desequilibrio de clases, lo que afectó negativamente el rendimiento en las emociones minoritarias (disgust, fear, surprise) en todos los modelos.
