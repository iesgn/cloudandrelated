# Ejercicios con docker

## Ejercicio 1: Nuestros primeros contenedores

### Nuestro primer contenedor "Hola Mundo"

    $ docker run ubuntu /bin/echo 'Hello world'
    Unable to find image 'ubuntu:latest' locally
    latest: Pulling from library/ubuntu
    8387d9ff0016: Pull complete 
    ...
    Status: Downloaded newer image for ubuntu:latest
    Hello world

Con el comando `run` vamos a crear un contenedor donde vamos a ejecutar un comando, en este caso vamos a crear el contenedor a partir de una imagen ubuntu. Como todavía no hemos descargado ninguna imagen del registro docker hub, es necesario que se descargue la  imagen. Si la tenemos ya en nuestro ordenador no será necesario la descarga. 

* Comprueba si hay algún contenedor ejecutándose (`docker ps`).
* Comprueba los contenedores que ya se han ejecutado y ahora están parados (`docker ps -a`).
* Compruebas las imágenes de nuestro registro local (`docker image ls`)

### Ejecutando un contenedor interactivo

En este caso usamos la opción `-i` para abrir una sesión interactiva, `-t` nos permite crear un pseoude-terminal que nos va a permitir interaccionar con el contenedor, indicamos un nombre del contenedor con la opción `--name`, y la imagen que vamos a utilizar para crearlo, en este caso “ubuntu”,  y por último el comando que vamos a ejecutar, en este caso `/bin/bash`, que lanzará una sesión bash en el contenedor:

    $  docker run -it --name contenedor1 ubuntu /bin/bash 
    oot@2bfa404bace0:/#

El contenedor se para cuando salimos de él. Para volver a conectarnos a él:

    $ docker start contendor1
    contendor1
    $ docker attach contendor1
    root@2bfa404bace0:/#

### Creando un contenedor demonio

En esta ocasión hemos utilizado la opción `-d` del comando `run`, para la ejecución el comando en el contenedor se haga en segundo plano.

    $ docker run -d --name contenedor2 ubuntu /bin/sh -c "while true; do echo hello world; sleep 1; done"
    7b6c3b1c0d650445b35a1107ac54610b65a03eda7e4b730ae33bf240982bba08

* Comprueba que el contenedor se está ejecutando
* Comprueba lo que está haciendo el contenedor (`docker logs contenedor2`)

Por último podemos parar el contenedor y borrarlo con las siguientes instrucciones:

    $ docker stop contenedor2
    $ docker rm contenedor2

### Creando un contenedor con un servidor web

Tenemos muchas imágenes en el registro público **docker hub**, por ejemplo podemos crear un servidor web con apache 2.4:

    $ docker run -d --name my-apache-app -p 8080:80 httpd:2.4

Vemos que el contenedor se está ejecutando, además con la opción `-p` mapeamos un puerto del equipo donde tenemos instalado el docker, con un puerto del contenedor.  Para probarlo accede desde un navegador a la ip del servidor con docker y al puerto 8080.

## Ejercicio 2: Creando nuestras imágenes con Dockerfile

 
## Recursos sobre docker

* [Introducción a docker](https://www.josedomingo.org/pledin/2015/12/introduccion-a-docker/)
* [Primeros pasos con Docker](https://www.josedomingo.org/pledin/2016/02/primeros-pasos-con-docker/)
* [Ejecutando una aplicación web en docker](https://www.josedomingo.org/pledin/2016/02/ejecutando-una-aplicacion-web-en-docker/)
* [Dockerfile: Creación de imágenes docker](https://www.josedomingo.org/pledin/2016/02/dockerfile-creacion-de-imagenes-docker/)
* [Ejemplos de ficheros Dockerfile, creando imágenes docker](https://www.josedomingo.org/pledin/2016/02/ejemplos-de-ficheros-dockerfile-creando-imagenes-docker/)
* [Gestionando el registro Docker Hub](https://www.josedomingo.org/pledin/2016/02/gestionando-el-registro-docker-hub/)
* [Enlazando contenedores docker](https://www.josedomingo.org/pledin/2016/02/enlazando-contenedores-docker/)
* [Creando servidores docker con Docker Machine](https://www.josedomingo.org/pledin/2016/05/creando-servidores-docker-con-docker-machine/)
* [Gestión del almacenamiento en docker](https://www.josedomingo.org/pledin/2016/05/gestion-del-almacenamiento-en-docker/)
* [Gestionando el almacenamiento docker con Dockerfile](https://www.josedomingo.org/pledin/2016/11/gestionando-el-almacenamiento-docker-con-dockerfile/)
* [Creando servidores docker con Docker Machine](https://www.josedomingo.org/pledin/2016/05/creando-servidores-docker-con-docker-machine/)