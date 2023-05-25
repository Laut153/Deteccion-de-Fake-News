# Deteccion de Fake News
En el siguiente trabajo se propuso desarrollar un algoritmo de aprendizaje automatico que mediante la utilización de técnicas del Procesamiento del Lenguaje Natural (PLN), se pueda clasificar si una noticia será verdadera o falsa.

Para la prueba de concepto se utilizó los datos de [Kaggle](https://www.kaggle.com/datasets/arseniitretiakov/noticias-falsas-en-espaol), donde se presentan distintos artículos ya clasificados como verdaderos o falsos. Los utilizados para el desarrollo fueron onlytrue1000 y onlyfakes1000, ambos están en formato cvs y como se puede ver en el título, se cuenta con 1000 noticias verdaderas y 1000 noticias falsas.
 
Una vez cargadas las diferentes noticias, se les aplicó técnicas de PLN para que puedan ser ingresadas como datos de entrada en un modelo de aprendizaje automatico. Los procesos que se realizaron fueron los siguientes: eliminación de numeros como signos de puntuación, minusculización del artículo, generación de tokens (transformación del articulo a una secuencia de palabras que contienen la información acerca del lenguaje utilizado), filtrado de palabras que no aportan información al análisis (Stop Words), y agrupamiento de las diferentes palabras con un token que las represente (ejemplos: las palabras corrió, corría, corriendo, se agruparán con correr)

Para facilitár la visualización de la diferencia que existe entre las noticias verdaderas como falsas se generaron distintas gráficas de nubes de palabras. La palabra que se encuentre con mayór tamaño será la que se repite con mayor frecuencia.

Nube de palabras de noticias verdaderas:

![image](https://github.com/Laut153/Deteccion-de-Fake-News/assets/75812390/871820c0-b1c7-4dcb-9d80-0954e4216bc6) </br>
Se puede observar que las palabras que mayormente se repiten son año, ser y él, seguidos por poder, segun, tras y día. 

Nube de palabras de noticias falsas:

![image](https://github.com/Laut153/Deteccion-de-Fake-News/assets/75812390/e3713dc5-1bad-4b76-a51f-5a4151b20903) </br>
Se puede observar que las palabras que mayormente se repiten son año, ser y él, poder y hacer, seguidos por si. 

Como se puede ver, con el análisis de las nubes de palabras se podría clasificar si una noticia es verdadera o falsa, pero tardaría mas tiempo lograr la clasificación. Por eso se propuso la creación de un algoritmo de aprendizaje automatico, ya que generaría la clasificación de forma eficiente. 

De la prueba de distintos modelos de aprendizaje automático, el que mejores resultados obtuvo fué el de Maquinas de Vectores de Soporte (SVM), con una exactitud (accuracy) igual a 79%, significando que en el 79% de los casos el modelo funcionará correctamente. Para facilitár la comprensión del funcionamiento del modelo se presenta una matriz de confusión:

![image](https://github.com/Laut153/Deteccion-de-Fake-News/assets/75812390/2c154d1a-41e2-4d7f-83b3-7834a23ac653) </br>
De la matriz de confución, se puede observar que en un 77% de las observaciones que se predijeron como falsas se clasificaron de manera correcta, mientras que solo 23% de ellas fueron clasificadas incorrectamente. Por otro lado, un 82% de las noticias que eran verdaderas fueron clasificadas correctamente, mientras que un 18% de los casos fue identificada de forma incorrecta.

Por ultimo, una vez comprobado el funcionamiento del algoritmo se exportará el modelo de producción para su futura utilización en problemas del mundo real.
