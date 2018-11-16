# Instalación de docker en una máquina virtual gestionada por vagrant

En este apartado vamos a crear una máquina virtual en virtualbox gestionada por [vagrant](https://www.vagrantup.com/) y que tendrá instalada la última versión de docker.

## Creación de la máquina virtual con vagrant

Tenemos un ordenador donde hemos instalado la [última versión de vagrant](https://www.vagrantup.com/downloads.html) y VirtualBox. Tenemos que descargarnos una imagen vagrant del sistema operativo debian stretch, para ello (Nota: todas las operaciones que hacemos con vagrant la hacemos con un usuario sin privilegios):

    $ vagrant box add debian/stretch64 --provider virtualbox

Al terminar la descarga comprueba que se ha bajado correctamente con:

    $ vagrant box list

A continuación, creamos una carpeta y dentro vamos a crear un fichero `Vagantfile` con el siguiente [contenido](Vagrantfile). Para arrancar la máquina, ejecuta dentro del directorio creado la siguiente instrucción (Nota: todas las operaciones que hacemos para este escenario hay que ejecutarla dentro del directorio donde tenemos el fichero `Vagrantfile`):

    ~/docker$ vagrant up

Cuando finalice la creación, podemos acceder a la máquina con:

    ~/docker$ vagrant ssh

