## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/naomipoclava2021/pagina-web-con-README/edit/main/README.md) to maintain and preview the content for your website in Markdown files.


# Modulo Nro.3
>## Temas

- Entrada  y Salida por consola
- Variables de texto.   Leer/escribir textos.

Clase  nro.2
- Listas.
- Colas.
- Pilas.
- Hash Map
- Recursion

>## Listas:
Las listas son un tipo de coleccion que hereda de la interface collection, son una estructura de datos que respeta el orden en el cual fueron agregados los elementos, tambien permiten registros repetidos.

``` indice 1 indice 2 indice 3 indice 4```

- El numero de elementos de la lista no suele estar fijado.
- Se tiene un control absoluto y preciso del lugar en el que se quiere insertar.
- Es posible acceder a sus elementos a traves de su indice
- Maneja grandes volumenes de datos
- List se encuentra en el paquete java.util
- Algunas clases que implementa son:
    - ArrayList
    - LinkedList
    - Stack
    - Vector

## Listas
>**Crear y declarar una lista**

Hemos indicado que List es una interfaz y esta implementada por clases como:

- ArrayList
- Stack
- Vector
- LinkedList

Por lo tanto, puede declarar y crear instancias de la lista de cualquiera de las siguientes maneras:

```java
    List linkedlist = new LinkedList();
    List arraylist = new ArrayList();
    List vec_list = new Vector();
    List stack_list = new Stack();
```

el orden de los elementos cambiara dependiendo de la clase utilizada para crear una instancia de la lista.

por ejemplo, para una lista con clase stack, el orden es Last In, First Out (LIFO).

## Listas:
>**Metodos**

- add()
- addAll()
- clear()
- contains()
- containsAll()
- copyOf()
- equals()
- get()
- hashCode()
- indexOf()
- isEmpty()
- iterator
- lastIndexOf()
- lastIterator()
- of()
- remove()
- removeAll()
- replaceAll()
- retainAll()
- set()
- size()
- sort()
- spliterator()
- subList()
- toArray()

## Listas:

>**Ejemplo**

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

Class fichero{
    public static void main(String[] args) throws Exception{
        List<String> list = new ArrayList<String>();
        // Añadimos elementos
        list.add("Luis");
        list.add("Marta");
        list.add("Julio");

        // Obtenemos un Iterador y recorremos la lista.
        // Iterador<String> lista = new list.iterator();
        Iterator<String> iter = new list.iterator();
        while(iter.hasNext()){
            System.out.print(iter.next());
        }

    }
}
```


Definimos un ArrayList de tipo String.

Agregamos datos a la lista con add().

Iterator es un objeto que nos permite recorrer una lista y presentar por pantalla todos sus elementos. Dispone de dos metodos claves para realizar esta operacion hasNext()y next().

## Listas:
>**Diferencias entre listas y arrays**

| Arrays        | Listas        |
| ------------- | ------------- |
| Escrituras de datos para almacenar una secuencia de valores, No redimensionable.  | estructura de datos para almacenar una secuencia de valores , que Es redimencionable. |
| Serie de variables consecutivas en memoria.  | Se guardan en memoria de manera dinamica.  |
| Se debe  especificar su tamaño.| No es necesario definir su tamaño.
|Se debe definir el tipo de datos que manejara. | Puede almacenar distintos tipos de datos (no recomendado).
|Se maneja con indice. | Se maneja con puntero.|
|No se puede agregar o eliminar elementos | Se puede agregar y eliminar elementos.

## Temas:
- Entrada y Salidas por consola
- Variable de textos. Leer/ escribir textos.
>**Clase nro.2**
- Listas.
- **Colas**
- **Pilas**
- Hah Map
- Recursion

## Colas:
La interfaz de cola se proporciona el paquete java.util e implementa la interfaz de Coleccion.

- Son un tipo especial de listas
- Es un tipo de dato abstracto(TDA)
- La cola implementa FIFO(firts in, first out), es decir, primero en entrar, primero en salir..

![Cola](https://user-images.githubusercontent.com/95596561/169605578-a2679c3a-f5d5-4a1a-ad34-29f6b18586ca.png)

>Practica

***Este texto esta in italica***
~~tachada~~
`hola` este un boque de codigo

>## ***El codigo de esta pagina esta*** [GitHub](https://github.com/naomipoclava2021/pagina-web-con-README)

![Imagen](https://docs.github.com/assets/cb-319648/images/help/writing/image-rendered.png)


















Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/naomipoclava2021/pagina-web-con-README/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
