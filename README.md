# OCEAN_dataset
Se han hecho las primeras lecturas del dataset.
El objetivo del proyecto será clasificar a cada persona dentro de los 5 grandes rasgos de la personalidad.
Surgen varios problemas debido a la naturaleza y gran dimensionalidad del dataset:
	1. Hay Nans en todas las columnas numéricas, solo hay tres columnas (categóricas las tres) las cuáles no tienen.
  	2. Dificultad a la hora de visualizar los datos, ¿Hacemos división en bloques del dataset?
	3. Duda de si hacer PCA, ya que hemos visto que hay mucha correlación entre las variables.

29/11/2024
Diferentes avances hechos, se ha solucionado el problema de los Nans para todas las columnas que tuvieran, teniendo en cuenta los diferentes bloques de atributos. Usando SimpleImputer, pero en algunos casos basándose en la moda y en otros en la mediana.

También se han vuelto numéricas las variables categóricas, se han combinado otras y las dos últimas se han eliminado por falta  de aporte de información.

Se han normalizado la mayoría de variables, las respuestas al ir del 1-5 no, veremos si hará falta.

Primeras aproximaciones al objetivo, hemos creado el umbral {Baja, Media, Alta} para cada rasgo y lo hemos aplicado para la media de respuestas de cada bloque de cuestiones, así se han creado 5 nuevas clasificaciones y fueron añadidas como variables al dataset.

¿Tendremos que pasar a numéricas estas variables?

05/11/2024
Hemos pasado a numéricas estas variables, creando unas nuevas: EXT_class_num, EST_class_num,...

Se hicieron cambios en el enfoque del dataset, los Nan de las respuestas a las cuestiones ya no se imputan por moda, ya que esto afectaría gravemente a la predicción, sino que son tratados como si fueran 0 que son valores también presentes en estas columnas. La interpretación hecha es que son respuestas a las que la persona encuestada no quiso responder, entonces no se tendrán en cuenta a la hora de la clasificación, haremos la media de las respuestas con los valores diferentes a 0.

Se han hecho más gráficos e histogramas para visualizar el rango de respuestas a las preguntas y también para la cantidad de personas en cada umbral de cada rasgo. Además de ver si hay correlación entre las respuestas de las preguntas y el tiempo que se tarda en responder, que viendo las matrices observamos que no hay prácticamente.

También normalizamos las columnas que no fueran las de respuestas, porque tenían valores muy amplios. 

Y ya se procedió a visualizar métricas, primero para el primer rasgo, EXTRAVERSIÓN, probamos con un LogisticRegression() e hicimos un classification_report().

Posterior a esto, la idea ya fue ejecutar con el train y test para los distintos modelos seleccionados.

Ahora la siguiente cuestión es ver si haciendo PCA obtenemos una mejora en los tiempos y en el f1_score.
11/11/2024
Durante estos días se han descartado la idea del PCA ya que no reducía tiempos ni mejoraba el f1_score.

Ejecutamos los distintos modelos, mucho tiempo de ejecución sobre todo en el KNN que se ve que no es efectivo,

Comparación de modelos y de Matrices de Confusión.

CrossValidation con la desviación estándar aunque se han perdido algún valor de algún rasgo por error en el Kernel al tardar tanto en ejecutarse. Pero se ve muy poca variación.

Muchas dificultades para buscar hiperparámetros y regularización por el coste computacional que supone por la gran dimensionalidad.

Finalización del proyecto.





