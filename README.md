# Detector de SMS spam con Machine Learning

Proyecto de clasificación de texto que identifica si un mensaje SMS es spam o legítimo (ham).

## Dataset
SMS Spam Collection (UCI Machine Learning Repository / Kaggle): 5.574 mensajes en inglés, 86,6% ham y 13,4% spam (clases desbalanceadas).

- UCI: https://archive.ics.uci.edu/dataset/228/sms+spam+collection
- Kaggle: https://www.kaggle.com/uciml/sms-spam-collection-dataset

## Herramientas
Python, pandas, scikit-learn, matplotlib, Google Colab.

## Metodología
1. Exploración de datos y análisis del desbalance de clases.
2. División en entrenamiento (80%) y prueba (20%) estratificada.
3. Vectorización del texto con TF-IDF.
4. Entrenamiento y comparación de dos modelos: Naive Bayes y Regresión Logística (con class_weight="balanced").

## Resultados
| Modelo | Precisión | Recall spam | F1 spam |
|---|---|---|---|
| Naive Bayes | 96,9% | 0,77 | 0,87 |
| Regresión Logística | 98,2% | 0,92 | 0,93 |

- Naive Bayes no marcó ningún mensaje legítimo como spam, pero dejó pasar 35 de 149 spam.
- La Regresión Logística redujo los spam no detectados a 12, a costa de 8 falsos positivos.
- Elegí la Regresión Logística como modelo final por su mejor equilibrio entre ambos errores.

## Demo
Mensajes de prueba escritos por mí:

| Mensaje | Predicción |
|---|---|
| Congratulations! You won a free prize. Click here to claim now | spam |
| Hey, are we still meeting for lunch tomorrow? | ham |
| URGENT! Your account has been selected for a cash reward. Call now | spam |

## Aprendizajes
- Con clases desbalanceadas, la precisión general no alcanza: hay que mirar recall y F1.
- Ajustar el peso de las clases mejora la detección de la clase minoritaria.

## Posibles mejoras
Probar otros modelos (SVM, redes neuronales), ajustar hiperparámetros y entrenar con mensajes en español.

## Autora
Nicole Ramirez - [LinkedIn](https://www.linkedin.com/in/nicole-ramirez-0a2a06294)
