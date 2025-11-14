# Python for data Analytics -  SmartBank

Realizar un análisis exploratorio del dataset asignado para comprender su estructura, calidad y
contenido. Este primer entregable busca que conozcan a fondo la información con la que
trabajarán, identificando posibles problemas de calidad de datos y visualizando sus principales
características antes de avanzar al análisis o modelado.


# Introduccion

El conjunto de datos (PFDA_bank_campaigns.csv) analizado está destinado a la predicción de
la suscripción de depósitos a plazo por parte de clientes bancarios. Las dimensiones del dataset
se confirman en 41,188 registros (filas) y 18 variables (columnas). Esta cantidad de
observaciones se considera robusta para el desarrollo de modelos predictivos.

## Diagnóstico de Calidad de Datos

## Consistencia y Duplicados
La integridad estructural del conjunto de datos es elevada, ya que el análisis de duplicados no
identificó ninguna fila totalmente repetida. Esto asegura que cada observación es única y no
sesgará el análisis o el entrenamiento del modelo por redundancia de datos.
Valores Nulos
Se identificó la presencia de valores nulos, que requieren un proceso de imputación o
tratamiento antes del modelado. Las columnas afectadas y el conteo de valores faltantes son:

• job: 2,100 nulos.

• education: 1,276 nulos.

• age: 576 nulos.

• duration: 864 nulos.




## Distribuciones

![Distribución de la variable edad](ScreenDistribucion)

El histograma de la variable age muestra una distribución sesgada hacia la derecha. La gran
mayoría de los clientes se concentra en el rango de 30 a 40 años, y la frecuencia disminuye
significativamente después de los 60 años. Esto es un hallazgo relevante para el perfilamiento
del cliente y para la posible segmentación o discretización de la edad.

![Distribución de la variable job.](ScreenDistribucion)

El gráfico de conteo de la variable job revela que el grueso de la base de clientes bancarios se
concentra en las categorías de "admin." y "blue-collar", siendo estos dos grupos los más
numerosos en el dataset, superando los 8,500 registros cada uno. Les siguen en importancia los
clientes clasificados como "technician" y "services", mientras que las categorías de menor
representación incluyen a los "unknown" (desconocido), "housemaid" y "unemployed".

![Relación entre age y duration.](ScreenDistribucion)

El gráfico de líneas que compara la duration promedio de la llamada en función de la age (edad)
del cliente revela una tendencia general de estabilidad en la duración del contacto para la mayor
parte de la población objetivo. Específicamente, entre los 25 y los 60 años, la duración
promedio se mantiene notablemente consistente, oscilando ligeramente alrededor de los 250 a
300 segundos. Sin embargo, se observa una mayor volatilidad e incrementos significativos en la
duración promedio para los extremos del rango de edad, es decir, clientes muy jóvenes (menores
de 25 años) y, de forma mucho más marcada, para los clientes de la tercera edad (mayores de 65
años). Este patrón sugiere que los segmentos más jóvenes y, especialmente, los de mayor edad,
requieren tiempos de explicación considerablemente más largos, lo cual podría indicar una
mayor necesidad de información detallada, o simplemente una mayor disposición a conversar,
siendo un factor clave a considerar en la asignación de recursos y estrategias de contacto.
