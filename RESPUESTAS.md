# Respuestas

Indica tu nombre a continuación: Patricia Campos Medel

Por cada etapa agrega una sección abajo y escribe las respuestas a las preguntas de cada etapa.

## ETAPA 1

¿Cuál es la diferencia entre los archivos con el verbo `Create` con los archivos con el verbo `Add`?
Respuesta: 
Los archivos 'create' crean las tablas, los archivos 'Add' agregan registros a las tablas

¿Cómo se llama el servicio que se declara en el archivo `docker-compose.yml`?
Respuesta: 
se llama flyway

¿Cuál es el comando que se ejecuta en el servicio declarado?
Respuesta: 
-locations=filesystem:/flyway/sql -connectRetries=60 migrate 
Este comando Crea la base de datos y carga datos en las tablas

## ETAPA 2

¿Qué pasa si cambias el nombre del servicio de `postgres` a `db`? ¿Qué otros cambios tendrías que hacer?
Respuesta: 
si se cambia solo el nombre del servicio no se crea la bd se debe cambiar tambien el nombre en la dependencia del servicio flyway "depends_on:" 

## ETAPA 3
¿Qué te llama la atención?
Respuesta: 
Tiene el paso a paso para construir y hacer deploy de la api

¿Cómo se relacionan el archivo `docker-compose.yml` y el archivo `movies-api/Dockerfile`?
Respuesta: 
En el archivo docker-compose.yml se definen las variables de ambiente + directorios que usará el Dockerfile

¿Qué crees que hace el atributo `context` debajo de `build` (está en la linea 6 del archivo `docker-compose.yml`)?
Respuesta: 
en el context se define la ruta que usará el dockerfile para crear la imagen de la api

## ETAPA 4

Compara los archivos `Dockerfile` de `movies-api` y `movies-front`. 

¿Cuál es la diferencia? 
Respuesta: 
El dockerfile de movies-api construye la aplicación desde los fuentes y después hace un deploy del binario construido en una imagen
el dockerfile de movies-front instala la aplicación usando las dependencias que están dfinidas en package-json

Compara el atributo `build` del servicio `movies-api` con el de `movies-front`. 
¿Qué pasa si los dejas iguales?
Respuesta:
si de deja el front igual al de la api no puede instalar la aplicación
si se deja la api ugyual al del front no puede construir la api desde los fuentes