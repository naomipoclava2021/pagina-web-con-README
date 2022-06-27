## JAVA

### Teoria Git- Github

## ¿Que es Git?

Es un **sistema de control de versiones**, es distribuido, es decir que multiples personas pueden trabajar en **equipo**, es open source y tambien se adapta a todo tipo de proyectos desde pequeños hasta grandes, ademas, se pueden fusionar archivos, **guardan una linea de tiempo** a lo largo de todo el proyecto.


## ¿Por que lo usamos?

* **Trabajo Colaborativo**. Distintos programadores pueden estar editando el mismo archivo, o versiones distintas del mismo archivo, y todo seran reflejados en el documento final.

* **Reduce** considerablemente **los tiempos de deploy** (despliegue) de un proyecto, al subir solamente los cambios (no los archivos cambiados,solo los cambios!).

* Permite **regresar a versiones anteriores** de forma muy sencilla y muy rapida.

* Permite **generar flujos de trabajo** que facilitan el desarrollo y mantenimiento de proyectos de gran tamaño.

* El **ecosistema** de GIT es incrible.

* Las "branches" o ramas, permiten trabajar con una base codigo **paralela al proyecto** en si.

* Empezar a **trabajar desde otro entorno** es tan facil como "clonar" el proyecto a tu nuevo entorno, trabajar sobre los archivos que se quieran, y subir los cambios al "master" o a una "branch".

* Sistema de etiquetas, para **etiquetar las distintas versiones** del proyecto.

## Flujo de Trabajo en Local con Git

En Git tendremos el **directorio de trabajo**, la **stagig area** y el **directorio git** (repositorio).

* En el **directorio de trabajo**, tendremos todos los archivos de nuestro proyecto, incluidos aquellos que no nos interesa mandar al repositorio.

* La **staging area** es una zona o area de espera, a la que mandaremos los archivos que tenemos listos para actualizar en el repositorio.

* El **directorio git** es donde se almacenara el snapshop (imagen actual) de los archivos que estan en la staging area.


En Git, los archivos pueden encontrarse en los siguientes estados:

* **untracked**: cuando no se ha añadido a ningun repositorio.
* **tracked**: el fichero ha sido añadido a algun repositorio.
* **staged** el fichero ha sido añadido al repositorio, pero no ha sido enviado todavia con commit al repositorio.
* **modified**: el fichero ha sido modificado.
* **unmodified**: el fichero no ha sido modificado.
* **commited**: el fichero ya ha sido actualizado en el repositorio.


## Antes de Comenzar... aqui una referencia de alguno comandos basico de linux que seran utiles para mas adelante !!

* pwd: Directorio actual en el que te encuentras
* cd: Cambiar de directorios / carpeta
* ls: Ver el contenido de un directorio
* cat: Ver el contenido de un archivo
* cp: Copiar un archivo
* mv: Mover directorios y/o archivos
* mkdir: Crear un nuevo directorio/carpeta
* rmdir: Eliminar directorios vacios
* rm: Eliminar un archivo
* touch: Crear un archivo
* locate: Localizar un archivo
* find: ubica archivos dentro de un directorio
* grep: Busca a traves del texto en un archivo
* sudo: Permite realizar tareas de superusuario
* df: Informa sobre el uso del disco del sistema
* du: Verifica cuanto espacio ocupa un archivo
* head: Muestra las primeras lineas de un archivo
* tail: Muestra las ultimas diez lineas de un archivo
* diff: Compara el contenido de dos archivos
* tar: Guarda archivos en formato tarbar (.tar)
* chmod: Asigna o quita permisos a un archivo
* chown: Transfiere la propiedad de un archivo
* jobs: Muestra todos los procesos ejecutandose
* kill: Finalizala ejecucion de un proceso
* ping: Verifica tu estado de conexion a un servidor
* wget: Descarga archivos de internet
* history: Ver historial de comandos
* man: Muestra las instrucciones de un comando
* apt-get: Instalar / Actualizar un paquete
* hostname: Conoce el nombre de tu host/red

## Creando nuestro Primer Repositorio LOCAL

Ahora una vez instalado Git, Todos los comandos que vamos a ver se ejecutaran sobre **Git Shell**.
El git Shell, visto desde Windows, es un aplicacion que abre un entorno de linea de comandos al estilo Linux. Nos permitira ejecutar tipicos comando de Linux, como crear carpetas, borrar archivos, editar un archivo con vi, etc


Para crear un repositorio privado, crearemos la carpeta del proyecto y a continuacion inicializaremos el repositorio con el comando **git init**.
Para ello abriremos el **Git Shell**, accederemos a la carpeta donde vamos a grabar el proyecto y alli dentro ejecutaremos el comando **git init**.


```bash
#Accedemos a la ruta deseada y crearemos una carpeta: 
mkdir proyecto
cd proyecto

# Una vex dentro del proyecto inicializamos el proyecto con el comando "git init": 

/proyecto/git init

# Despues de un mensaje de creacion del repositorio, si mostramos el contenido de la carpeta con un ls -al veremos una carpeta oculta (.git):
ls -al
.git

```

## Nuestro Primer COMMIT

* Una vez que ya tenemos creado el repositorio, vamos a enviar algunos ficheros y **notificar al sistema** que existen dichos archivo(**commit**).
* Para ello utilizaremos el comando **git add ficheros**.

```bash
# Accedemos a la carpeta del proyecto y creamos algun archivo de pruebas:

/proyecto/touch hola.html
/proyecto/touch index.html
/proyecto/touch prueba.txt

# Ahora le indicamos al sistema que hay nuevos ficheros:
# (el punto hace referencia a la carpeta y añadira todos los ficheros en encontrados)
/proyecto/git add.

```

* Para comprobar las modificaciones que se han producido en el repositorio utilizamos el comando **git status**

```bash
# Ejecutamos el comando git status:
/proyecto/git status

```

* Para notificar al repositorio que hemos añadido ficheros, se hace con el comando **git commit**

```bash
# Notificamos al repositorio los cambios que se han producido, y se envian aquellos ficheros que se encuentran en la staging area:
/proyecto/git commit -m "Nuestro primer commit"

# Si queremos que se envien todos los archivos modificados desde el ultimo commit, independientemente de si se encuentran o no en la staging area, usaremos -a:
/proyecto/git commit -a -m "Nuestro primer commit con todos los archivos modificados"

# Mostrara algo como lo siguiente:

[master (root-commit) 9f89cdf] Nuestro primer commit
0 files changed
create mode 100644 hola.html
create mode 100644 index.html
create mode 100644 prueba.txt
```


## Trabajando con Ramas

Un branch(rama) es una **version de nuestro codigo**. Git nos permite movernos entre versiones de forma sencilla.

La creacion de ramas nos permite trabajar en diferentes versiones de un mismo archivo y cuando lo consideramos podemos **fusionar los cambios**.

Cada vez que creamos una rama, se crea  un nuevo puntero a la version indicada o a la que estamos trabajando. Se van a emplear los comandos **git branch** y **git checkout**.

Para definir un branch se utiliza el comando **git branch** y para cambiarnos a ese branch se utiliza el comando **git checkout**.

Para definir un branch y cambiarnos inmediatamente utilizando **git checkout -b nombre branch:**

```bash
# Definimos un branch controlLDAP
git branch controlLDAP

# Nos cambiamos a ese branch
git checkout -b controlLDAP

Podremos hacer la pogramacion de nuevo opciones en este branch y cuando hayamos terminado
Se enviara los cambios y se fusionaria con la rama master, que es la que se enviaria a produccion.

```


GIT - Github- Trabajo Colaborativo

Que vamos a ver?

* Git Fundamentos
    * Instalacion
    * Versionado en Local (areas de trabajo)
    * Comandos, Ramas, Uniones
* GitHub Basico
    *Login, Interfaz, Markdown y Documentacion
* GitHub Avanzado
    * Sincronizando repo local con remoto
    * Haciendo una Pull request
* Trabajo en Equipo
* Buenas Practicas en Java con Github

Gracias.


















































































































































