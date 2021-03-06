# Patrones Creacionales

### Integrantes
1. Paula Andrea Gomez - 20152020927
2. Juan Arias Ortegon - 20161020522
3. Jorge Escobar Bohorquez - 20152020120

## Sinlgeton
### Introducción 
Es un patrón de diseño que permite restringir la creación de objetos pertenecientes a una clase o el valor de un tipo a un único objeto. Su intención consiste en garantizar que una clase sólo tenga una instancia y proporcionar un punto de acceso global a ella. Lo utilizamos porque permite acceso controlado a la única instancia, puede tener un control estricto sobre cómo y cuándo acceden los clientes a la instancia, Debe haber exactamente una instancia de una clase, y debe ser accesible a los clientes desde un punto de acceso conocido.

![GitHub Logo](https://github.com/paulagomez05/PatronesCreacionales/blob/master/2.png)

En el diagrama UML, la clase que es Singleton define una instancia para que los clientes puedan accederla. Esta instancia es accedida mediante un método de clase.Los clientes (quienes quieren acceder a la clase Singleton) acceden a la única instancia mediante un método llamado getInstance().

En el siguiente bloque de codigo podemos ver como implementamos el patron de diseño singleton el cual permite restringir la creacion de objetos y garantizar la instanciacion de una sola clase, este patron se ve implementado en el prestamo de bicicletas en nuestro programa.

![GitHub Logo](https://github.com/paulagomez05/PatronesCreacionales/blob/master/1.png)

## Prototype
### Introducción
El patrón prototype tiene un objetivo muy sencillo: crear a partir de un modelo.Permite crear objetos prediseñados sin conocer detalles de cómo crearlos. Esto lo logra especificando los prototipos de objetos a crear. Los nuevos objetos que se crearán de los prototipos, en realidad, son clonados. Vale decir, tiene como finalidad crear nuevos objetos duplicándolos, clonando una instancia creada previamente.

![GitHub Logo](https://github.com/paulagomez05/PatronesCreacionales/blob/master/prototype.gif)

En el siguiente bloque de codigo podemos ver como implementamos el patron creacional prototype el cual permite realizar las clonaciones necesarias de las naves; es un patron muy funcional a la hora de necesitar la creacion de objetos parametrizados.

![GitHub Logo](https://github.com/paulagomez05/JuegoPrototype/blob/master/3.png)

## Factory Method
### Introducción

Factory Method es un patrón de creación de objetos y normalmente se suele usar para solucionar el problema que se presenta cuando tenemos que crear la instancia de un objeto pero a priori no sabemos aún que tipo de objeto tiene que ser, generalmente, porque depende de alguna opción que seleccione el usuario en la aplicación o porque depende de una configuración que se hace en tiempo de despliegue de la aplicación. Define la interfaz de creación de un cierto tipo de objeto, permitiendo que las subclases decidan que clase concreta necesitan instancias.

![GitHub Logo](https://github.com/paulagomez05/PatronesCreacionales/blob/master/factory.jpg)

En el siguiente bloque de codigo podemos ver como se puede implementar el patron creacional Factory Method 

<pre><code>
package FactoryMethod1;
public class Main
{
    public static void main(String[] args)
    {
         CreadorAbstracto creator = new Creador();
        IArchivo audio = creator.crear( Creador.AUDIO );
        audio.reproducir();
        IArchivo video = creator.crear( Creador.VIDEO );
        video.reproducir();
    }
}
// PRODUCTO, SEGUN UML//
package FactoryMethod2;
 public interface IArchivo
{
    public void reproducir();
}
// PRODUCTO CONCRETO, SEGUN UML//
package FactoryMethod2;
public class ArchivoAudio implements IArchivo
{
    public ArchivoAudio() {
    }
// CREADOR, SEGUN UML//    
    package FactoryMethod1;
 public abstract class CreadorAbstracto
{
    public static final int AUDIO = 1;
    public static final int VIDEO = 2;
    // --------------------------------
     public abstract IArchivo crear(int tipo);
}
// CREADOR CONCRETO, SEGUN UML// 
package FactoryMethod1;
public class Creador extends CreadorAbstracto
{
    public void Creador() {
    }
</code></pre>

## Abstract Factory 
### Introducción
Este patrón crea diferentes familias de objetos. Su objetivo principal es soportar múltiples estándares que vienen definidos por las diferentes jerarquías de herencia de objetos. Es similar al Factory Method, sólo que esta orientado a combinar productos. Se debe utilizar cuando Un sistema se debe configurar con una de entre varias familias de productos.

![GitHub Logo](https://github.com/paulagomez05/PatronesCreacionales/blob/master/abstract-factory.jpg)

AbstractFactory: declara una interfaz para la creación de objetos de productos abstractos.

ConcreteFactory: implementa las operaciones para la creación de objetos de productos concretos.

AbstractProduct: declara una interfaz para los objetos de un tipo de productos.

ConcreteProduct: define un objeto de producto que la correspondiente factoría concreta se encargaría de crear, a la vez que implementa la interfaz de producto abstracto.

Client: utiliza solamente las interfaces declaradas en la factoría y en los productos abstractos. 
Una única instancia de cada FactoryConcreto es creada en tiempo de ejecución. AbstractFactory delega la creación de productos a sus subclases FactoryConcreto.

En el siguiente bloque de codigo podemos ver como se puede implementar el patron creacional Abstract Factory

![GitHub Logo](https://github.com/paulagomez05/PatronesCreacionales/blob/master/color.png)

![GitHub Logo](https://github.com/paulagomez05/PatronesCreacionales/blob/master/amarillo.png)

## Builder
### Introducción

Permite la creación de un objeto complejo, a partir de una variedad de partes que contribuyen individualmente a la creación y ensamblación del objeto mencionado. Hace uso de la frase "divide y conquistarás". Por otro lado, centraliza el proceso de creación en un único punto, de tal forma que el mismo proceso de construcción pueda crear representaciones diferentes.

Los objetos que dependen de un algoritmo tendrán que cambiar cuando el algoritmo cambia. Por lo tanto, los algoritmos que estén expuestos a dicho cambio deberían ser separados, permitiendo de esta manera reutilizar dichos algoritmos para crear diferentes representaciones. 

![GitHub Logo](https://informaticapc.com/patrones-de-diseno/images/builder.jpg)

En el siguiente bloque de codigo podemos ver como se puede implementar el patron creacional Builer

<pre><code>
Vehiculo v = new Vehiculo();
v.NumPuertas = 5;
v.Matricula = "1034 CAA";
v.Faros = new Faro[4];
v.Faros[0] = new Faro(TipoFaro.Xenon);
v.Faros[1] = new Faro(TipoFaro.Xenon);
v.Faros[2] = new Faro(TipoFaro.Lexus);
v.Faros[3] = new Faro(TipoFaro.Lexus);
v.Color = "Rojo";
v.Motor = new Motor(TipoMotor.Gasolina);
v.Motor.Capacidad = 2200;
v.Motor.Valvulas = 12;

DirectorConstruccion director = new DirectorConstruccion (new ConstructorFordFiestaSportEdition());
Vehiculo v = director.ConstruirVehiculo();

</code></pre>
# Patrones Estructurales

## Decorator
### Introducción 

El patrón decorator permite añadir responsabilidades a objetos concretos de forma dinámica. Los decoradores ofrecen una alternativa más flexible que la herencia para extender las funcionalidades.
### Este patrón se debe utilizar cuando:
Hay una necesidad de extender la funcionalidad de una clase, pero no hay razones para extenderlo a través de la herencia.
Se quiere agregar o quitar dinámicamente la funcionalidad de un objeto.

![GitHub Logo](https://lh6.googleusercontent.com/vIoskk-tgi1crMhB0O-Cd3lQZwpYOEfs8_tPxCvTC5hK0yHjlIXHDIVLJa-gwRhoesr-BLI-nUhctVOn1FUAD6XWOVKtQNzUoZ8nayfwYarmy5JkpQ)

<pre><code>
public abstract class Combo {
  
 String descripcion = "";
  
 public String getDescripcion() 
 {
  return descripcion;
 }
 
 public abstract int valor();
 
}

public class ComboBasico extends Combo{
 
 public ComboBasico() {
  descripcion="Porcion de Papas Fritas, " +
   "salsa, queso, amburgueza sencilla, gaseosa";
 }
  
 @Override
 public int valor() {
  return 6200;
 }
}

public abstract class AdicionalesDecorator extends Combo{
 
 public abstract String getDescripcion();
}

public class Carne extends AdicionalesDecorator{
 
 Combo combo;
  
 public Carne(Combo combo)
 {
  this.combo=combo; 
 }
  
 @Override
 public String getDescripcion() {
  return combo.getDescripcion()+" , Porcion de Carne";
 }
 
 @Override
 public int valor() {
  return 2500+combo.valor();
 }
}
</code></pre>

## Adapter
### Introducción 

Como se ilustra en la imagen que encabeza este artículo, el patrón Adapter sirve para hacer que dos interfaces, en principio diferentes, puedan comunicarse. Para ello añadiremos un adaptador intermedio, que se encargará de realizar la conversión de una interface a otra.

Lo usaremos cuándo: necesitamos hacer compatibles dos interfaces, que de inicio no lo son. Muy útil cuando trabajamos con librerías externas. Una analogía con el mundo real sería la de un adaptador para utilizar un conector español en un enchufe americano.

Ventajas: hace que dos interfaces incompatibles, sean compatibles. Puede servir para encapsular clases que no controlamos, y que pueden cambiar.
Desventajas: como muchos patrones, añade complejidad al diseño. Hay quién dice que este patrón es un parche, utilizado en malos diseños.

![GitHub Logo](http://1.bp.blogspot.com/-DPJ5nnEdZ3s/Ubm18bwxqKI/AAAAAAAABSI/D-c_eLyYgmY/s1600/adapter.jpg)

En el siguiente bloque de codigo podemos ver como se puede implementar el patron estructural Adapter

<pre><code>

public class Cliente {

public static void main(String[] args) {
    Forma linea = new Linea();
    Forma rombo = new Rombo();
    Forma texto = new CuadroTexto();

    ArrayList<Forma> l = new ArrayList<Forma>();
    l.add(linea);
    l.add(rombo);
    l.add(texto);

    for (Forma f : l)
        f.dibuja();
}

}
public abstract class Forma {
abstract void dibuja();
}

public class Linea extends Forma{
@Override
void dibuja() {
    System.out.println("----------------------");
}
}

public class Rombo extends Forma {
@Override
void dibuja() {
    System.out.println("    *    ");
}

import javax.swing.JTextPane;

// es más complicada y necesita usar una libreria externa TextView

public class CuadroTexto extends Forma{

public JTextPane text = new JTextPane();

void dibuja() {
    text.setText("text");
    System.out.println(text.getText());
}
}
</code></pre>

## Bridge
### Introducción 

Este patrón debe ser utilizado cuando:
Se desea evitar un enlace permanente entre la abstracción y su implementación. Esto puede ser debido a que la implementación debe ser seleccionada o cambiada en tiempo de ejecución. Tanto las abstracciones como sus implementaciones deben ser extensibles por medio de subclases. En este caso, el patrón Bridge permite combinar abstracciones e implementaciones diferentes y extenderlas independientemente. Cambios en la implementación de una abstracción no deben impactar en los clientes, es decir, su código no debe tener que ser recompilado. 

Se desea compartir una implementación entre múltiples y este hecho debe ser escondido a los clientes.
Permite simplificar jerarquías demasiado pobladas.

![GitHub Logo](http://2.bp.blogspot.com/-LIWVkOwbj7Q/VD1vHPM97cI/AAAAAAAABlQ/eFFdxvxqgf0/s1600/00.jpg)

Se implementa de la siguiente forma
<pre><code>
interface Implementador {
    public abstract void operacion();
}
 
/** primera implementacion de Implementador **/
class ImplementacionA implements Implementador{
    public void operacion() {
        System.out.println("Esta es la implementacion A");
    }
}
/** segunda implementacion de Implementador **/
class ImplementacionB implements Implementador{
    public void operacion() {
        System.out.println("Esta es una implementacion de B");
    }
}
/** interfaz de abstracción **/
interface Abstraccion {
    public void operacion();
}
/** clase refinada que implementa la abstraccion **/
class AbstraccionRefinada implements Abstraccion{
    private Implementador implementador;
    public AbstraccionRefinada(Implementador implementador){
        this.implementador = implementador;
    }
    public void operacion(){
        implementador.operacion();
    }
}
/** aplicacion que usa el patrón Bridge **/
public class EjemploBridge {
    public static void main(String[] args) {
        Abstraccion[] abstracciones = new Abstraccion[2];
        abstracciones[0] = new AbstraccionRefinada(new ImplementacionA());
        abstracciones[1] = new AbstraccionRefinada(new ImplementacionB());
        for(Abstraccion abstraccion:abstracciones)
            abstraccion.operacion();
    }
}
</code></pre>


## Composite
### Introducción 

Se debe utilizar este patrón cuando:
Se busca representar una jerarquía de objetos como “parte-todo”.
Se busca que el cliente puede ignorar la diferencia entre objetos primitivos y compuestos (para que pueda tratarlos de la misma manera).

![GitHub Logo](https://danielggarcia.files.wordpress.com/2014/03/033014_1801_patronesest1.png?w=620)

<code><pre>
public abstract class AbstractCompositor {

   public abstract int getCosto();
   public abstract void agregarHoja(AbstractCompositor composicion);
}

public class Hoja extends AbstractCompositor {
 
 private int costo;
 public Hoja(int costo){
  this.costo = costo;
 }

 @Override
 public int getCosto() { 
  return this.costo;
 }

 @Override
 public void agregarHoja(AbstractCompositor composicion) {
  // metodo no se usa
 }
}
public class Libro extends AbstractCompositor {
 
 private int costo = 0;
 private List<AbstractCompositor> listaComposicion;
 
 /**
  * Constructor
  */
 public Libro (){
  listaComposicion = new ArrayList<AbstractCompositor>();
 }
 
 /**
  * Obtiene el costo del libro
  */
 @Override
 public int getCosto() { 
  return this.costo;
 }
 
 /**
  * Agrega las hojas y calcula su valor rapidamente.
  * @param composicion
  */
 public void agregarHoja(AbstractCompositor composicion){
  this.costo = this.costo + composicion.getCosto();
  this.listaComposicion.add(composicion);
 }
}
public static void main(String[] args) {
     AbstractCompositor componenteUno = new Hoja(10);

     System.out.println(componenteUno.getCosto());
     
     AbstractCompositor componenteTres = new Hoja(3);
     AbstractCompositor componenteDos = new Libro();
     
     componenteDos.agregarHoja(componenteUno);
     componenteDos.agregarHoja(componenteTres);
     
     System.out.println(componenteDos.getCosto());

 }
}
</code></pre> 

## Facade
### Introducción 
Se debe utilizar cuando:
Se quiera proporcionar una interfaz sencilla para un subsistema complejo.
Se quiera desacoplar un subsistema de sus clientes y de otros subsistemas, haciéndolo más independiente y portable.
Se quiera dividir los sistemas en niveles: las fachadas serían el punto de entrada a cada nivel. Facade puede ser utilizado a nivel aplicación.

![GitHub Logo](![GitHub Logo](https://danielggarcia.files.wordpress.com/2014/03/033014_1801_patronesest1.png?w=620))

Se implementa
<code><pre> 
public class FachadaImpresoraNormal {

    Impresora impresora;
    
    
    public FachadaImpresoraNormal(String texto) {
        super();
        impresora= new Impresora();
        impresora.setColor(true);
        impresora.setHoja("A4");
        impresora.setTipoDocumento("PDF");
        impresora.setTexto(texto);
    }


    public void imprimir() {
        
        impresora.imprimirDocumento();
    }
    
}


public class PrincipalCliente2 {

    public static void main(String[] args) {
        
        
        FachadaImpresoraNormal fachada1= new FachadaImpresoraNormal("texto1");
        fachada1.imprimir();
        
        FachadaImpresoraNormal fachada2= new FachadaImpresoraNormal("texto2");
        fachada2.imprimir();
        
        
        Impresora i3 = new Impresora();
        i3.setHoja("a4");
        i3.setColor(true);
        i3.setTipoDocumento("excel");
        i3.setTexto("texto 3");
        i3.imprimirDocumento();
    }

}
var peticion = $.ajax( "destino.php" ).done(function() {

           alert( "ok" );
})

var peticion2 = $.get( "destino.php",function() {

           alert( "ok" );
});

var peticion3 = $.post( "destino.php",function() {

           alert( "ok" );
});
</code></pre> 

## Proxy
### Introducción

Cuándo usarlo
En cualquier situación en que sea necesaria una referencia a un objeto más versátil y/o sofisticada que un simple puntero. Por ejemplo:
Un apoderado remoto proporciona un representante local para un objeto en un espacio de direcciones diferente (J.Coplien los llama embajadores).
Un apoderado virtual crea por demanda objetos costosos.
Un apoderado de protección restringe, por motivos de seguridad, el acceso a un objeto.
Una referencia “inteligente” es una sustitución por un simple puntero, que incorpora servicios adicionales como cuenta del número de referencias, carga de objetos persistentes en memoria cuando estos son referenciados y uso de cerrojos para controlar el acceso exclusivo a regiones críticas.

Su UML

![GitHub Logo](https://informaticapc.com/patrones-de-diseno/images/proxy.jpg)

Su implementacion
![GitHub Logo](http://1.bp.blogspot.com/-sZvdyV6QwLM/TekSnYtf6hI/AAAAAAAAJOU/oSaKfcnG1cs/s1600/proxy.png)
![GitHub Logo](http://2.bp.blogspot.com/-QdcAUINg4Jk/TekR73hGRKI/AAAAAAAAJOI/r7qM3MkJhWk/s1600/iguardar.png)
![GitHub Logo](http://2.bp.blogspot.com/-v6ZRwvV8vQQ/TekSA4j_jRI/AAAAAAAAJOM/F-Yhn7xuI0Y/s1600/ghd.png)
![GitHub Logo](http://4.bp.blogspot.com/-e1oqFWAfHHQ/TekSHMFMQXI/AAAAAAAAJOQ/aJdRYi28MlY/s1600/objetoremoto.png)
![GitHub Logo](http://1.bp.blogspot.com/-tP7jpNOSONM/TekS4HAS3wI/AAAAAAAAJOY/B02dHb406lI/s1600/guardardatos.png)

## Flyweight
### Introducción

Busca eliminar o reducir la redundancia cuando tenemos gran cantidad de objetos que contienen información idéntica, además de lograr un equilibrio entre flexibilidad y rendimiento (uso de recursos).
Este patrón quiere evitar el hecho de crear un gran número estados de objeto para representar a un sistema. Permite compartir estados para soportar un gran número de objetos pequeños aumentando la eficiencia en espacio.

![GitHub Logo](https://lh6.googleusercontent.com/U8FtCPlWF05eCqgwYsQuO4IPhNEbo2eD7-VD-Zpd-FcR7A9xO_rDVOg08QWkdM2tiO4T1p2CaQeTJfmehzwPoKfTAvX4bga8klpg9P2LxRlGuwLQu10)

Su implementacion 

![GitHub Logo](https://2.bp.blogspot.com/-3hrJHEDummc/Tej4FrXzW7I/AAAAAAAAJOE/eRZldykA53Y/s1600/main.png)


![GitHub Logo](https://2.bp.blogspot.com/-eD2_qB0aizQ/Tej3zXgntHI/AAAAAAAAJOA/YkhvXtEU7gg/s1600/alumno.png) 


### Referencias
 http://migranitodejava.blogspot.com.co 

 https://informaticapc.com 
 
 https://www.genbetadev.com/metodologias-de-programacion
