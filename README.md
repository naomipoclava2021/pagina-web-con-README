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
















































































































































