## Base de Datos con Java - Teoria Clase 3

> Que vamos a ver?

- 1° Clase Teoria:
    - Teoria General de Base de Dato - Modelo Relacional - Anailis y Diseño de Base de Datos
- 1° Clase Practica:
    - Instalar MySQL y crear tablas de bdd.
- 2° Clase Practica:
    - Teoria de BDD con Java
- 2° Clase Practica:
    - Consumir BDD desde Java con consultas.

> Introduccion de JDBC

En la mayoria de las aplicaciones que nos vamos a encontrar, aparecera una base de datos como **fuente de informacion**.

- JDBC nos va a permitir acceder a base de datos (BDD) **desde Java**.
- Con JDBC **no es necesario** escribir distintos programas de distintas BD, sino que un **unico programa** sirve para acceder a BD de **distinta** naturaleza.
- Podemos **acceder a mas de una BDD** de distinta fuente (Oracle, Access, MySQL, etc.) en la misma aplicacion.
- Podemos pensar en JDBC como el **puente** entre una base de datos y nuestro programa Java.

El esquema a seguir en un programa que use JDBC es el siguiente.

> Introduccion a JDBC

Un programa Java que utilice JDBC primero debera **establecer una conexion con el SGBD**.

Para realizar dicha conexion haremos uso de un **driver especifico para cada SGBD** que estemos utilizando.

Una vez establecida la conexion ya podemos interrogra la BD con cualquier comando SQL(select, update, create, etc.)

El resultado de un comando select es un **objeto de clase ResultSet**, que contiene los datos que devuelve la consulta. Disponemos de metodos en ResultSet para manejar los datos devueltos.

Tambien podemos realizar **cualquier operacion en SQL** (creacion de tablas, gestion de usuarios, etc.)

> Introduccion a JDBC

Los drivers para poder acceder a cada SGBD **NO** forman parte de la **distribucion de Java** por lo que deberemos **obtenerlos por separado**.

¿Por que hacer uso de un driver?

El principal problema que se nos puede plantear es que **cada SGBD dispone de su propio API** (la mayoria propietario), por lo que un cambio en el SGBD **implica una modificacion** de nuestro codigo.

Si colocamos una capa intermedia, podemos **abstraer la conectividad**, de tal forma que nosotros utilizamos un objeto para la conexiono, y el driver se encarga de traducir la llamada al API.

El driver lo suelen distribuir las **propias empresas** que fabrican el SGBD.

> Introduccion a JDBC

## Tipos de Drivers

- **Tipo 1: Puente JDBC-ODBC**. ODBC (Open Database Connectivity) fue creado para proporcionar una conexion a bases de datos en Microsoft Windows. El puente JDBC-ODBC permite enlazar Java con cualquier base de datos disponibles en ODBC. No se aconseja el uso de este tipo de driver cuando tengamos que acceder a bases de datos de alto rendimiento, pues las funcionalidades estan limitadas a las que marca ODBC.

- **Tipo 2: Parte Java-Parte Nativo**. Es una combinacion de implementacion Java y API nativo para el acceso a la base de datoss. Este tipo de drivers es mas rapido que el anterior, pues no se realiza el paso por capa ODBC. Las llamadaas JDBC se traducen en las llamadas especificas del API de las bases de datos. Cada cliente debe tener instalado el driver. Tiene menor rendimiento que los dos siguientes y no se pueden usar en Internet, ya que necesita el API de forma local.


- **Tipo 3: Servidor Intermediario a BDD**. Este tipo de driver proporciona una abstraccin de la conexion. EL cliente se conecta a los SGBD mediante un componente servidor intermedio, que actua como una puerta para multiples servidores. La ventaja de este tipo de driver es el nivel de abtraccion. El servidor de aplicaciones WebLogic incorpora este tipo de driver.

- **Tipo 4: Drivers Java**: Este es el mas directo. La llamada JDBC se traduce directamente en una llamada de red a la base de datos, sin intermediarios. Proporcionan mejor rendimieto. La mayoria de SGBD proporcionan drivers de este tipo.


- **Tipo 4: Drivers Java**: Estr es la mas directo. La llamada JDBC se traduce directamente en una llamada de red a la base de datos, sin intermediarios. Proporcionan mejor rendimiento. La mayoria de SGBD proporcionan drivers de este tipo.

>Instalacion del Driver

La distrubuccion de JDBC incorpora los drivers para el puente JDBC-ODBC que nos permite acceder a cualquier BD que gestione con ODBC. Para MySQL, deberemos descargar e instalar el SGBD u el driver, que puede ser obtenido en la direccion https://downloads.mysql.com/archives/c-j/ .

![Driver](https://user-images.githubusercontent.com/95596561/172074406-95b2af2d-58e6-463f-9454-5ec6bffb3b79.png)

>Introduccion a JDBC

Para instalar el driver lo unico que debemos hacer es **incluir el fichero JAR** dentro de nuestro Java Project para eso vamos a **extraer** el contenido del archivo comprimido en alguna carpeta dentro de nuestro ordenador de la siguiente manera

- Buscamos el archivo que **descargamos** y hacemos click derecho sobre el y elegimos la opcion de **'Extraer aqui'**
![Driver](https://user-images.githubusercontent.com/95596561/172074686-2ba72a40-4774-4578-acad-88a96b398550.png)


>Introducion a JDBC

Esto nos va a **descomprimir** los archivos y deberiamos tener una carpetq similar a esta de aqui, el archivo que nos interesa es el de nombre:
- **"mysql-connetor-java-8.0.xx.jar"**
![Driver](https://user-images.githubusercontent.com/95596561/172074797-7fbdcf28-54d5-4ed0-ab09-4d95fab8fa89.png)

>Introduccion a JDBC

Ahora vamos a seguir una serie de pasos para poder **incluir** dentro de nuestro Java Project a nuestro **Connector/J**.

* Hacer **click derecho** sobre nuestra carpeta donde tendremos el Java Project en el que vamos a querer conectarnos a la BDD y seleccionar **Properties o Propiedades**

![Connector/J](https://user-images.githubusercontent.com/95596561/172074974-181505dc-3bbc-4c9a-99a3-baf3dfdd195f.png)

> Introduccion a JBDC

Dentro de Properties/Propiedades buscamos en la lista a la izquierda la opcion **Java Build Path** y la seleccionamos, desde aqui vamos a poder **añadir el Conector/J** a nuestro Java Project.

![Connector/J](https://user-images.githubusercontent.com/95596561/172075157-0568529a-8519-457c-b50a-c42f3a0d23ef.png)

> Introduccion a JDBC

Ahora hacemos click sobre la opcion **"Add External JARs.."** y se nos desplegara un exporador de archivos donde debemos ubicar y seleccionar nuestro archivo **"mysql.connector.java.8.0.xx"** y seleccionamos la opcion de **"Abrir"**

![Connector/J](https://user-images.githubusercontent.com/95596561/172075325-1f20a0cc-86a9-43ba-948d-0a25c4fbeb8a.png)

>Introduccion a JDBC

Desde aqui vamos a ver **corroborar que se añadio** la version que queriamos de nuestro **Conector/J** y luego daremos click en el boton **"Apply and Close"**, por ultimo veremos dentro de nuestro Eclipse en la parte de **Package Explorer** (en la parte izquierda del editor) si tienen añadida la libreria que necesitamos(deberia aparecer como la foto de la derecha) para poder ahora si conectarnos y comenzar a hacer cosas con nuestra BDD.

![Connector/J](https://user-images.githubusercontent.com/95596561/172075642-484f2dd0-918f-4286-bf6a-a0ad2ce31e12.png)


>Introduccion a JDBC

El driver de DBMS debe **proporcionar** implementaciones, cuando menos, para las siguientes interfaces de paquete **java.sql**

![java.sql](https://user-images.githubusercontent.com/95596561/172075751-15e2e1b8-168d-4c30-90e4-b843b242ea3a.png)

> Introduccion a JDBC

Pasos para usar JDBC


<ol>
    <li>Crear una instancia del JDBC Driver</li>
    <li>Especificar la url y credenciales de la BDD.</li>
    <li>Establecer una conexion usando el driver que crea el objeto Connection.</li>
    <li>Crear un objeto Statement, usando Connection</li>
    <li>Armar el postulado SQL y enviarlo a ejecucion usando el Statement</li>
    <li>Recibir los resultados en el objeto ResultSet</li>
</ol>


Para correr el siguiente ejemplo vamos a utilizar la BDD world. que debiamos importar en el TP1_modulo3

>Introduccion a JDBC

Ejemplo con **codigo** de los pasos utilizar JDBC:

* Al principio vamos a **importar la librerias** esto nos traera todo lo que necesitamos para poder acceder a la BDD (java.sql.Connection, java.sql.Statement, java.sql.PreparedStatement,java.sql.CallableStatement, java.sql.ResultSet,java.sql.Driver)

![import java.sql.*](https://user-images.githubusercontent.com/95596561/172076477-1c0f06c7-7df7-4ab3-9d3e-410ec38ba6d0.png)

>Introduccion a JDBC

* En este paso vamos a definir el **Driver**, la **URL de la BDD** a la que queremos acceder, y las **credenciales de acceso** para poder luego conectarnos con la BDD.

![Credenciales](https://user-images.githubusercontent.com/95596561/172076611-2eae7ba8-2b5c-4dfd-8263-eabf861a24bb.png)

* **JDBC_DRIVER**: Esto le especifica cual sera el driver que utilizaremos para acceder a la BDD.
* **DB_URL**: Aqui le proporcionaremos la direccion en la que se **encuentra** la BDD a la que queremos acceder.
* **USER**: Este es el nombre del usuario con el que accedemos, por defecto a la hora de instalar quedo el usuario "root".
* **PASS**: La contraseña que teniamos que **guarda** para poder acceder con nuestro driver a la BDD.

>Introduccion a JDBC

* Aqui vamos **Registrar el Driver**
![screenshot (8)](https://user-images.githubusercontent.com/95596561/172077002-53c160e2-b665-4b98-8542-bf98f8905454.png)
* Aqui vamos a **Conectarnos a la BDD** con las credenciales que le proporcionamos
![screenshot (9)](https://user-images.githubusercontent.com/95596561/172077109-bddb15eb-4e25-40cf-868c-267f2765c2ae.png)
* Aqui vamos a crear un objeto Statement para poder **correr nuestras sentencias SQL**

