Abstract classes are classes that are not fully implemented.
Rule 1: If you define an abstract class you can have both concrete and abstract methods. But you must reuse your abstract methods in subclasses.
Example: 
abstract class Shape {
    abstract void draw();
    void sayHello() {
        System.out.println("Hello from Shape!");
    }
}

class Triangle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a tri.");
    }
}
Rule 2: If the method defines is abtract then the class must be an abstract class.
Example: 
public class Shape {
    abstract void draw();  //Error
    void sayHello() {
        System.out.println("Hello from Shape!");
    }
}
Rule 3: An abstract class extends an abstract class, an interface extends another interface, but class implements interface.

interface Shape {
    void consumesMemory ();  
}
abstract class Quadrilateral implements Shape {
    abstract void draw();
    void sayHello() {
        System.out.println("Hello from Quadrilateral!");
    }
}
  
class Square extends Quadrilateral  {
    @Override
    void draw() {
        System.out.println("Drawing a squ.");
    }
}

Rule 4: An abstract class is not required to implement the abstract methods of its parent class, nor is it required to implement the methods of an interface it implements.
Example:
interface Shape {
    void consumesMemory ();  
}
abstract class Quadrilateral implements Shape {
    abstract void draw();
    void sayHello() {
        System.out.println("Hello from Quadrilateral!");
    }
}
Rule 5: A class defined as final cannot be extended. A final method cannot be overriden.

final class Shape {
    void consumesMemory ();  
}
abstract class Quadrilateral extends Shape {  //compile error
    abstract void draw();
    void sayHello() {
        System.out.println("Hello from Quadrilateral!");
    }
}
Rule 6:If a non-abstract class extends an abstract class that implements an interface, the class is required to override both the abstract methods from the extended class and the methods from the interface.

interface Shape {
    void consumesMemory ();  
}
abstract class Quadrilateral implements Shape {
    abstract void draw();
    void sayHello() {
        System.out.println("Hello from Quadrilateral!");
    }
}
public class Edge extends Quadrilateral {
   public void consumesMemory(){  
      System.out.println("Edge consumes memory!");
    }
    public void draw(){
       System.out.println("Edge is drawn");
    }
}

In summary, if the child class is abstract, it is not required to implement the abstract methods of the interface or abstract class.
However, if the child class is not declared abstract (i.e., it is concrete), it must implement all the abstract methods from both the
abstract class and the interface it implements.

Rule 7:A class can extend only one class (No multiple inheritance). But a class can implement multiple interfaces.
Also, interfaces can extend multiple interfaces.
Example:
public class Shape extends Quadrilateral,Triangle{  //Error   // Quadrilateral,Triangle are classes.

public class TV implements Usb, Screen{

