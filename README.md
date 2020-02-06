# Chat dialogs labelling - Final project Text Mining

### Objetivo

Dado un conjunto de textos proveniente de una conversacion queremos identificar los temas que se fueron hablando por secciones.

Por ejemplo: Supongamos que al programa (Clasificador), le damos como entrada una conversacion con un amigo. El objetivo es que podamos obtener de una manera visual las secciones de los diferentes temas hablados en esa conversacion como así tambien el tema que se estuvo discutiendo.

![](images/sample_nico.png)

En la imagen anterior podemos ver un ejemplo de una conversacion, lo que nosotros esperamos es que el modelo pueda identificar esta parte de la conversacion con temas relacionados a la universidad, estudio, etc.

![](images/sample_nico_labeled.png)

### Aproximación

Cuestiones para tener en cuenta en el proyecto es que las etiquetas van a estar fijas y van a ser en base al corpus de entrenamiento. Este corpus de entrenamiento debe ser generado a partir de conversaciones personales.

El primer paso en el proyecto es la obtención del Corpus. Este paso se dificulta por el hecho de que las conversaciones son personales. Una forma de obtener chats fue recolectar conversaciones de grupos de whatsapp y chats propios.

La idea del approach es de utilizar un corpus para etiquetar conversaciones y con esos ejemplos ya etiquetados poder entrenar un clasificador. La forma de etiquetar estas conversaciones que luego se usaran para entrenar el clasificador es a partir de un algoritmo de clustering en el cual a partir de los elementos de cada cluster, se generaliza el tema y se usa esa etiqueta para cada elemento de ese cluster.

Se tiene que destacar que la mayor parte del projecto consiste en generar estos ejemplos para el clasificador, ya que de esto dependera de la calidad de las predicciones.



### Diagrama de flujo

![](images/flujo.png)

#### Preprocesamiento

El objetivo de este paso es normalizar el corpus. Este paso nos permitira obtener mejores resultados en las siguientes etapas, es una parte critica para el proyecto. Dentro de las acciones realizadas tenemos:

*  Creación de unidad, los cuales son conjuntos de mensajes enviados sin interrupción por un mismo usuario, con un threshold de X minutos.
*  Normalizar algunas palabras utilizando expresiones regulares, esto nos permite por ejemplo remplazar 'jajaj' o 'jjaja' por 'jaja'
*  Eliminar caracteres repetidos. Por ejemplo 'holaaaa' por 'hola'
*  Remover stopwords, dígitos y palabras con menos de 3 caracteres.
*  Lematización. Este paso nos permite remplazar palabras por su raiz, ejemplo 'corriendo' por 'correr'
*  Remover unidades con menos de 6 palabras (Luego del preprocesamiento anterior).


#### Embeddings

* BAG con TF-IDF

* Doc2Vec gensim

* Promedio con embeddings con fastText (uso de subwords)

#### Clustering


### Datos de ejemplo

![](images/sample_chat.png)

- Aca se muestra una captura del corpus antes del procesamiento. 

### Topic detection en clustering.

### Topic discovery

### Aplicacion de retrieval o de que se habla en este grupo

### Visualization

*** Conversaciones en las qie se habla este tema, snipet en el que se habla el tema

### Resultados y comparaciones

### Desafios

* Diferentes dominios

* Palabras mal escritas

* Palabras personalizadas

* Mensajes en multimedia que son parte de la conversacion

* Inseguridad de donde empieza y termina un tema

* El corpus es de caracter personal por lo que dificulta la obtencion de ejemplos por temas de privacidad.

### Conclusiones

Como primera conclusion puedo destacar la dificultad del problema debido a que no existe una unica etiqueta que englobe a la conversacion, esto dificulta la forma de evaluación de la solución.

En el siguiente proyecto se pudo ver de una forma end-to-end el proceso de creacion de un proyecto de text mining. Desde el planteo del problema y la solucion, hasta los diferentes pasos como la obtencion del corpus, su pre-procesamiento, las visualizaciones de los datos, la formas de evaluar la presicion del mismo y como asi tambien lograr un prototipo.



### Trabajo a futuro

* Corpus mas grande y especificos del lenguaje, (se puede incluir tweets en español de temas especificos para mejorar el corpus.)

* Investigar con Sent2Vec de gensim

* Mejorar el clusterizado

### Instalacion y uso

Instalación de requerimientos

`pip install -r requirements.txt`

### Referencias

[Referencias de la propia materia.](https://sites.google.com/view/text-mining-2019/materiales?authuser=0)
[Preprocesado de corpus](https://kavita-ganesan.com/text-preprocessing-tutorial/#.XjU0mhMzYmp)
[Word2Vec y FastText Word Embedding en Gensim](https://towardsdatascience.com/word-embedding-with-word2vec-and-fasttext-a209c1d3e12c)
[Introduccion a Doc2Vec](https://medium.com/wisio/a-gentle-introduction-to-doc2vec-db3e8c0cce5e)
[Topic modelling](https://nlpforhackers.io/topic-modeling/)
[Curso de NLP de stanford](http://web.stanford.edu/class/cs224u/)
[Clasificador con regresion logistica](https://kavita-ganesan.com/news-classifier-with-logistic-regression-in-python/#.XjPCehMzYmo)
[Regresion logistica en python](https://towardsdatascience.com/logistic-regression-using-python-sklearn-numpy-mnist-handwriting-recognition-matplotlib-a6b31e2b166a)
