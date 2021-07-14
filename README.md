# Análisis de Datos de Anime: Tópicos, Modelo Predictivo y un Recomendador

Para este proyecto se utilizaron datos obtenidos de https://www.kaggle.com/hernan4444/anime-recommendation-database-2020


## Anime_Topic_Analisis.ipynb

En este proyecto se desarrolló un análisis de tópicos sobre los resúmenes de los animes que se encontraron en el dataset, realizando un pequeño análisis de la evolución de 
estos en el tiempo. Luego utilizando los resultados del análisis de tópicos y los distintos features que se pudieron obtener del dataset se generó un modelo predictivo de la 
popularidad de un dado Anime. Para definir la popularidad se utilizó como target el logaritmo en base 10 del número de usuarios que interactuaron con cada anime. Luego 
para realizar las predicciones se utilizaron únicamente los features que no tienen que ver con la respuesta de los usuarios al anime (es decir que no se tomaron en cuenta 
features como la cantidad de usuarios que agregaron a favoritos o votaron en un dado anime). Un feature que se consideró para el análisis inicial fue la puntuación de cada 
anime. Con este se logró obtener una performance de 0.827 con un modelo de Random Forest. Luego se evaluaron también los resultados descartando este valor ya que resultó 
cuestionable si este feature sería posible de obtener de antemano en la práctica. Para este modelo se obtuvo una performance de 0.73, la cual resulta un 10% menor a la anterior, 
pero aún aceptable.

## Recomendador_KNN.ipynb

Por otro lado se trabajó en la elaboración de un modelo recomendador, basado en un modelo KNN para encontrar los vecinos más cercanos. Para esto se utilizaron datos correspondientes 
a 5000 usuarios para los cuales se tenía indicado con un 1 si un dado anime le gusto, un -1 si no le gusto y un 0 si no lo vio (o no dio opinión). Luego se desarrolló una función
para tomar las columnas correspondientes a los animes que un usuario vio para luego compararlos con los datos del resto del dataset y mediante el modelo KNN obtener los vecinos más 
cercanos. A continuación de esto se evalúan cuáles fueron los animes que más gustaron a estos vecinos y que el usuario en cuestión aún no a visto, obteniendo de esta manera la 
lista de recomendación. Por último se desarrolló una función para hacer posible el cálculo de una matriz de confusión para poder evaluar la performance del modelo, obteniendo 
una sensibilidad de 0.931, especificidad de 0.112, accuracy de 0.842, precisión de 0.896. Dado que se trata de un recomendador, lo más importante es que lo que se le recomienda al 
usuario le termine gustando, es decir la precisión, para la cual se obtuvieron muy buenos resultados. 

