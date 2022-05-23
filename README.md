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

## Colas: 

- En un mundo real podemos encontrasr este ejemplo en las colas de un banco, etc.
- En el caso de la cola en el banco, la primera persona en llegar es tambien la primera en irse (suponiendo una unica ventanilla) y en los documentos a imprimir, la impresora imprime segun el orden de llegada.
- Las colas se pueden implementar utilizando una estructura estatica (arreglos), o una estructura dinamica (listas enlazada, vectores, etc).

## Colas:
>**Operaciones:**
- add(e):  Insertar el elemento e al final de la cola
- poll(): Elimina el elemento del frente de la cola y lo retorna. Si la cola esta vacia se produce un error.
- peek(): Retorna el elemento del frente de la cola. Si la cola esta vacia se produce un error.
- isEmpty(): Retorna verdadero si la cola esta vacia.
- size(): Retorna la cantidad de elementos de la cola


## Colas:
>**Implementacion:**
- Se crea una coleccion llamada cola de Queue
    - **Queue**:  es una forma lineal especial, que solo permite la eliminacion en el extremo frontal de la lista, mientras que el extremo posterior de la operacion de insercion de la lista.
- Con una implementacion de lista enlazadas(LinkedList):
    - clase LinkedList implementa la interfaz de cola, por lo que puede usar listas enlazadas como un cola
- Se define excepciones para las condiciones de error

## Colas:
>**Ejemplo:**

```java
public static void cola(){
    Queue<Integer> cola = new LinkedList<>();
    System.out.println("Agregando valores");
    for(int i =0; i<5; i++){
        cola.add(i);
        System.out.println("Valor: "+ i);
    }
    System.out.println("\nTamaño Inicial de la cola: "+ cola.size());
    System.out.println("\nRetirando valores");
    while(cola.peek()!=null){
        System.out.println("Valor: "+ cola.poll());
        System.out.println("Tamaño actual de la cola: "+ cola.size());
    }
    System.out.println("Tamaño final de la cola: "+ cola.size());
}

public static void main(String [] args){
    lista();
    cola();
}
```

## Pilas (stacks):
La interfaz de pila se proporciona en el paquete java.util e implementa la interfaz de Coleccion.
- Son un tipo especial de lista.
- Es un tipo de dato abstracto(TDA)
- La pila implementa LIFO(Last in, first out), es decir, utimo en entrar, primero en salir...

![Pila](https://user-images.githubusercontent.com/95596561/169881280-04080b20-61b3-422e-9b8b-6620720d698e.png)

## Pilas:
- En el mundo real podemos encontrar este ejemplo al apilar platos en un punto, cuando queremos mover los platos uno por uno se comienza retirando el ultimo plato.
- Las pilas se pueden implementar utilizado una estructura estatica(arreglos), o una estructura dinamica (listas enlazadas, vectores, etc).


## Pilas:
**Operaciones:**
- push(e): Inserta el elemento e al tope de la pila.
- pop(): Elimina el elemento del tope de la pila y lo retorna. Si la pila esta vacia se produce un error.
- top(): Retorna el elemento del tope de la pila. Si la pila esta vacia se produce un error
- isEmpty(): Retorna verdadero si la pila esta vacia.
- size(): Retorna la cantidads de elementos de la pila

## Pilas:
**Implementacion:**
- Se puede crear una pila de forma sencilla con la clase Stack que hereda de la clase Vector
- Se define excepciones para las condiciones de error.

## Pilas:
**Ejemplo:**

```java
public static void pila(){
    Stack<Integer> pila = new Stack();
    System.out.println("Agregando valores");
    for(int i =0;i<5; i++){
        pila.push(i);
        System.out.println("Valor: "+ i);
    }
    System.out.println("\nTamaño Inicial de la pila: "+ pila.size());
    System.out.println("\nRetirando valores");
    while(!pila.isEmpty()){
        System.out.println("Valor: "+ pila.pop());
        System.out.println("Tamaño actual de la pila: "+ pila.size());
    }
    System.out.println("Tamaño final de la pila: "+ pila.size());
}
```


Gracias. 

>Practica

***Este texto esta in italica***
~~tachada~~
`hola` este un boque de codigo

>## ***El codigo de esta pagina esta*** [GitHub](https://github.com/naomipoclava2021/pagina-web-con-README)

![Imagen](https://docs.github.com/assets/cb-319648/images/help/writing/image-rendered.png)









## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/naomipoclava2021/pagina-web-con-README/edit/main/README.md) to maintain and preview the content for your website in Markdown files.









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
