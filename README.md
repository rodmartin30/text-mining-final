# Chat dialogs labelling - Final project Text Mining

### Objetivo

Dado un conjunto de textos proveniente de una conversacion queremos identificar los temas que se fueron hablando por secciones.

Por ejemplo: Supongamos que al programa (Clasificador), le damos como entrada una conversacion con un amigo. El objetivo es que podamos obtener de una manera visual las secciones de los diferentes temas como asi tambien el tema que se estuvo discutiendo.


### Aproximación

Cuestiones para tener en cuenta en el proyecto es que las etiquetas van a estar fijas y van a ser en base al corpus de entrenamiento. Este corpus de entrenamiento debe ser generado a partir de conversaciones personales.

El primer paso en el proyecto es la obtención del Corpus. Este paso se dificulta por el hecho de que las conversaciones son personales. Una forma de obtener chats fue recolectar conversaciones de grupos de whatsapp y chats propios.

La idea del approach es de utilizar un corpus para etiquetar conversaciones y con esos ejemplos ya etiquetados poder entrenar un clasificador. 

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

* Suma y promedio con embeddings con fastText

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



### Trabajo a futuro

* Corpus mas grande y especificos del lenguaje 

* Investigar con Sent2Vec de gensim

* Mejorar el clusterizado

### Instalacion y uso

Instalación de requerimientos

`pip install -r requirements.txt`

### Referencias