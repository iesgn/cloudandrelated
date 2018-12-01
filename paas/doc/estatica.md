# Práctica 2: Desplegando una página estática en OpenShift

Vamos a desplegar len OpenShift la página estática que se encuentra en el repositorio al que le has hecho un fork. Para ello:

1. Accede a la consola web de OpenShift (usuario *developer* y con cualquier contraseña) y elige del catalogo de imágenes, la imagen **Apache HTTP Server**.

2. A continuación indicamos el nombre de nuestra aplicación y el repositorio que queremos desplegar (la dirección del repositorio será con https, para que openshift pueda acceder al mismo).

3. Accede a tu proyecto y a la aplicación y comprueba que se está ejecutando el primer *build* (en este proceso se crea una imagen docker a partir de la imagen que hemos seleccionado (apache2) y el contenido del repositorio indicado. A partir de esta imagen se creará posteriormente el *deploymente* que creara el *pod* de nuestra aplicación).

4. Una vez terminada la ejecución del *build*, comprueba que se ha creado un *deployment*, un *pod*, un *service* y una *ruta de acceso* a la aplicación.

5. Accede desde un navegador a la ruta de acceso de la aplicación y comprueba que hemos desplegado nuestra aplicación.

## Escalando nuestra aplicación

6. ddd