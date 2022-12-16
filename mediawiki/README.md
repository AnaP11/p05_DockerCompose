***
## INSTRUCCIONES
***

1. Estando ubicados en el repositorio local, nos **movemos a la carpeta de mediawiki** mediante la terminal :

    ``cd .\mediawiki\``

2. **Generamos el escenario** multi-contenedor de MediaWiki ejecutando el siguiente comando:
    ``docker compose up -d``

3. Esperamos a que se instalen los archivos correspondientes, y **accedemos en el navegador** al [puerto 8081](http://localhost:8081)

   También puedes acceder al botón lateral de Docker en el Visual SC, y hacer click derecho en el servicio mediawiki del multicontainer _mediawiki_ para abrirlo en el navegador (_Open in Browser_).

4. **Realizar la instalación de MediaWiki** que se propone en el navegador. Para ello, necesitaremos una serie de datos concretos, los cuales podremos obtener en el multi-contenedor generado recientemente, en el Visual Studio Code:

    - El _servidor de la base de datos_ será la **IP de la base de datos de Mariadb**. Para saber cual es, basta con acceder al multi-contenedor de la aplicación _mediawiki_, hacer clic derecho al contenedor de _mariadb_, y seleccionar _Inspect_; esto permite abrir el archivo mariadb.json para ver la dirección IP que necesitamos (alrededor de la línea 230, el valor contenido en la clave "IPAdress").
    Copiamos esa dirección y la sustituímos por la que nos pone por defecto el instalador de MediaWiki (ya no es localhost).

    - El _nombre de usuario de la base de datos_ será **root**, y la _contraseña de la base de datos_ será **anapcontra**, tal y como se indica en el fichero docker-compose.yml

    - Al crear los datos de la cuenta de administrador, puedes poner las credenciales que veas apropiadas, a tu criterio y a las normas de la instalación de mediawiki.

    - Para ahorrarnos pasos de más que no proceden en esta práctica, podemos hacer click en el apartado de _Ya me aburrí. tan solo instala la wiki._

    - Dale clic a continuar hasta que te aparezca el final, es decir, hasta que te permita **descargar el archivo LocalSettings.php**

    >Es importante **descargar este fichero**, ya que es el que ha recogido los datos de instalación. Además de descargarlo en tu ordenador, **deberás copiarlo al directorio de _mediawiki_**, al mismo nivel que el archivo docker-compose.yml y de este propio archivo README.md

5. Ahora procedemos a **modificar el fichero docker-compose.yml** de esta forma sencilla: 
DESCOMENTAMOS LA LÍNEA 13 (_- ./LocalSettings.php:/var/www/html/LocalSettings.php_) y guardamos el fichero. Esto se realiza para ubicar el fichero LocalSettings.php de nuestro host al contenido de la aplicación de mediawiki.

```yml
version: '3'
services:
  mediawiki:
    container_name: p05_mediawiki_anaponce
    image: mediawiki
    restart: always
    ports:
      - 8081:80
    links:
      - database
    volumes:
      - images:/var/www/html/images
      #- ./LocalSettings.php:/var/www/html/LocalSettings.php
  database:
    container_name: p05_mariadb_medwiki_anaponce
    image: mariadb
    restart: always
    environment:
    # He eliminado las variables de entorno que estaban por defecto en dockerHub, y me funciona solo con poner la
    # siguiente variable, tal y como lo hicimos la anterior vez que instalamos MediaWiki en clase
      MYSQL_ROOT_PASSWORD: 'anapcontra'
    volumes:
      - db:/var/lib/mysql
volumes:
  images:
  db:

  # Al finalizar la instalación, descargar el LocalSettings.php, ubicarlo en la misma carpeta de este docker-compose.yml 
  # y DESCOMENTAR LA LÍNEA 13 de este mismo archivo .yml (solo quitando el # )
  # Luego, ejecutar este comando -> docker-compose -f docker-compose.yml up
  # Finalmente, abrir mediawiki en el navegador -> localhost:8081
```

6. Después de guardar los cambios anteriores, es necesario **parar la ejecución del multicontenedor** y seguidamente **ejecutar la siguiente línea de comando** :

    ``docker-compose -f docker-compose.yml up``

Una vez terminado, puedes **acceder en el navegador** al [puerto 8081](http://localhost:8081) y comprobar que se visualiza la mediawiki que configuraste previamente.

7. Para **finalizar el proceso de esta aplicación**, se puede hacer click derecho al multicontainer _mediawiki_ y seleccionar _Compose Stop_, o bien parar la ejecución mediante comando :

    ``docker-compose stop``

    Este paso te lo puedes saltar si quieres seguir probando el resto de aplicaciones (y también si tienes un ordenador que aguante los procesos), ya que cada aplicación puede correr a la vez y tienen todos distintos puertos, por lo que no daría problemas de conexión entre ellas.

    Pero eso sí: **si ya no quieres seguir probando más escenarios, es conveniente que primero ejecutes el comando de _Compose Stop_ de cada escenario/multi-contenedor y luego cierres las aplicaciones de tu ordenador**

***
## REFERENCIAS
***

* Apuntes de clase : [Docker Compose](https://docs.google.com/document/d/1gP0NFSej29oNDjU40f1uoAZP40tXoCN0_FqaKGWxnOw/edit#heading=h.lxcb1oq76810)

* Apuntes de clase : [Curso Docker](https://docs.google.com/document/d/1RNZN8G8lspbvcrXw_im7IgoMS7e5kS05GtlfdV6zdnU/edit)

* Documentación oficial : [MediaWiki en DockerHub](https://hub.docker.com/_/mediawiki)