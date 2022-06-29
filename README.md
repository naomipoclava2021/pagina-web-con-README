## Java

¿ Que es Apache Maven?

Es una herramienta de gestion y construccion de proyectos de software con Java.

Algunas de las tareas que nos permite resolver son:

🔳 Identificar componentes

🔳 **Resolver dependencias**

🔳 Test

🔳 Empaquetamiento

🔳 ...

## POM

Marven se basa en un **Modelo de Objetos del Proyecto** (POM) para su configuracion.

Dicha configuracion debera describirse en un fichero pom.xml

Siempre se situa en la raiz del proyecto.

## Artifict (Artefeacto)

Es un componente de software, la unidad minima que desplegara todo repositorio Maven. Una compilacion de maven produce uno o mas artefactos (**JAR, WAR, POM).

## Coordenadas

Sistema por el cual se determina de forma unica a cada uno de los artefactos en internet.


🔳 **Group ID**: identificacion del grupo. Normalmente se utiliza el nombre del dominio al reves. Por ejemplo: **com.cinemar.mps**

🔳 **Artifact ID**: Identificacion del artefacto. Por ejemplo: **supermak, cinemar**

🔳 **Version 1.0.0-SNAPSHOP, 1.2.5-RC (Release Candidate), 1.3.3-Release**


## Empaquetado

Debemos especificar que tipo de componentes de software que desplegaremos.

🔳 **JAR**: **Java ARchive** es un tipo de archivo que permite ejecutar aplicaciones y herramientas implementadas en el lenguaje de programacion JAVA.
🔳 WAR, EAR, POM


|clean| Elimina los ficheros generados en construcciones anteriores|
|---|---|
|validate| Valida el proyecto si es correcto|
|compile| Genera los ficheros *.class compilando los fuentes *.java|
|test| Ejecuta los test unitarios existentes|
|package| Genera el empaquetado final (**jar, war, etc**)|
|verify| Verificar que el paquete cumpla los criterios de calidad|
|install| Instala un paquete en el equipo local|
|deploy| Instala un paquete en el repositorio remoto|


## Plugin

Es una tarea especifica, mas pequeña que una fase de construccion, que contribuye a la **construccion** y gestion del proyecto.

Permiten conectar con herramientas externas en este proceso de construccion.


# Estructura del Proyecto
|Estructura del Proyecto|
|---|
|Project|
|src|
|main|
|java|
|wwebapps|
|resource|
|test|
|java|
|resource|
|target|
|pom.xml|

## POM.xml

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
        <modelVersion>4.0.0</modelVersion>

        <parent...>

        <groupId>com.cinemar</groupId>
        <artifictId>Cinemar</artifictId>
        <version>0.0.1-SNAPSHOP</version>
        <packaging>jar<packaging>

        <name>Cinemar</name>
        <descripcion>TPFinal Java Mil Programadores Salteños</description>
        <url>https://github.com/Luis-AP/${proyect.artifictId}</url>

        <licenses...>

        <developers...>

        <properties...>

        <dependencie...>

        <build>
            <plugins...>
        </build>
</project>

```


## Repositorio
🔳 Estructura de directorio y ficheros que usa **Maven** para almacenar, recuperar y organizar artefactos.

🔳 Existen repositorios locales, privados y remotos.

* Repositorio central de Maven: [Maven Repository](https://mvnrepository.com/)
* Repositori local: %user%**/.m2./repository**

## Perfiles
🔳 Permite cambiar la configuracion de la aplicacion dependiendo del entorno en que se despliega

🔳 Es definido el el fichero **setting.xml** y se utiliza en el fichero **pom.xml**

## Arquetipos

🔳 Plantilla para crear proyectos



## Spark

>**¿Que es Spark?**

Spark es un framework para Java/Kotlin que nos permite levantar un servidor liviano. El mismo esta diseñado para el desarrollo rapido, escribiendo una cantidad de codigo reducida y de forma expresiva.


Dentro de las filosifias de Spark se encuentran:

- Sintaxis elegante
- Sintaxis declarativa
- Sintaxis expresiva


## Spark

>**¿Como instalamos Spark?**

Debemos agregar a nuestro archivo **pom.xml** de maven la siguiente dependencia.

```xml
<dependency>
    <groupId>com.sparkjava</groupId>
    <artifactId>spark-code</artifactId>
    <version>2.9.3</version>
</dependency>
```

¡ Y listo, ya tenemos Spark, ahora crearemos nuestro servidor!


## Spark

>**Creando nuestro primer servidor**

Como spark funciona con un servidor jetty embebido (cosa que no nos importara a nosotros), a la hora de correr nuestra aplicacion Java, se ejecuta y quedara levantada para poder pegarle.


```java
import static spark.Spark.*;
// Necesitamos llamar a Spark para utilizarlo, Agregarlo de esta manera nos ayudara a que cada vez que llamenos algun metodo de Spark no tengamos que llamarlo desde la clase (Spark).

public class Aplicacion {
    port(8000); //Opcional: Es el puerto TCP que utizara, en casao de no agregarlo usara el 4567
    get("/saludar", (request, response) = "Hola mundo");

    // get: El metodo HTTP que se solicitara
    // "/saludar" :Es la direccion o path donde pedira el recurso
    // request: Es la solitud de algun recurso
    // response: El la repuesta  a la solicitud
    // "Hola mundo": Es lo que vamos a devolver como respuesta
}


```

     Para para para, me estas diciendo que ya esta mi servidor Rest?


## Spark
>mmm...

Estonces...

Bueno, tenemos el servidor, pero queremos una API y esta debe responder objetos REST, en poca palabras un objeto Json o un XML, usaremos el primero, ya que es el mas utilizado. Una vez que tengamos eso se finit, tendremos nuestra API REST levantado es un servidor Jetty.


> ¿Pero como lo hago?, ¿Debo llorar ahora?

NAAA, tu tranquilo pana

Solo necesitamos 3 cositas:

1) Agregar una dependencia para convertir objetos al formato Json.
2) Llamar a la clase dentro de nuestro controlador.
3) Decirle a nuestro endpoint que devolvera un Json.


## Spark
> **Devolviendo un Json**

Agregamos la dependecia al **pom.xml** para convertir Objetos al formato Json

```xml
<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.9.0</version>
</dependency>
```
Instanciamos un objeto que sera quien nos convierta los objetos en nuestro metodo main.
```java
Gson mapper = new Gson();
```
Lo que hacemos a continuacion es decirle a nuestra respuesta que sera un objeto Persona, y como 3er argumento le pasamos el metodo que convierte a Json de nuestro mapeador

```java
get("/saludo", (req, res) = new Persona("Gabriel", "Silvestre"), mapper::toJson);
```
Si todo esta listo, ya tenemos nuestro api rest respondiendo una persona en formato Json.

```json
{"nombre": "Gabriel", "apellido":"Silvestre"}
```


## Spark

> Para terminar te dejo el codigo completo de la magia.

```java
import com.google.gson.Gson;
import static spark.Spark.*;

public class App{
    public static void main(String[] args){

        Gson mapper = new Gson();

        port(8080);

        get("/saludo", (req, res) = new Persona("Gabriel", "Silvestre"), mapper::toJson);

    }
}
```


Toda la documentacion la encontraras en: http://sparkjava.com/documentation


## POSTMAN

gracias.
















































































































































