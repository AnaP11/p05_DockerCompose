La entrega consiste en un enlace a un repositorio en GitHub con un directorio por aplicación o servicio a desplegar (según el caso), y un README.md con instrucciones para cada despliegue en local (muchas veces no basta con lanzar el comando docker compose up -d, sino que hay que hacer otras configuraciones adicionales) y referencias de donde se haya obtenido la información. Para su calificación se clonará el repositorio y se ejecutarán las instrucciones que se hayan indicado. 

***
# INTRODUCCIÓN

El presente repositorio aloja la configuración y creación de cinco escenarios multi-contenedor utilizando la tecnología de Docker Compose.

* Servidor web Apache
* Mediawiki 
* Guestbook 
* Wordpress 
* adminer 


***
# INSTRUCCIONES


## Pasos iniciales : software necesario y preparación del entorno

Para comenzar a disfrutar del despliegue de estas aplicaciones, es necesario que tengas el Docker Desktop instalado _**y siempre corriendo**_. 

También necesitarás descargar la imagen de docker compose (en el caso de que aún no la tengas instalada) para poder ejecutar los comandos que te permitirán inicializar las aplicaciones en tu ordenador.

Cabe decir que el proceso de creación de los escenarios se realizó exitosamente con una de las versiones más recientes de Docker Desktop (v4.14.1), bajo la versión 20.10.21 de  Engine, y con la versión 2.12.2 de Compose.

Para la ejecución de los comandos necesarios, puedes utilizar una terminal desde Visual Studio Code, la cual puede resultarte más intuitiva (y es altamente recomendable en este caso). En este caso, también podrás descargar la extensión Docker y la de Dev Containers, ambas de Microsoft, en el caso de que desees experimentar todas las características de Docker de una forma incluso más sencilla e intuitiva.

¡Ahora mismo puedes clonar este repositorio en tu repositorio local!
(Puedes utilizar la aplicación Git-Bash)


Una vez iniciadas las anteriores aplicaciones, a continuación abre una terminal en Visual Studio Code y ubícate en el directorio donde has clonado este repositorio mediante ``cd [la\ruta\al\directorio]``

A partir de aquí, deberás ejecutar una serie de comandos dependiendo de la aplicación que quieras probar:

* Servidor web Apache

* Mediawiki 

* Guestbook 

* Wordpress 

* adminer 

***
# ACERCA DE

Practica correspondiente al módulo de Despliegue de Aplicaciones Web (2º del CFGS de Desarrollo de Apicaciones Web)