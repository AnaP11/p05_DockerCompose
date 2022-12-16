***
## INSTRUCCIONES
***

1. Estando ubicados en el repositorio local, nos **movemos a la carpeta de servidor_web_apache** mediante la terminal :

    ``cd .\servidor_web_apache\``

2. **Generamos el escenario** multi-contenedor de apache ejecutando el siguiente comando:
    ``docker compose up -d``

3. Esperamos a que se instalen los archivos correspondientes, y **accedemos en el navegador** al [puerto 8080](http://localhost:8080)

   También puedes acceder al botón lateral de Docker en el Visual SC, y hacer click derecho en el servicio httpd del multicontainer _servidor_web_apache_ para abrirlo en el navegador (_Open in Browser_).

4. Para **finalizar el proceso de esta aplicación**, se puede hacer click derecho al multicontainer _servidor_web_apache_ y seleccionar _Compose Stop_, o bien parar la ejecución mediante comando :

    ``docker-compose stop``

    Este paso te lo puedes saltar si quieres seguir probando el resto de aplicaciones (y también si tienes un ordenador que aguante los procesos), ya que cada aplicación puede correr a la vez y tienen todos distintos puertos, por lo que no daría problemas de conexión entre ellas.

    Pero eso sí: **si ya no quieres seguir probando más escenarios, es conveniente que primero ejecutes el comando de _Compose Stop_ de cada escenario/multi-contenedor y luego cierres las aplicaciones de tu ordenador**

***
## REFERENCIAS
***

* Apuntes de clase : [Docker Compose](https://docs.google.com/document/d/1gP0NFSej29oNDjU40f1uoAZP40tXoCN0_FqaKGWxnOw/edit#heading=h.lxcb1oq76810)

* Apuntes de clase : [Curso Docker](https://docs.google.com/document/d/1RNZN8G8lspbvcrXw_im7IgoMS7e5kS05GtlfdV6zdnU/edit)

* Documentación oficial : [Apache en DockerHub](https://hub.docker.com/_/httpd)