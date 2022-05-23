# Modulo Nro.3
## Java
>Temas:
- Entrada y Salida por consola
- Variables de texto. Leer/escribir textos.
- Pilas.
- Colas.
- Listas.

**Clase nro.3**
- **Hash Map**
- **Recursion**

## HASHMAP
Cuando vimos vectores y ArrayList aprendimos que los arrays y vectores son una coleccion ordenada de elementos en los cuales tenemos acceso a cada elemento que aloja el vector o ArrayList por medio de un indice de tipo entero(indice/elemento).

Hashmap es una estructura de datos que sigue una idea muy parecida a la de **vectores** o **ArrayList** (indice/elemento) pero con la diferencia que Hashmap almacena dos items una Clave y un Valor y en este caso podemos acceder a cada valor por medio de la clave asociada.

## HASHMAP - ¿COMO CREAR?
```java
public class Test{
    public static void main(String[] args){
        //TODO Auto-generated method stub
        HashMap<String,String> hm= new HashMap<String,String>();

        hm.put("1","Argentina");
        hm.put("3","Chile");
        hm.put("2","Bolivia");
        
        System.out.println(hm.get("2"));
        hm.remove("3");
        System.out.println(hm.size());
        for(String i: hm.keySet()){
            System.out.println(i);
        }

        for(String valor: hm.values()){
            System.out.println(valor);
        }

        for(String i: hm.keySet()){
            System.out.println("Clave: "+ i+ " Valor: "+ hm.get(i));
        }

        hm.clear();
    }
}
```


## RECURSION - CONCEPTO

La recursividad es una tecnica de programacion que permite diseñar algoritmo que dan soluciones elegantes y simples.

Es una tecnica por la cual un algoritmo se invoca a si mismo para resolver una version mas pequeña del problema original para el cual fue diseñado.

## RECURSION - DISEÑO
- El diseño de una solucion recursiva para un problema P consta fundamentalmente de los siguientes pasos:
- Plantear P de forma que pueda ser descompuesto en k subproblemas (P1,P2,...Pk) de la misma naturaleza que el problema original.
- Determinar el **Caso base(condicion de parada o terminacion**: es una condicion que no produce auto invocacion.
- **Llamada recursiva**: es la invocacion del algoritmo a si mismo.

Nota: el valor de los parametros cambiara en cada llamada, volviendolo un caso mas sencillo que el anterior y aproximadamente en cada llamado al caso base.


## RECURSION - DISEÑO
Para determinar si un algoritmo recursivo esta bien diseñado, se puede utilizar el metodo de las 3 preguntas:


1. ¿Existe una salida no recursiva o caso base, y esta funciona correctamente para ella?
2. ¿Cada llamada recursiva se refiere a un caso mas pequeño del problema original?
3. Suponiendo que 1 y 2 se cumplen, ¿Funciona correctamente en todo el proceso?

![Recursion](https://user-images.githubusercontent.com/95596561/169908888-94c0edd6-53d3-45d2-a806-b460f7a4a2b2.png)

![Recursion](https://user-images.githubusercontent.com/95596561/169908981-802d796d-be24-4855-8390-1a68578c4a16.png)

2. CASO BASE: n=0 (litas sin elementos).
3. LLAMADA RECURSIVA: supongamos que nuestro algoritmo lo vamos a llamar sumarLista este modulo recibira como parametros la lista y su longitud. De acuerdo a como se planteo la division en subproblemas de P vemos que vamso reduciendo en 1 la lista quitando siempre el ultimo elemento, es decir en cada subproblema lo vamos "perdiendo" pero antes de perderlo deberiamos acumularlo ya que queremos sumar todos los elementos de la lista. Entoces la llamada recursiva queda: ultimoElemento + RestoLista.

## RECURSION - CODIGO JAVA
```java
public int sumarLista(int lista, int n){
    if(t==0){
        return 0;
    }else return lista[n-1]+ sumarLista(lista, n-1);
}
```

## RECURSION - TRAZA
Para comprender mejor el funcionamiento de un algoritmo recursivo es fundamental conocer como funciona la pila de llamadas de un programa en ejecucion.

Todo programa en ejecucion tiene una pila asociada para este proposito. En los lenguajes de alto nivel (como C o Java) la gestion de la pila de llamadas la realiza de forma automatica el compilador, por lo tanto, el programa no necesita preocuparse de su correcto funcionamiento.

Cuando en un punto del programa se llama a una funcion (recursiva o no) se reserva un espacio en la pila para la siguiente informacion:

- Direccion de retorno de la funcion
- Parametros de la llamda
- Espacion para las variables locales
- Resuelto devuelto

## RECURSION - TRAZA
Ahora que sabemos como se funciona un programa en ejecucion pasemos a un ejemplo de la ejecucion de un algoritmo recursivo.

Supongamos un programa que calcula la factorial de un numero n. Sabemos que la de matematica el factorial se define como n!=n(n-1), esta definicion traducida a codigo Java:

```java
public static int factorial(n){
    if(n==0){
        return 1;
    }else{
        return n*factorial(n-1)
    }
}
```

Si asignamos a n el valor 4

1. Dentro de factorial, cada llamada return n*factorial(n-1); genera una nueva zona de memoria en la pila, siedo n-1 el correspondiente parametro actual para esta zona de memoria. En cada llamada tambien queda pendiente la evaluacion de la ejecucion de la expresion y la ejecucion de return.
2. El proceso 1 se repite hasta que la condicion del caso base  se hace verdadera. Se ejecuta return 1 y empieza la vuelta hacia atras de la recursion. Se evaluan las expresiones y se ejecutan los return pendientes.

![factorial](https://user-images.githubusercontent.com/95596561/169915111-2bde7d78-3f9a-4222-9ec8-59ce1300a26b.png)

## RECURSION
**¿Por que escribir algoritmos recursivos?**
- Generalmente son mas faciles de analizar
- Se adaptan mejor a las estructuras de datos cuya naturaleza es recursiva
- Ofrecen soluciones estructuradas, modulares y elegantemente simples


gracias

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
