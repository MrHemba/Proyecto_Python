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

<img width="876" height="692" alt="Image" src="https://github.com/user-attachments/assets/f88ab5ae-8402-4fd9-9d19-30acfb6fef3b" />

El histograma de la variable age muestra una distribución sesgada hacia la derecha. La gran
mayoría de los clientes se concentra en el rango de 30 a 40 años, y la frecuencia disminuye
significativamente después de los 60 años. Esto es un hallazgo relevante para el perfilamiento
del cliente y para la posible segmentación o discretización de la edad.

<img width="786" height="719" alt="Image" src="https://github.com/user-attachments/assets/9af7b76a-9d78-49cd-b8b8-36dc13be1d3e" />

El gráfico de conteo de la variable job revela que el grueso de la base de clientes bancarios se
concentra en las categorías de "admin." y "blue-collar", siendo estos dos grupos los más
numerosos en el dataset, superando los 8,500 registros cada uno. Les siguen en importancia los
clientes clasificados como "technician" y "services", mientras que las categorías de menor
representación incluyen a los "unknown" (desconocido), "housemaid" y "unemployed".

<img width="895" height="719" alt="Image" src="https://github.com/user-attachments/assets/f0b1267a-ba6b-4a10-9edc-dea5c1cb2061" />

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

## Análisis orientado a responder las preguntas

### ¿Cuál es el mejor canal de contacto?
<img width="536" height="399" alt="Image" src="https://github.com/user-attachments/assets/db635da8-8a8f-4757-b00e-821a074ba9c7" />

El gráfico muestra que la probabilidad de que un cliente acepte el depósito a plazo es mucho mayor cuando se le contacta por celular  que por teléfono fijo. 

El celular es claramente el canal más efectivo para esta campaña de telemarketing. 


### ¿Qué combinación de canal de contacto y rango de edad genera mayor probabilidad de aceptación?
<img width="855" height="475" alt="Image" src="https://github.com/user-attachments/assets/7c54c019-8a81-4ac3-b69b-07abd5f4bd4e" />

Entre los clientes contactados por celular, los rangos de edad 15–24 y sobre todo 65+ tienen las tasas de aceptación más altas, mientras que los grupos intermedios (25–54) muestran niveles bastante menores.

Al usar el canal celular, conviene priorizar a jóvenes y adultos mayores, ya que son los segmentos que responden mejor al depósito a plazo. 


### ¿Cómo influye el resultado de campañas previas en la aceptación del depósito a plazo?
<img width="531" height="392" alt="Image" src="https://github.com/user-attachments/assets/c36b5b3d-b2c9-43f9-859e-f10f5fcf18de" />

El resultado previo de la campaña es un factor clave: si el cliente ya tuvo una experiencia exitosa, es mucho más probable que vuelva a aceptar el depósito a plazo.

Los clientes con resultado previo success tienen una probabilidad de aceptación mucho mayor que quienes tuvieron failure o nonexistent, cuyos niveles son bastante bajos.

<img width="885" height="567" alt="Image" src="https://github.com/user-attachments/assets/1b1901d0-203c-409b-b0a6-862b1d6d375c" />

Si el resultado previo fue exitoso, el nivel educativo deja de ser tan decisivo: en general, estos clientes son muy propensos a volver a aceptar el depósito a plazo.

El gráfico muestra que, entre los clientes que ya tuvieron campañas previas exitosas, la probabilidad de volver a aceptar el depósito es alta en todos los niveles de estudio



### ¿Cuántas llamadas son suficientes para concretar la mayoría de aceptaciones?
<img width="709" height="479" alt="Image" src="https://github.com/user-attachments/assets/6fa69658-4127-48c5-946d-3970b4c1be96" />

Para esta campaña, entre 1 y 3 llamadas son suficientes para concretar la gran mayoría de aceptaciones; hacer más de 3–4 intentos por cliente casi no aporta conversiones y solo consume recursos del equipo.

El gráfico muestra que la mayoría de las aceptaciones se consiguen con 1 o 2 llamadas, y una parte menor con 3 o 4. A partir de la 4.–5. llamada, el número de nuevas aceptaciones cae casi a cero.

## Datos adicionales obtenidos por analisis

### Patrones Relevantes
La mayoría de las aceptaciones se concentra entre 1 y 3 llamadas; más intentos casi no generan nuevos “yes”.

Los clientes con resultado previo success tienen una probabilidad de aceptación cercana al 65%, muy superior a failure y nonexistent.

Entre los contactos por celular, los grupos de edad 15–24 y 65+ son los que muestran mayor tasa de aceptación.

### Anomalías identificadas
El nivel educativo illiterate aparece con 100% de aceptación, lo que sugiere un grupo muy pequeño y poco representativo.

Se observan algunos casos con más de 10 llamadas y pocas aceptaciones, indicio de campañas muy insistentes con bajo retorno.

### Variables nuevas que ayudan
Creación de rango_edad y uso de la función tasa_conversion para comparar segmentos de forma clara.

### Hallazgos con valor para el banco
Focalizar campañas en clientes con éxito previo, contactados por celular y en edades 15–24 y 65+, limitando a 3 llamadas por cliente para usar mejor los recursos.


