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


