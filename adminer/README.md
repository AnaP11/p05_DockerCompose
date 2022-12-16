***
## INSTRUCCIONES
***

1. Estando ubicados en el repositorio local, nos **movemos a la carpeta de adminer** mediante la terminal :

    ``cd .\adminer\``

2. **Generamos el escenario** multi-contenedor de adminer ejecutando el siguiente comando:
    ``docker compose up -d``

3. Esperamos a que se instalen los archivos correspondientes, y **accedemos en el navegador** al [puerto 8083](http://localhost:8083)

   También puedes acceder al botón lateral de Docker en el Visual SC, y hacer click derecho en el servicio adminer del multicontainer _adminer_ para abrirlo en el navegador (_Open in Browser_).

4. **Iniciamos sesión en adminer** a través del navegador:
   
   - Para ello, utilizamos el usuario **root** y la contraseña **anapcontra** 

6. Para **finalizar el proceso de esta aplicación**, se puede hacer click derecho al multicontainer _adminer_ y seleccionar _Compose Stop_, o bien parar la ejecución mediante comando :

    ``docker-compose stop``

    Este paso te lo puedes saltar si quieres seguir probando el resto de aplicaciones (y también si tienes un ordenador que aguante los procesos), ya que cada aplicación puede correr a la vez y tienen todos distintos puertos, por lo que no daría problemas de conexión entre ellas.

    Pero eso sí: **si ya no quieres seguir probando más escenarios, es conveniente que primero ejecutes el comando de _Compose Stop_ de cada escenario/multi-contenedor y luego cierres las aplicaciones de tu ordenador**

***
## REFERENCIAS
***

* Apuntes de clase : [Docker Compose](https://docs.google.com/document/d/1gP0NFSej29oNDjU40f1uoAZP40tXoCN0_FqaKGWxnOw/edit#heading=h.lxcb1oq76810)

* Apuntes de clase : [Curso Docker](https://docs.google.com/document/d/1RNZN8G8lspbvcrXw_im7IgoMS7e5kS05GtlfdV6zdnU/edit)

* Documentación oficial : [Adminer en DockerHub](https://hub.docker.com/_/adminer)