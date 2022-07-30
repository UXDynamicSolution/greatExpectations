# TUTORIAL GREAT EXPECTATIONS

#instalar great expectations

'pip install great_expectations'


#inicializar repositorio

great_expectations init

#- Run `great_expectations datasource new` to connect to your data.

great_expectations datasource new


#SELECCIONAR ORIGEN DE DATOS
What data would you like Great Expectations to connect to?
    1. Files on a filesystem (for processing with Pandas or Spark)
    2. Relational database (SQL)


SELECCIONAR CON QUE HERRAMIENTA SE PROCESARAN LOS DATOS
What are you processing your files with?
1. Pandas
2. PySpark


SE DESPLIEGA UN JUPYTER NOTEBOOK:

CREAMOS UN NUEVO DATASOURCE Y EJECUTAMOS LAS CELDAS EN EL NOTEBOOK
datasource_name = "prueba_ds"

VALIDAR SI EXISTE EL DATASOURCE
great_expectations datasource list


AHORA CREAREMOS LAS REGLAS DE CALIDAD, GENERAMOS LA SUITE QUE ES LA AGRUPACION DE EXPECTATIONS
great_expectations --v3-api suite new --no-jupyter


Nos entrega 3 opciones de generacion de expectativas

How would you like to create your Expectation Suite?
    1. Manually, without interacting with a sample batch of data (default)
    2. Interactively, with a sample batch of data
    3. Automatically, using a profiler  # infiere de forma automatica las reglas de calidad
: 

Seleccionamos la opcion 3 para que genere automaticamente las reglas de calidad en base a sugerencia y luego enter para conservar 


# ABRIMOS EL NOTEBOOK NUEVO GENERADO EN LA RUTA, EJECUTAMOS Y VEMOS LAS REGLAS AUTOMÁTICAS QUE SE HAN GENERADO EN UN JSON


# EDITAR REGLAS SUITE GREAT EXPECTATIONS
great_expectations --v3-api suite edit VAPORESSN.csv.warning

podemos ir editando las reglas, cambiando parámetros, orden, etc...


ENCONTRAMOS REGLAS
https://legacy.docs.greatexpectations.io/en/0.12.0/reference/glossary_of_expectations.html


GENERAR DOCUMENTACION
great_expectations --v3-api docs build


COMO APLICAR UN CONJUNTO DE REGLAS DE CALIDAD DE DATOS A UN DATASET
great_expectations --v3-api checkpoint new myckp --no-jupyter

EJECUTAR UN CHECKPOINT: TOMA LAS REGLAS DE CALIDAD Y LO APLICA AL DATASET
great_expectations --v3-api checkpoint run myckp
