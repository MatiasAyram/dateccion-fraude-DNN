# Detección de Fraude con Redes Neuronales Profundas

Este proyecto implementa una red neuronal profunda (DNN) para detectar transacciones fraudulentas utilizando el dataset `creditcard.csv`.  
Es un ejemplo de cómo manejar un problema de clasificación con un conjunto de datos muy desbalanceado con técnicas de machine y deep learning.

## Descripción del flujo de trabajo
En el notebook se realiza el siguiente flujo de trabajo:
1. Carga y análisis exploratorio del dataset con 28 características.  
2. Evaluación de la importancia de las variables.  
3. Eliminación de las características menos relevantes.  
4. Escalado de los datos con `StandardScaler`.  
5. Aplicación de **SMOTE** para balancear las clases.  
6. Construcción y entrenamiento de una red neuronal profunda (DNN) usando Keras.  
7. Evaluación con métricas como **F1-score**, matriz de confusión y `classification_report`.  
8. Optimización del umbral de decisión (**threshold**) para mejorar el rendimiento.

## Instalación
para clonar el repositorio y preparar el entorno puede ejecutar en la consola:
```bash
git clone https://github.com/MatiasAyram/dateccion-fraude-DNN.git
cd dateccion-fraude-DNN
pip install -r requirements.txt
```
(El código fue desarrollado en un entorno virtual de Anaconda Navigator (Python 3.10).)

## Conjunto de datos
para descargar el conjunto de datos puede ir al siguente link y descargarlo de forma segura:
```text
https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud
```
El dataset contiene transacciones realizadas con tarjetas de crédito europeas en septiembre de 2013, y ha sido preprocesado para preservar la privacidad (mediante PCA en la mayoría de los atributos)
(El archivo creditcard.csv no se incluye en este repositorio debido a las limitaciones de tamaño de archivo en GitHub (100 MB))

## Resultados
luego de varias pruebas (con diferentes escaladores, semillas, selección de variablesy optimización de thresholds) se llego a los siguente valores de clasificacion:

Reporte de clasificación:(threshold=0.8899999999999996)
```text
              precision    recall  f1-score   support

           0       1.00      1.00      1.00     56864
           1       0.58      0.86      0.69        98

    accuracy                           1.00     56962
   macro avg       0.79      0.93      0.85     56962
weighted avg       1.00      1.00      1.00     56962
```
A pesar de aplicar SMOTE, el modelo presenta desafíos al clasificar correctamente la clase 1, aunque logra buenos valores relativos dada la alta desproporción de clases en el conjunto original.

## License
 este proyecto esta licenciado bajo la licencia MIT License

---



