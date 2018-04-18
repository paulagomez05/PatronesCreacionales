# Patrones Creacionales

### Integrantes
1. Paula Andrea Gomez - 20152020927
2. Juan Arias Ortegon - 20161020522
3. Jorge Escobar Bohorquez - 20152020120

## Sinlgeton
### Introducción 


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

En el siguiente bloque de codigo podemos ver como implementamos el patron creacional Factory Method 

