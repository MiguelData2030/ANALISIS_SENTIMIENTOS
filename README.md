# ANALISIS_SENTIMIENTOS
Resultados_de Analisis en la Compra de Alexa

<div id="header" align="center">
    <img src="alexaamazon.jpg" width="600" />
    
1. Primero, se realiza un preprocesamiento de los datos de texto en el DataFrame `df`. Se eliminan los caracteres no alfabéticos, se convierten todas las letras a minúsculas y se aplica la técnica de stemming utilizando el algoritmo de Porter. Además, se eliminan las palabras de parada (stop words) en inglés, excepto algunas específicas.

2. A continuación, se utiliza `CountVectorizer` de scikit-learn para convertir el corpus de texto preprocesado en una representación de características numéricas. El objeto `vectorizer` se ajusta a los datos de texto (`corpus`) y se transforma en una matriz de término-documento (`X`) utilizando `X = vectorizer.fit_transform(corpus)`. Esto asigna un valor numérico a cada palabra del corpus basado en su frecuencia en el texto.

3. Luego, se dividen los datos en conjuntos de entrenamiento y prueba utilizando `train_test_split` de scikit-learn. El conjunto de entrenamiento se utiliza para entrenar el modelo y el conjunto de prueba se utiliza para evaluar el rendimiento del modelo. El parámetro `test_size=0.2` especifica que el 20% de los datos se utilizarán para el conjunto de prueba, mientras que `random_state=1` establece una semilla para la reproducibilidad.

4. Se crea una instancia del clasificador `MultinomialNB` y se ajusta al conjunto de entrenamiento utilizando `clasificador.fit(X_train, y_train)`. Esto entrena el modelo de clasificación utilizando los datos de entrenamiento.

5. Luego, se realizan predicciones en el conjunto de prueba utilizando `y_pred = clasificador.predict(X_test)`. El modelo clasifica las características numéricas (`X_test`) en etiquetas de retroalimentación positivas o negativas (`y_pred`).

6. Finalmente, se evalúa el rendimiento del modelo calculando la precisión utilizando `accuracy_score` de scikit-learn. La precisión se calcula comparando las etiquetas reales (`y_test`) con las etiquetas predichas (`y_pred`), y se almacena en la variable `ACC`.

El algoritmo utiliza el modelo de clasificación Naive Bayes y se entrena con las características numéricas de las palabras extraídas del corpus de texto. Luego, clasifica los datos de prueba en positivos o negativos en función de la retroalimentación del algoritmo Naive Bayes.


