# Bases de Datos con Java - Teoria Clase 1

> Que vamos a ver?

- 1° Clase Teorica:
    - Teoria General de Bases de Datos - Modelo Relacional - Analisis y Diseño de Bases de Datos
- 1° Clase Practica:
    - Instalar Mysql y crear tablas de bdd.
- 2° Clase Teorica:
    - Teoria de BDD con Java
- 2° Clase Practica:
    - Consumir BDD desde Java con consultas.


> Teoria General de Bases de Datos
**¿Que son las Bases de Datos?**

Existen muchas definiciones  entre las cuales podemos encontrar que:

- Es una **recopilacion organizada de informacion** o datos estructurados normalmente se almacena de forma electronica en un sistema informatico.

- Es un **conjunto de datos relacionados** entre si.

- Es una **herramienta para organizar** y recopilar informacion.

- Una base de datos hace referencia al conjunto de datos o informaciones determinadas que se pueden **consultar de manera agil**, y segmentando las caracteristicas que se quieran destacar para concretar mas informacion que se pretende revisar.

- **Representa** alguna porcion del **mundo real.**

> Teoria General de Bases de Datos
Una definicion mas completa:
- Una **coleccion de datos** integrados, con redundacia controlada y con una estructura que refleja las **interrelaciones** y restricciones semantica existentes en el mundo real; los datos, que han de ser **compartidos** por diferentes usuarios y aplicaciones, deben mantenerse independientes de esta y su definicion y descripcion, unicas para cada tipo de datos, han de estar **almacenadas** con los mismos. Los procesos de actualizacion y recuperacion, comunes y bien determinados habran de ser capaces de **conservar** la integridad, seguridad y confidencialidad del conjunto de datos.

> Teoria General de Bases de Datos
Un sistema de Base de Datos esta formado por:

## HARDWARE
El hardware es el conjunto de **dispositivos fisicos** sobre los que reside la BDD, Consiste en una o mas computadoras, unidades de discos, monitores, impresoras, unidades de almacenamiento, cableado y otros equipos auxiliares.

## SOFTWARE

Incluye distintos tipos de software:
- El **Sistema de Gestion de Bases de Datos(SGBD)**
- El sofware para la aplicacion, que usa las facilidades del SGBD para **manipular** la BDD.
- Herramientas para el **desarrollo** de aplicaciones.

## DATOS
- Son el objetivo principal, y por lo tanto **ningun** sistema de BDD **debe** (diferente de puede, ojo!) existir sin los datos.
- Estos datos **deben ser** cuidadosa y logicamente **estructurados**.
- Base sobre la que se fundamenta las necesidades de informacion y de procesamiento de una empresa.


## PERSONAL
- **Usuarios Informaticos:** Persona cuya mision esta en el diseño y del mantenimiento del sistema de BDD y su paquete de programas de aplicacion asociado.
- **Usuarios No informaticos:** Personas que necesitan la informacion de la BDD para desarrollar su trabajo en el negocio.


> Teoria General de Bases de Datos

| VENTAJAS | DESVENTAJA |
| --- | --- |
| Permiten encontrar informacion con **mayor rapidez** .Esto colocando una palabra clave (o incluso solo una parte de esta) e iniciando una busqueda que, **dependiendo del tamaño** de la base de, suele ser muy veloz.| Puede ser **vulnerables o susceptibles a ataques externos**, por ejemplo, por parte de un hacker (Por eso es importante tener un respaldo e invertir en seguridad informatica).|
| **Ahorro de espacio fisico**, al no tener que guardar achivos o papeles en el almacen u oficina. | Si el sistema falla, se genera un **efecto en cadena** que puede paralizar muchos procesos importantes de la empresa. |
Permiten **compartir** datos de manera rapida con quien sea requerido.| Se requiere de **mucha capacidad** en el disco duro y de memoria RAM para funcionar de forma eficiente. |
Permite ingresar una cantidad practicamente ilimitada de datos (la limitacion la da el hardware). | Su instalcion puede exigir un elevado coste (licencias). |
Es posible **trabajar con los datos** en funcion a lo que requiere el analista, seleccionando rapidamente los datos que comparten caracteristica. Por ejemplo, extrayendo aquellas informacion que pertenece al mismo cliente.| Se debe contratar a un especialista para su mantenimiento. 

## Teoria General de Bases de Datos
Elementos que encontramos en una BDD

>Entidades

Se define una entidad (o instancia) como una **unidad** de una base de datos que **contiene informacion**. Esta unidad es una representacion detro de la base de datos de un objeto, persona, empresa...etc, del mundo real, y con tal **posee ciertos atributos que la diferencian del resto de entidades**

Estas entidades como la conocemos ahora, van a representar un tabla en nuestra BBDD, luego nos va a interesar **recopilar datos acerca de estas entidades** y es un proceso de algo de practica poder identificarlas en una organizacion o empresa.

![atributos](https://user-images.githubusercontent.com/95596561/170130228-f13ca973-5703-4d3b-ac69-4d6ed91d2cbb.png)


## Teoria General de Basesd de Datos
Elementosa que encotramos en una BDD
>Atributos

Los atributos **definen o identifican las caracteristicas de entidad** (**es el contenido de esta entidad**). Cada entidad contiene distintos atributos, que dan **informacion sobre esta entidad**. Estos atributos puenden ser de distintos tipos (numericos, texto, fecha...).

![atributos](https://user-images.githubusercontent.com/95596561/170131570-072f3752-a689-481c-a361-e6c176bdaf95.png)


## Teoria General de Bases de Datos
>EL MODELO RELACIONAL
- El modelo Relacional es un modelo muy simple y con solidos fundamentos matematicos, basada en la **teoria de conjuntos**. Fue diseñado por E.F Codd en 1970
- Codd argumento que los datos **deberian relacionarse mediante interrelaciones** naturales,logicas, inherentes a los datos.
- Codd propuso un modelo simple de datos en el que todos ellos **se representaron en tablas constituidassd por filas y columnas.**

>Relacion
- Las **relaciones** de **base de datos** son **asociaciones entre tablas** que se crean utilizando sentencias de union para recuperar datos.
- Una relacion **Es un vinculo** entre entidades.

![relacion](https://user-images.githubusercontent.com/95596561/170133071-a173ccf9-3641-43a3-84a7-42f4f42b5ad8.png)


## Teoria General de Bases de Datos
Entoces ahora todas las relaciones son lo mismo? Nop, Gracias a la Cardinalidasd.
> Cardinalidad

Define la **cantidad** de entidades en un conjunto de entidades, que pueden asociarse con el **numero de entidades** de otro conjunto a traves del conjunto de relaciones.

![cardinalidad](https://user-images.githubusercontent.com/95596561/170134114-d1ec1795-1878-4c7a-b35c-cf747ad086a0.png)

## Teoria General de Base de Datos

- En informatica, o concretamente en el contexto de una base de datos realacional, un **registro** (tambien llamado **fila** o **tupla**) **representa un objeto unico de datos** implicitamente estructurados en una tabla. **No puede haber un registro duplicado**, los datos deben ser diferentes en al menos uno de los campos.
- Un registro es un conjunto de campos que **contienen los datos que pertencen a una misma entidad**. Se le asigna automaticamente un numero consecutivo (numero de registro) que en ocasiones es usado como indice auque lo normal y practico es asignarle a cada registro un campo clave para su busqueda.
- **Es cada una de las filas de una relacion o tabla**


![Tabla](https://user-images.githubusercontent.com/95596561/170135700-15fe62c1-c431-4061-a931-1c75a976b634.png)


## Teoria General de Bases de Datos
**CARACTERISTICAS** QUE DEBE TENER UNA TABLA EN EL **MODELO RELACIONAL**

- Cada tabla debe contener un solo tipo de filas. Es decir, todas las filas tienen las mismas columnas y formato.
- Cada fila tienen que ser unica, no pueden haber filas duplicadas.
- El orden de las filas de las tablas es indiferente.
- Cada columna debe estar identificado por un nombre especificado.
- El orden de las columnad dentro de una tabla es indiferente.
- Cada columna debe extrear sus valores de un dominio.
- Un mismo domino podra servir para definir los valores de varias columnas diferentes,
- El valor individual de la interseccion de cualquier fila y culumna sera un unico dato.

## Teoria General de Bases de Datos
>DENTRO DE LA TUPLAS PODEMOS ENCONTRAR aLgunas cosas mas.

- **VALOR NULO**:
    - Es el valor de un atributo en una tupla si el atributo es inaplicable o su valor es desconocido. Por ejemplo puede existir un registro donde el valor de una columna no exista y queda como un valor nulo.
- **CLAVE**
    - Es un conjunto minimo de atributos que identifique univocamente a cada tupla en la relacion. Puede haber varias claves. Se Llama clave principal, a aquella que se selecciona como la clave de la relacion.
- **CLAVE EXTERNA:**
    - Es un atributo o conjunto de atributos en una relacion que es una clave en otra, o en la misma relacion.
- **RESTRICCIONES:**
    - Es una ragla que limita los valores de los datos contenidos en la  BDD.
    - El Modelo Relacional de Codd incluye varias restricciones para verificar la validez de los datos.
        - **Integridad de la Entidad:**
            - El atributo que es clave de fila en una relacion no puede tener un valor nulo
        - **Integridad Referencial:**
            - El valor de una clave externa o es nulo o debe ser un valor real de una clave en otra relacion.
        - **Dependencia Funcional:**
            - Este concepto se refiere a que todos los valores de los atributos de un registro tienen que estar referenciados o tener una dependencia con el atributo seleccionado como clave primaria.

## Teoria General de Base de Datos
> SGBD (Sitema Gestor de Bases de Datos)

"Un **conjunto coordinado de programas**, procedimiento, lenguaje, etc., que **suministra**, tanto a los usuarios no informaticos como a los analistas, programadores o al administrador de la BDD los **medios necesarios** para describir, recuperar y manipular los datos almacenados en la base, manteniendo su integridad, confidencialidad y seguridad"

## Teoria General de Bases de Datos
> **Funciones de un SGBD**

> Funcion de **Descripcion o Definicion**

 - Mediante esta funcion el administracion especificara los elementos que integran la B.D., su estructura, y las relaciones que existen entre ellos, las reglas de integridad semantica, asi como las caracteristicas de tipo fisico y las vistas logicas de los usuarios.
- El diseñador utiliza esta funcion mediante el lenguaje de definicion o descripcion de datos (en adelante LDD), de tal forma que defina las tres estructuraas de datos (externa, logica global, e interna).

> Funcion de **Manipulacion:**
- Mediante ella se pueden realizar las operaciones de buscar, añadir, suprimir, y modificar los datos de la B.D., simpre segun las especificaciones y las normas de seguridad prevista por el administrador.
- Esta funcion se realiza con el leguaje de manipulacion de datos (LMD) que facilita las tecnicas necesarias para la realizacion de estas actividades.

> Funcion de **Utilizacion:**
- Tambien llamad de control, reune toda la interfaz que utilizan los distintos usuarios, y proporciona al administrador un conjunto de procedimiento para mantener el control, la integridad, y la seguridad de la BD
- Esta funcion se realiza con el lenguaje de control de datos (en adelante LCD)

## Teoria General de Bases de Datos

> Lenguajes

**Lenguaje de descripcion de los datos(LDD)** mediante el cual se definiran y construiran las diferentes estructuras: logica global, externa, e internas
**Lenguaje de manipulacion de datos(LMD)** que hara posible todas las operaciones de seleccion, borrando, modificacion, e insercion de datos. Pueden ser procedimentales, y de cuarta generacion
**Lenguaje de control de datos(LCD)** con el cual se controlaran los temas referentes a seguridad y administracion de la base de datos.

EL LENGUAJE SQL

SQL (por sus siglas en ingles **Structured Query Language**; en español **lenguaje de consulta estructurada**) es un lenguaje de dominio especifico, diseñado para administrar, y recuperar informacion de sistema de gestion de bases de datos relacioneles. Una de sus principales caracteristicas es el manejo del algebra y el calculo relacional para efectuar consultas con el fin de recuperar, de forma sencilla, informacin de base de datos, asi como realizar cambios en ellas.


## Teoria General de Base de Datos
> EL LENGUAJE SQl comandos DDL


|Comandos| Descripcion |
|---|---|
|CREATE| Utilizado para crear nuevas tablas, campos e indices|
|DROP| Almacena texto en formato binario. Empleado para eliminar tablas e indices|
|ALTER| Utilizado para modificar las tablas agregando campos o cambiando la definicion de campos.

```sql
CREATE TABLE clientes;
ALTER TABLE alumnos ADD edad INT UNSIGNED;
DROP TABLE alumnos;
```

## Teoria General de Bases de Datos
>EL LENGUAJE SQL comando DML

|Comandos| Descripcion|
|---|---|
|SELECT| Utilizado para consultar registros de la base de datos que sastifagan un criterio determinado|
|INSERT| Utilizado para cargar lotes de datos en la base de datos en una unica operacion.|
|UPDATE| Utilizado para modificar los valores de los campos y registros especificados|
|DELETE| Utilizado para eliminar registros de una tabla de una base de datos|

## Teoria General de Base de Datos
> EL LENGUAJE SQL comando DML

```SQL
SELECT *
FROM
    coches
ORDER BY
    marca,
    modelo;

```

```SQL
INSERT INTO
    tabla(columnaA, [columnaB, ...])
    VALUES
    ('valor1', ['valor2',...]);
-- O tambien se puede utilizar como:
INSERT INTO table VALUES ('valor1', 'valor2');
```

```SQL
UPDATE My_table SET field1 = 'update value' WHERE fileD2= 'N';

```


```SQL
DELETE FROM mi_table WHERE columna2='N';
```



