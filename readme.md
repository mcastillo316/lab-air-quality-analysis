Estás trabajando en una organización sin ánimo de lucro con sede en Estados Unidos.
Esta organización trabaja en la promoción de mejores condiciones medioambientales.
La organización ha iniciado recientemente una campaña de concienciación sobre el ozono
como contaminante. Su tarea consiste en identificar las principales regiones de EE.UU. 
con los niveles más altos de ozono, 
que se utilizarán en una campaña de concienciación regional en los medios sociales.

Solución

Tienes que realizar los siguientes pasos:
Encontrar un repositorio de datos de código abierto que contenga lecturas de la calidad del aire
Consultar esos datos utilizando los servicios y herramientas de AWS
Averiguar qué ciudad tiene la lectura de ozono más alta
Encontrarás datos de código abierto en https:\\registry.opendata.aws
AWS Glue Athena

1. Busca en "openaq" y haz click en detalles https://registry.opendata.aws/openaq/ 
2. Explora el bucket (browse bucket)
3. selecciona "realtime\" (Proporciona los datos, que sólo utilizaremos de la 
fecha reciente 2021/10/31).
4. ve a la consola de aws  y selecciona AWS Glue
5. Selecciona Crawler para descubrir la estructura de los datos del bucket y crearlos.
6. Crea un nuevo Crawler, dale el nombre de "Crawler-airQuality" clic en siguiente
	- Crawler source Type DataStores
	- Repeat crawls of s3 data stores selecciona crawl all folders
	- Crawl data in Specified path in another account y selecciona la ruta del S3 donde esta los archivos,
	  en este caso seria s3://openaq-fetches/realtime/2021-10-31
	- en Add another datastore clic en NO.
7. crear un IAM role AWSGlueServiceRole-nombre
8. en el schedule para el crawler, seleccionar run on demand.
9. en database crear una base de datos nueva openai
10. finalizar
11. en el listado de los crawler seleccionarlo y dar clic en run crawler

