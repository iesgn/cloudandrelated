# Jugando con git y GitHub

Utilizaremos **git** para realizar el control de versiones de nuestros proyectos. Los sistemas de control de versiones son programas que tienen como objetivo controlar los cambios en el desarrollo de cualquier tipo de software, permitiendo conocer el estado actual de un proyecto, los cambios que se le han realizado a cualquiera de sus componentes, las personas que intervinieron en ellos, etc.

**Github** es un servicio para alojamiento de repositorios de software gestionados por el sistema de control de versiones Git. 

## Empecemos

1. Crea una cuenta en GitHub. Tenemos dos formas de acceder a los repositorios remotos de GitHub:

    * Por https: En este caso cada vez que hagamos una modificación en el repositorio tendremos que autentificarnos. Si queremos utilizar el contenido de nuestro respositorio, pero sin hacer cambios (sólo lectura) puede ser un modo de acceso válido.
    * Por SSH, para conectarnos al servidor que aloja nuestro repositorio tendremos que usar un par de claves RSA, de esta manera debemos copiar nuestra clave pública a GitHub, para ello:
        * Si no tienes ese fichero, puedes generar una nueva clave ssh pública, ejecuntando el siguiente comando: 

                ssh-keygen
        
        * Deja el nombre por defecto `~/.ssh/id_rsa` y no pongas palabra de paso.
	    * Copia el contenido de tu fichero `~/.ssh/id_rsa.pub`, para ello: añade una nueva clave SSH en el apartado "SSH keys" de tu perfil en GitHub y pega el contenido de tu clave pública.
	
2. Crea en GitHub un repositorio con el nombre **prueba** (inicializa el repositorio con un fichero README) y la descripción **Repositorio de prueba**.
3. Instala git en tu ordenador.

		apt-get install git

4. Copia la url SSH del repositorio (no copies la URL https) y vamos a clonar el repositorio en nuestro ordenador.

		git clone git@github.com:josedom24/prueba.git

5. Entramos en el nuestro repositorio local y configuramos git:

		cd prueba
		git config --global user.name "Pepito Pérez"
		git config --global user.email pepito.perez@gmail.com
		git commit --amend --reset-author

	Comprueba que dentro del repositorio que hemos creado se encuentra el fichero README.md, en este fichero podemos poner la descripción del proyecto.

6. Vamos a crear un nuevo fichero, lo vamos a añadir a nuestro repositorio local y luego lo vamos a sincronizar con nuestro repositorio remoto de GitHub. Cada vez que hagamos una modificación en un fichero lo podemos señalar creando un commit. Los mensajes de los commits son fundamentales para explicar la evolución de un proyecto. Un commit debe ser un conjunto pequeño de cambios de los ficheros del proyecto con una cierta coherencia.

		echo "Esto es una prueba">ejemplo.txt
		git add ejemplo.txt
		git commit -m "He creado el fichero ejemplo.txt"
		git push

7. Si modificas un fichero en tu repositorio local, no tienes que volver a añadirlo a tu repositorio (**git add**). Pero tienes que usar la opción -a al hacer el commit.

		git commit -am "He modificado el fichero ejemplo.txt"
		git push

8. Si quieres cambiar el nombre de un fichero o directorio de tu repositorio:

		git mv ejemplo.txt ejemplo2.txt
		git commit -am "He cambiado el nombre del fichero"
		git push

9. Si quieres borrar un fichero de tu repositorio:

		git rm ejemplo2.txt
		git commit -am "He borrado el fichero ejemplo2"
		git push

10. Puedes clonar tu repositorio de GitHub en varios ordenadores (por ejemplo, si quieres trabajar en tu casa y en el instituto), por lo tanto antes de trabajar en un repositorio local tienes que sincronizar los posibles cambios que se hayan producido en el repositorio remoto, para ello:

		git pull

11. Para comprobar el estado de mi repositorio local:

		git status


## Haciendo un fork de un repositorio existente

Cuando hacemos un fork de un repositorio estamos haciendo una copia del mismo. Podemos hacer un fork de cualquier repositorio de cualquier usuario de github y obtenemos una copia del repositorio en nuestra cuenta. Veamos como se hace:

1. Accede a mi repositorio de GitHub: [`https://github.com/josedom24/html_for_openshift`](https://github.com/josedom24/html_for_openshift), busca el botón **Fork** y hazte una copia del mismo.
2. Clona tu copia en tu ordenador de trabajo.
3. Todas las modificaciones que hagas a partir de ahora, la estará haciendo sobre tu copia de repositorio. 

