# Lenguajes funcionales

## ¿Qué es la Programación Funcional?

La programación funcional nos es más que un paradigma de programación, es decir, es una forma en la cual podemos resolver diferentes problemáticas.

~~~
Functional Programming (Programación Funcional), comúnmente abreviado FP.
~~~

Cuando nos encontramos desarrollamos software utilizando este paradigma, estaremos trabajando principalmente con funciones, evitaremos los datos mutables, así como el hecho de compartir estados entre funciones.

Con este paradigma las funciones serán tratadas como ciudadanos de primera clase. Las funciones podrán ser asignadas a variables además podrán ser utilizadas como entrada y salida de otras funciones.

A las funciones que puedan tomar funciones como parámetros y devolver funciones como resultado serán conocidas como función de orden superior.

La programación funcional es un paradigma declarativo. Nos enfocaremos en "qué" estamos haciendo y no en "cómo" se está haciendo que sería el enfoque imperativo. Esto quiere decir que nosotros expresaremos nuestra lógica sin describir controles de flujo; no usaremos ciclos o condicionales.

Veamos un ejemplo utilizando Java.

Java, cómo sabemos es un lenguaje orientado a objetos, sin embargo, en versiones recientes nosotros podemos hacer uso de la programación funcional.

En este ejemplo, la problemática es conocer la cantidad de elementos en la lista mayores a 10.

~~~
List<Integer> numeros = List.of(18, 6, 4, 15, 55, 78, 12, 9, 8);
~~~

Nosotros podemos resolver la problema utilizando ciclos y condicionales. Este sería el enfoque imperativo.
~~~
//Declarativo.
List<Integer> numeros = List.of(18, 6, 4, 15, 55, 78, 12, 9, 8);

int contador = 0;
for(int numero : numeros) {
    if(numero > 10) {
        contador ++;
    }
}
System.out.println(contador);
~~~

El enfoque imperativo sería el siguiente.

~~~
//Imperativo
Long result = numeros.stream().filter(num -> num > 10).count();
System.out.println(result);
~~~

Cómo observamos, con el enfoque imperativo las líneas de código se reducen y nuestro código se torna más legible.

Personas que no tengan conocimientos de programación podrían comprender el funcionamiento del programa. Primero se filtra y posteriormente se suma.

En esta última implementación podemos concluir que es funcional, ya que delega el control de flujos y condiciones a funciones (filter y sum).

Al trabajar con programación funcional, nos toparemos con conceptos tales cómo:

* Funciones puras.
* Composición de funciones.
* Estados compartidos.
* Mutabilidad.
* Efecto secundario.

Expliquemos rápidamente en qué consiste cada uno de estos conceptos.

### Funciones Puras

Las funciones puras, no son más que funciones, las cuales, dando el mismo input, siempre retornan el mismo output, además de no tener efectos secundarios.

### Composición de funciones

La composición de funciones es el proceso de combinar dos o más funciones, teniendo como finalidad ejecutar cada una de estas funciones en secuencia para obtener un resultado en concreto.

~~~
> f(x)
> g(x)

> f(g(x))
~~~

En este caso combinamos la función f de x con la función g de x.

### Estado compartido

El estado compartido es cualquier variable, objeto o espacio de memoria que exista en un ámbito compartido. Un ámbito compartido puede incluir el alcance global o ámbitos de cierre. A menudo, en la programación orientada a objetos, los objetos se comparten entre ámbitos al agregar propiedades a otros objetos.

~~~
Materia materia = new Materia();
Usuario usuario = new Usuario();

usuario.materia = materia;
~~~

### Mutabilidad

Un objeto inmutable es aquel que no puede ser modificado una vez haya sido creado. Por ejemplo, una variable en Java, no es un objeto inmutable.

~~~
String caracteres = "ABC";
String nuevaCadana = caracteres.toLowerCase();
~~~

Podemos ver a los objeto inmutables como constantes, una vez nosotros asignamos un valor este no podrá ser modificado.

### Efectos secundarios

Un efecto secundario es cualquier cambio de estado en la aplicación que sea observable fuera de la función llamada.

Algo complejo, ¿no? Examinemos un poco nuestro código.

~~~
public static int funcion(int x){
 variable_global = 10; //Cambio de valor
 return x + 10;
}
~~~

En este caso mi "función", no es una función pura, ya que esta posee efectos secundarios, modifica el valor de una variable externa a la función.

Los efectos secundarios se evitan principalmente en la programación funcional, para tener como resultado programas mucho más fáciles de comprender y fáciles de probar.

### Lenguajes de programación

Actualmente contamos con una gran cantidad de lenguajes en donde podemos hacer uso de la programación funcional, por ejemplo :

* Java
* PHP
* Ruby
* Python
* Elixir
* Kotling
* Haskell
* Erlang

Muchos de estos lenguajes no están cien por ciento enfocados en la programación funcional, lo cual no es malo, de hecho, estos nos permite hacer una transición de un paradigma a otro, comúnmente de la programación orientada a objetos ha programación funcional.
