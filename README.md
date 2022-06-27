## Java

> Diagramas de Clases

¿Que es un diagrama de clases?
Clase 
Asociaciones
Multiplicidad
Agregacion
Composicion
Generalizacion o Herencia

> ¿Que es un diagrama de clase?
Los diagramas de clase decriben la estructura estatica de un sistema.


Las cosas que existen y que nos rodean se agrupan naturalmente en categorias o grupos (**Clases**). Una Clase tiene **atributos** (caracteristicas) y/o **metodos** (comportamientos).

Un rectangulo es el simbolo que representa a la clase, y se divide en tres areas. Un diagrama de clases esta formado por varios rectangulos de este tipo conectados por lineas que representan las **asociaciones o menera en que las clases se relacionan entre si**

## Clase
| Clase |
|---|
| atributo: tipo |
| /atributo Derivado |

Las clases se representan con rectangulos divididos en tres areas:
* La superior contiene el nombre de la clase.
* La central contiene los atributos.
* La inferior los metodos.

Podemos esquematizar la visibilidad de los **metodos** o **atributos** mediante los siguientes **modificadores de acceso**:

| Visibilidad | Public | Private | Protected |
|---|---|---|---|
| Desde la misma clase | ✔ | ✔ | ✔ |
| Desde una subclase | ✔ | ❌ | ✔ |
| Desde una otra clase (no subclase)| ✔ | ❌ | ❌ |
Simbolo                 + - *

## Asociaciones
Las **asociaciones** son las que presentan a las **relaciones estaticass** entre las clases.

El nombre de la asociacion va por sobre o por debajo la linea que la representa.

Una flecha rellena indica la direccion de la relacion. Los roles se ubican cerca del final de una asociacion.

Los roles representan la manera en que dos clases se ven entre ellas. No es comun el colocar ambos nombres, el de la asociacion y el de los roles a la vez.

Cuando una asociacion es calificada, el simbolo correspondiente se coloca al final de la asociacion, contra la clase que hace de calificador.

## Multiplicadad
| Multiplicidad|
|---|
| 1 no mas de uno |
| 0...1 cero o uno |
| * muchos |
| 0...* cero o muchos |
| 1...* uno o muchos |


Las notaciones utilizadas para señalar la multiplicidad se colocan cerca del final de una asociacion. Estos simbolos indican el numero de instancias de una clase vinculadas a una clase viculadas a una de las instancias de otra clase.

## Ejemplo
Una empresa puede tener uno mas empleados, pero cada empledo trabaja para una sola empresa solamente.

## Agregacion
La agregacion es una relacion en la que la Clase "**Todo**" juega un rol mas importante que la Clase "**Parte**", pero las dos clases no son dependientes una de otra.

Se grafica con un rombo diamante vacio contraa la Clase "**Todo**".

## Composicion
Composicion es un tipo especial de agregacion que denota una fuerte posesion de la Clase "Todo", a la Clase "Parte".

Se grafica con un rombo diamante relleno contra la clase que representa el todo.


## Generalizacion o Herencia
Generalizacion es otro nombre para herencia.
 
Se refiere a una relacion entre dos clases en donde una Clase "Especifica" es una version especializada de otra, o Clase "General".


Gracias.


















































































































































