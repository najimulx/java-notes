# java-notes
Java notes for DSC java class

### The Java compiler(javac)

* javac turns Java source code into a compiled class that contains Java virtual machine byte-code.

* By convention, source files are named with a .java extension; 

* The resulting class files have a .class extension.

* javac allows you one public class per file and insists the file have the same name as the class.

* If the filename and class name don’t match, javac issues a compilation error.

### JVM (Java Virtual Machine)

* The JVM has two primary functions:  to allow Java programs to run on any device or operating system (known as the "Write once, run anywhere" principle).

* Technical definition: The JVM is the specification for a software program that executes code and provides the runtime environment for that code.

* Garbage collection
Before Java, all program memory was managed by the programmer. In Java, program memory is managed by the JVM. The JVM manages memory through a process called garbage collection, which continuously identifies and eliminates unused memory in Java programs. Garbage collection happens inside a running JVM.


# JAVA BASICS


### Data Types


|Type| Size(bytes) |
|---|---|
|Byte |     1  | 
|Short  |   2  |
|Int   |    4 |
|long   |  8 |
|float   |  4 |
|double  |  8 |
|char   |   2 |
|boolean |  true or false|



### Access Specifiers

* public
* private
* protected

1. public access specifier:- If you declare any variable/ function as public access specifier so you can used it from anywhere of the program.
Syntax:-
< Access Specifier >     data type     variable /function ;
Ex:-
public int number;

2. private access specifier:- If you declare any variable/ function as private access specifier so you can used within the java class itself, not from outside the class, package and others.
Syntax:-
< Access Specifier >     data type     variable / function;
Ex:-
private int number=10;

3. protected access specifier:- If you want to access the private variable of parent class within your child class so you can declare those variable as protected. If your variable/method is declared aas protected so that variables/methods can be access same Class name, Package name, and sub class.
Syntax:-
< Access Specifier >     data type     variable / function;
Ex:-
protected int number=10; 


# OOP Concepts

### Classes and Objects

*Classes* : Java is a true object-oriented language and therefore the underlying structure of all java programs is classes. Anything we wish to represent in a java program must be encapsulated in a class that defines the state and behaviour of the basic program components known as objects.

```
 //start of class Person
Class Person
 {
 		//Start of Main Method
	public static void main(String args[])
  	 {
	  
            Person p = new Person();
		   
          } //End of Main Method
		  
 } //End of Person Class
```



*Objects* : An object is anything that really exists in the world and can be distingushed from others. Every thing that we see physically will come into this definition, for example:- human being, a book, tree, a table, a pen, and so on.

Collection of objects is called class. It is a logical entity.

### Inheritance 

Different kinds of objects often have a certain amount in common with each other.

Object-oriented programming allows classes to inherit commonly used state and behavior from other classes.

When one object acquires all the properties and behaviours of parent object i.e. known as inheritance. It provides code reusability. It is used to achieve runtime polymorphism

The class which inherits the properties of other is known as subclass (derived class, child class) and the class whose properties are inherited is known as superclass (base class, parent class).

_extends_ is the keyword used to inherit the properties of a class.


Using extends keyword, the My_Calculation inherits the methods addition() and Subtraction() of Calculation class.



```
class Calculation {
   int z;
	
   public void addition(int x, int y) {
      z = x + y;
      System.out.println("The sum of the given numbers:"+z);
   }
	
   public void Subtraction(int x, int y) {
      z = x - y;
      System.out.println("The difference between the given numbers:"+z);
   }
}

public class My_Calculation extends Calculation {
   public void multiplication(int x, int y) {
      z = x * y;
      System.out.println("The product of the given numbers:"+z);
   }
	
   public static void main(String args[]) {
      int a = 20, b = 10;
      My_Calculation demo = new My_Calculation();
      demo.addition(a, b);
      demo.Subtraction(a, b);
      demo.multiplication(a, b);
   }
}
```


### Interface

The interface is a mechanism to achieve fully abstraction in java. There can be only abstract methods in the interface. It is used to achieve fully abstraction and multiple inheritance in Java. Interface also represents IS-A relationship. It cannot be instantiated just like abstract class.


An interface is a reference type in Java. It is similar to class. It is a collection of abstract methods. A class implements an interface, thereby inheriting the abstract methods of the interface.

Along with abstract methods, an interface may also contain constants, default methods, static methods, and nested types. Method bodies exist only for default methods and static methods.

An interface is similar to a class in the following ways −

   An interface can contain any number of methods.

   An interface is written in a file with a .java extension, with the name of the interface matching the name of the file.

   The byte code of an interface appears in a .class file.

   Interfaces appear in packages, and their corresponding bytecode file must be in a directory structure that matches the package name.

However, an interface is different from a class in several ways, including −

   You cannot instantiate an interface.

   An interface does not contain any constructors.

   All of the methods in an interface are abstract.

   An interface cannot contain instance fields. The only fields that can appear in an interface must be declared both static and final.

   An interface is not extended by a class; it is implemented by a class.

   An interface can extend multiple interfaces.
   
   ```
   /* File name : Animal.java */
interface Animal {
   public void eat();
   public void travel();
}
   ```
   
   #### implementation
   ```
   /* File name : MammalInt.java */
public class MammalInt implements Animal {

   public void eat() {
      System.out.println("Mammal eats");
   }

   public void travel() {
      System.out.println("Mammal travels");
   } 

   public int noOfLegs() {
      return 0;
   }

   public static void main(String args[]) {
      MammalInt m = new MammalInt();
      m.eat();
      m.travel();
   }
} 
   ```






### Polymorphism

When one task is performed by different ways i.e. known as polymorphism. For example: to convense the customer differently, to draw something e.g. shape or rectangle etc.

Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object.

Any Java object that can pass more than one IS-A test is considered to be polymorphic.
```
public interface Vegetarian{}
public class Animal{}
public class Deer extends Animal implements Vegetarian{}
```


Now, the Deer class is considered to be polymorphic since this has multiple inheritance. Following are true for the above examples −

   A Deer IS-A Animal
   
   A Deer IS-A Vegetarian
   
   A Deer IS-A Deer
   
   A Deer IS-A Object
   
   
   When we apply the reference variable facts to a Deer object reference, the following declarations are legal −
   
 ```
Deer d = new Deer();

Animal a = d;

Vegetarian v = d;

Object o = d;
```





### Abstraction

Abstraction refers to the act of representing essential features without including background details or exceptions. Abstraction refers to the ability to make a class abstract in Object oriented programming. 

A class which contains the abstract keyword in its declaration is known as abstract class.

   * Abstract classes may or may not contain abstract methods, i.e., methods without body ( public void get(); )

   * But, if a class has at least one abstract method, then the class must be declared abstract.

   * If a class is declared abstract, it cannot be instantiated.

   * To use an abstract class, you have to inherit it from another class, provide implementations to the abstract methods in it.

   * If you inherit an abstract class, you have to provide implementations to all the abstract methods in it.
   
   
```
/* File name : Employee.java */
public abstract class Employee {
   private String name;
   private String address;
   private int number;

   public Employee(String name, String address, int number) {
      System.out.println("Constructing an Employee");
      this.name = name;
      this.address = address;
      this.number = number;
   }
   
   public double computePay() {
     System.out.println("Inside Employee computePay");
     return 0.0;
   }
   
   public void mailCheck() {
      System.out.println("Mailing a check to " + this.name + " " + this.address);
   }

   public String toString() {
      return name + " " + address + " " + number;
   }

   public String getName() {
      return name;
   }
 
   public String getAddress() {
      return address;
   }
   
   public void setAddress(String newAddress) {
      address = newAddress;
   }
 
   public int getNumber() {
      return number;
   }
}
```

### Encapsulation

The wrapping up of data and methods into a single unit (called class) is known as Encapsulation.
n encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as data hiding.

To achieve encapsulation in Java
1 : Declare the variables of a class as private.
2 : Provide public setter and getter methods to modify and view the variables values.

```
/* File name : EncapTest.java */
public class EncapTest {
   private String name;
   private String idNum;
   private int age;

   public int getAge() {
      return age;
   }

   public String getName() {
      return name;
   }

   public String getIdNum() {
      return idNum;
   }

   public void setAge( int newAge) {
      age = newAge;
   }

   public void setName(String newName) {
      name = newName;
   }

   public void setIdNum( String newId) {
      idNum = newId;
   }
}
```

#### Refer [Tutorial Point](https://www.tutorialspoint.com/java) for more


