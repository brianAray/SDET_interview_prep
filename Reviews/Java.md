# Java
## Java Orientation
---
- **Language Overview**
    - Java is a programming language used for software development
    - Java is an object-oriented language
        - It is based on the concepts of objects, which are instances of classes that encapsulate data and behavior
    - Java is platform-independent so the same code can be run on multiple platforms without modification
- **JDK, JRE, JVM**
    - **Java Development Kit**
        - Software development kit used for developing Java applications
    - **Java Runtime Environment**
        - Software environment used for running Java applications
    - **Java Virtual Machine**
        - A virtual machine that runs Java bytecode
    - The JDK includes teh JRE, as well as a set of tools and libraries for developing Java apps, like:
        - Java Compiler
        - Java Debugger
    - The JRE includes the JVM, as well as libraries and tools for running Java applications, but does **not** include the development tools
    - The JVM is responsible for executing Java bytecode
        - The compiled form of Jva code
    - Java applications are written in Java code, which is compiled to Java bytecode using the Java compiler in the JDK
    - The Java bytecode is then executed by the JVM, which translates it into machine code that can be run on the underlying hardware and operating system
- **Compilation Process**
    - Java code is written in plain text using a text editor or IDE and saved as a `.java` file
    - The compiler checks the syntax and semantics of the code then generates bytecode for the JVM to execute
    - The bytecode is saved in a file with the `.class` extension which can be executed on any platform that has a JVM installed
    - The bytecode is not machine code, it is an intermediate that can be translated into machine code by the JVM at runtime
## Java Basics
---
- **Primitive Types**
    - Java has 8 primitive data types, used to represent basic values
    - Primitives are stored directly in memory, which makes them faster to access and more efficient than objects
        - `boolean`
            - represents a single bit of information, and can have values of `true` or `false`
        - `byte`
            - 8-bit integer
        - `short`
            - 16-bit integer
        - `int`
            - 32-bit integer
        - `long`
            - 64-bit integer
        - `float`
            - 32-bit floating point number
        - `double`
            - 64-bit floating point number
        - `char`
            - Single 16-bit unicode character
    - Java has corresponding wrapper classes for each primitive type
        - Used to convert between primitive types and objects
- **Working with Basic Operators**
    - Java has a variety of operators that can be used to perform arithmetic, logical, and bitwise operations.
        - **Arithmetic Operators**
            - Addition `+`
                - `5 + 5`
            - Subtraction `-`
                - `10 - 4`
            - Multiplication `*`
                - `4 * 4`
            - Division `/`
                - `5 / 3`
            - Modulus `%`
                - Modulus is finding the remainder after division
                - `5 % 2` would be 1
            - Increment `++`
                - Increases the value of a variable by 1
            - Decrement `--`
                - Decreases the value of a variable by 1
        - **Logical Operators**
            - Logical operators are used to determine the logic between variables or values
                - And `&&`
                - Or `||`
                - Not `!`
        - **Comparison Operators**
            - Comparison operators are used to compare two values or variables
            - This lets us find answers and make decisions
            - The return value of a comparison is either `true` or `false`
                - Equal to `==`
                - Greater than `>`
                - Greater than or equal to `>=`
                - Less than `<`
                - Less than or equal to `<=`
        - **Bitwise Operators**
            - These are not used commonly, but are for operations on binary values
                - And (&)
                - Or (|)
                - Exclusive or (^)
                - Shift left (<<)
                - Shift right (>>)
                - Unsigned shift right (>>>)
        - **Assignment Operators**
            - Assignment (=)
                - `x = 5`
            - `+=`
                - `x += 3` is the same as `x = x + 3`
            - `-=`
                - `x -= 3` is the same as `x = x - 3`
            - `*=`
                - `x *= 3` is the same as `x = x * 3`
            - `/=`
                - `x /= 3` is the same as `x = x / 3`
            - `%=`
                - `x %= 3` is the same as `x = x % 3`
    - Operators can be used with variables, literals, and expressions to perform various computations
    - The order of operations, or operator precedence, determines the order in which operators are evaluated
    - Parenthesis override the default order of operations
- **Flow Control Statements**
    - Flow control statements are used to control the order in which statements are executed in a Java program
    - Here are the common ones:
        - `if` statement is used to test a condition and execute different code depending on the result:
            - ```java
              if (x > 5) {
                System.out.println("x is greater than 5");
              } else {
                System.out.println("x is less than or equal to 5");
              }
        - `for` statement is used to loop through a block of code a specified number of times
            - ```java
              for (int i = 0; i < 10; i ++){
                System.out.println(i);
              }
        - `while` statement is used to loop through a block of code as long as a condition is true
            - ```java
              int i = 0;
              while(i < 10){
                System.out.println(i);
                i++;
              }
        - `do-while` statement is used like the `while` loop, however it always executes the block at least once
            - ```java
              int i = 0;
              do{
                System.out.println(i);
                i++
              } while(i < 10);
        - `switch` statement is used to select one of many blocks of code to execute based on the value of an expression
            - ```java
              int chosenFlavor = 2;
              switch (chosenFlavor){
                case 1:
                    System.out.println("Chocolate is your favorite!");
                    break;
                case 2:
                    System.out.println("Vanilla is your favorite!");
                    break;
                default:
                    System.out.println("You have not chosen a valid flavor!");
                    break;
              }
    - Flow control can be nested and combined to create complex programs
    - Be careful not to create infinite loops
- **Arrays**
    - This is a data structure used to store a fixed number of elements of the same type
    - To declare an array, you must specify the type of the elements and the number of elements in the array
        - ```java
          int[] numbers = new int[5];
        - This declares an array named `numbers` that can store 5 integer values
        - You can also declare an array and instantiate it with values at the same time
        - ```java
          int[] numbers = {1, 2, 3, 4, 5};
        - Note the use of `{}` instead
    - Arrays in Java are zero-indexed, meaning the first element in the array has an index of 0, the second is 1, and so forth
    - To access an eelemnt from the array, we use the square bracket notation
        - `numbers[0]` would access the first element of the numbers array
    - You can assign values to arrays with the square bracket notation and the assignment operator
        - `numbers[0] = 42` assigns the value of 42 to the first element of the `numbers` array
- **Debugging**
    - It is the process of finding and fixing errors in software code
    - It is an invaluable skill for any developer, and there are a number of tools that can aid in the process
    - Common debugging techniques:
        - **Using print statements**
            - The simplest and most common way of debugging
            - You can add print statements to your code to see the value of variables or to check if a certain block of code is executed
            - ```java
              int x = 5;
              System.out.println("Value of x: " + x);
        - **Using a Debugger**
            - A debugger is a tool that allows you to step through your code line by line, set breakpoints, and examine variables and their values at each step
            - This is typically in built in your IDE
        - **Exception Handling**
            - Exceptions are a way of handling errors that occur during program executions
            - Try-Catch blocks can catch exceptions and print out their error messages to help debug your code
            - ```java
              try{
                int[] arr = {1, 2, 3};
                System.out.println(arr[3]);
              }catch(Exception e){
                System.out.println(e);
              }
- **Variable scopes**
    - Variable scopes refer to the range within which a variable can be accessed or used
    - The scope of the variable is determined by where it is declared in the code
    - There are four types of variable scopes in Java:
        - **Class Level Scope**
            - Variables declared at the class level have class-level scope
            - This means they can be accessed by any method in the class
            - ```java
              public class MyClass{
                int myVariable = 20;
                static int myStaticVariable = 40;
                
                public static void main(String[] args){
                    // Accessing static variable
                    System.out.println("static variable value: " + myStaticVariable);
                }

                public void printVariable(){
                    // Accessing instance variable
                    System.out.println("Instance variable value: " + myVariable);
                }
              }
        - **Method Level Scope**
            - Variables declared inside a method have method-level scope
            - They can only be accessed within the method they are declared in
            - ```java
              public class MyClass {
                  public static void main(String[] args) {
                      int myVariable = 10;
              
                      if (myVariable == 10) {
                          // Accessing variable declared inside if block
                          int anotherVariable = 20;
                          System.out.println("Variable value: " + anotherVariable);
                      }
              
                      // This will give compilation error as the variable is out of scope
                      // System.out.println("Variable value: " + anotherVariable);
                  }
              }
        - **Block Level Scope**
            - Variables declared inside a block, such as a loop or if statement, have block level scope
            - They can only be accessed within the block they are declared in
            - A block is anything that is between two curly braces `{}`
            - ```java
              public class MyClass {
                  public static void main(String[] args) {
                      for (int i = 0; i < 5; i++) {
                          // Accessing variable declared inside for loop block
                          int myVariable = i;
                          System.out.println("Variable value: " + myVariable);
                      }
              
                      // This will give compilation error as the variable is out of scope
                      // System.out.println("Variable value: " + myVariable);
                  }
              }
## Java Methods
---
- **Methods**
    - A method is a block of code that performs a specific task and can be called by other parts of the program.
    - Methods are used to organize and modularize code, reduce code duplication, and improve code readability and maintainability.
    - A method can have zero or more parameters and can return a value or be declared as `void` if it does not return any value.
- **Method Signature**
    - The method signature is a combination of the method name and parameter list, and is used to uniquely identify a method in a class.
    - The method signature consists of the method name, the number and types of parameters, and the return type of the method.
    - Two methods with the same name but different parameter lists or return types are considered to have different method signatures.
- **Method Overloading**
    - Method Overloading is a feature in Java that allows a class to have multiple methods with the same name but different parameter lists
    - Method overloading enables you to reuse the same method name with different inputs
    - When calling an overloaded method, the compiler determines which method to call based on the number and types of arguments passed
- **Method Overriding**
    - Method Overriding allows a child class to provide its own implementation of a defined method in the parent class
    - Method Overriding is used to achieve Polymorphism in Java, where objects of different classes can be treated as objects of a common superclass.
- **Example**
    - ```java
      public class MethodExample {
      
        // Method with no parameters and no return value
        public void sayHello() {
          System.out.println("Hello!");
        }
      
        // Method with two parameters and an integer return value
        public int addNumbers(int num1, int num2) {
          return num1 + num2;
        }
      
        // Method with the same name as addNumbers, but different parameter types
        public double addNumbers(double num1, double num2) {
          return num1 + num2;
        }
      
        // Method that overrides the toString() method in Object class
        @Override
        public String toString() {
          return "This is an example object";
        }
      
      }
- **Testing through the main() method**
    - Testing approach where the test cases are executed through the `main()` method of a Java program
    - This is also known as the Application Testing approach
    - Steps to follow it:
        - Create a separate Java class for testing that only contains a `main()` method that will execute test cases
        - Import the Java classes to be tested
        - Write test cases that cover all the functionality of the Java classes being tested
        - Execute the test cases by running the `main()` method
        - Verify the results
## Java Classes
---
- **Inheritance**
    - A way of creating a new class from an existing one by inheriting the properteis and behaviors of the existing class
    - Allows for code reuse and helps with creating a hierarchy of classes
    - ```java
      public class Animal {
        public void eat(){
            System.out.printlng("The animal is eating");
        }
      }

      public class Dog extends Animal{
        public void bark(){
            System.out.printlng("The dog barks!");
        }
      }
- **Polymorphism**
    - The ability of objects to take on different forms and behave differently based on their context
    - Achieved through method overriding and method overloading
    - ```java
      public class Vehicle {
        public void makeSound(){
            System.out.println("The vehicle makes a sound");
        }
      }

      public class Car extends Vehicle {
        // Overriding the makeSound inherited from Vehicle
        public void makeSound(){
            System.out.println("The Car goes vroom!");
        }
      }
- **Encapsulation**
    - The idea of bundling data and methods that operate on that data within a single unit or class, and controlling access to that data through access modifiers
    - Helps with creating more secure and maintainable code
    - ```java
      public class Person{
        private String name;
        private int age;

        public String getName(){
            return name;
        }

        public void setName(String name){
            this.name = name;
        }

        public int getAge(){
            return age;
        }

        public void setAge(int age){
            this.age = age;
        }
      }
- **Abstraction**
    - The process of hiding complex implementation details and providing a simplified view of a system or component to its users
    - Helps with managing complexity and making code more reusable and maintainable
    - ```java
      public abstract class Animal {
        public abstract void makeSound();
      }

      public class Dog extends Animal {
        public void makeSound(){
            System.out.println("The Dog Barks!");
        }
      }
- **Classes and Objects**
    - **Class**
        - The blueprint or template for creating objects
            - An object is an instance of a class
        - Classes contain attributes (fields/properties) and methods that define the behaviors of objects
        - ```java
          public class Person {
            private String name;
            private int age;

            public Person(String name, int age){
                this.name = name;
                this.age = age;
            }

            public void sayHello(){
                System.out.println("Hello, my name is " + name);
            }
          }
    - **Objects**
        - Objects are instances of classes, and take on the properties given to it in classes
        - Objects are instantiated using the `new` keyword and a reference to the class that is used as the template to instantiate it
        - Objects occupy the heap in memory, and are referred to using their reference
        - If an object reference goes out of scope, or is not assigned to an object then it will be removed from memory
            - For example, if an object is created inside of a method, once the method is finished and the object reference is not returned, the object in memory will be removed
        - ```java
          Person person = new Person("John", 30);
          person.sayHello(); // Outputs: Hello, my name is John
- **Interfaces**
    - In Java, an interface is a collection of abstract methods that are used to define a set of behaviors that a class can implement
    - An interface is defined using the `interface` keyword
    - An interface can contain:
        - Constants
        - Abstract methods
        - Default methods
        - Static methods
    - ```java
      public interface MyInterface {
        // constant declarations
        int MAX_SIZE = 100;
        String DEFAULT_NAME = "John";

        // abstract method signatures
        void doSomething();
        String getName();

        // default method implementations
        default void doSomethingElse() {
            System.out.println("Doing something else");
        }

        // static method signatures
        static void printHello() {
            System.out.println("Hello");
        }
      }
    - An interface cannot be instantiated, instead it needs to be `implemented` by another class
    - When a class implements an interface, it must implement any `abstract` methods declared
    - ```java
      public class MyClass implements MyInterface {
        public void doSomething(){
            System.out.println("Do Something!");
        }
      }
- **Abstract Classes**
    - An abstract class is a class that cannot be instantiated and is typically used as a base class for other classes to extend
    - An Abstract class can contain:
        - Instance variables
        - Abstract methods
        - Concrete methods
        - Constructors
    - An abstract class cannot be instantiated however, and must be extended by another class in order to access the properties inside it
    - ```java
      public abstract class Shape {
          private String color;
          
          public Shape(String color) {
              this.color = color;
          }
          
          public String getColor() {
              return color;
          }
          
          public void setColor(String color) {
              this.color = color;
          }
          
          public abstract double getArea();
          
          public abstract double getPerimeter();
          
          public void printDetails() {
              System.out.println("Color: " + color);
              System.out.println("Area: " + getArea());
              System.out.println("Perimeter: " + getPerimeter());
          }
          
          // Concrete method
          public double calculateDiameter(double radius) {
              return radius * 2;
          }
      }
    - The `Shape` class is declared as `abstract`
    - It contains an instance variable `color`
    - There are two abstract methods `getArea()` and `getPerimeter()` that have no implementation
- **Constructors**
    - This is a special method that is called when an object of a class is created
    - It is used to initialize the object's attributes and perform any necessary setup
    - It can be overloaded to provide different ways of creating objects
    - ```java
      public class Person{
        private String name;
        private int age;

        public Person(String name, int age){
            this.name = name;
            this.age = age;
        }

        public Person(String name){
            this.name = name;
            this.age = 0;
        }

        public Person(int age){
            this.name = "Empty";
            this.age = age;
        }
      }

      Person person1 = new Person("John", 30);
      Person person2 = new Person("Mike");
      Person person3 = new Person(30);
    - The constructor method will be called based on the arguments passed into it
- **Access Modifiers**
    - Access Modifiers define the level of access to a class, method, or variable
    - There are four access modifiers in Java
        - `public`
            - A public class, method, or variable can be accessed from anywhere in the program
            - It has the widest scope
        - `private`
            - A private class, method, or variable can only be accessed with the same class in which it is declared
        - `protected`
            - A protected class, method, or variable can only be accessed within the same package or by subclasses in other packages
        - `default` (no modifier)
            - A class, method, or variable with no access modifier is only accessible within the same package
    - ```java
      public class Car {
          private String make;
          protected String model;
          int year;
          public String color;
          
          public Car(String make, String model, int year, String color) {
              this.make = make;
              this.model = model;
              this.year = year;
              this.color = color;
          }
          
          private void startEngine() {
              // code to start the engine
          }
          
          protected void accelerate() {
              // code to accelerate the car
          }
          
          void stop() {
              // code to stop the car
          }
      }
      
      class Main {
           public static void main(String[] args) {
              Car myCar = new Car("Toyota", "Camry", 2022, "Blue");
              myCar.startEngine(); // this will not compile because startEngine() is private
              myCar.accelerate(); // this is allowed because accelerate() is protected
              myCar.stop(); // this is allowed because stop() is default (no modifier)
              System.out.println(myCar.color); // this is allowed because color is public
          }
      }
- **Non Access Keywords**
    - Non-access keywords are used in Java for defining different aspects of a class or method
    - Some common non-access keywords are:
        - `final`
            - When applied to a variable, it indicates that the value of the variable cannot be changed once assigned
            - When applied to a method, it indicates that the method cannot be overridden by a subclass
            - When applied to a class, it indicates that the class cannot be subclassed
        - `static`
            - Indicates that a member variable or method belongs to the class instead of the instance of the class
            - This means it can be accessed without creating an instance of the class
            - ```java
              public final class MyConstants {
                  public static final int MAX_SIZE = 100;
                  public static final String MESSAGE = "Hello, world!";
              }
        - `abstract`
            - Indicates that a class or method is incomplete and needs to be extended by another class
            - Abstract classes cannot be instantiated, and abstract methods must be implemented by the class that extends the abstract class
## Maven
---
- **Intro to Maven**
    - Maven is a build automation tool for Java projects
    - It automates the build process, including compilation, packaging, and distribution
    - Maven uses a Project Object Model (POM) to manage project dependencies, build profiles, and plugins
- **Central Repository**
    - Maven Central Repository is a public repository of artifacts for use with Maven
    - Artifacts are versioned and can be downloaded and used as dependencies in Maven Projects
- **XML and POM**
    - The Project Object Model (POM) is an XML file that describes a Maven project
    - Contains project metadata, dependencies, build settings, and plugins
    - Allows creation of multiple build profiles for different environments
    - Plugins are used to extend the build process, such as for testing, code coverage, and deployment
## Java Collection
---
- **Overview of Collection Hierarchy**
    - A hierarchy of interfaces / classes that represent a group of objects as a single entity
    - It is used to provide different ways of storing and manipulating groups of elements
    - The root interface is `Collection`
    - Subinterfaces: `List`, `Set`, `Queue`, and `Dequeue`
    - `List` and `Set` are the most commonly used interfaces
- **List Interface**
    - List is an ordered collection of elements that allows duplicate entries
    - It extends the `Collection` interface and defines behavior for elements that are ordered, allowing positional access
    - Common implemtations: `ArrayList`, `LinkedList`
    - ```java
      List<String> list = new ArrayList<>();
      list.add("apple");
      list.add("banana");
      list.add("orange");
      System.out.println(list.get(1)); // Output: banana
- **Set Interface**
    - Set is a collection of elements with no duplicate entries
    - It extends the `Collection` interface, and does not allow positional access
    - Common implementations: `HashSet`, `TreeSet`
    - ```java
      Set<String> set = new HashSet<>();
      set.add("apple");
      set.add("banana");
      set.add("orange");
      System.out.println(set.size()); // Output: 3
- **Map Interface**
    - Map is a collection of key-value pairs where each key is unique
    - It provides a way of looking up a value based on its associated key
    - Common implementations: `HashMap`, `TreeMap`
    - ```java
      Map<String, Integer> map = new HashMap<>();
      map.put("apple", 1);
      map.put("banana", 2);
      map.put("orange", 3);
      System.out.println(map.get("banana")); // Output: 2
- **Generics**
    - Generics provide a way to specify the type of objects that a collection can hold at compile time
    - By specifying the type of objects, it allows for type safety, and prevents errors at runtime
    - It can be used with the Collection interfaces and classes
    - ```java
      List<String> list = new ArrayList<>();
      Map<String, Integer> map = new HashMap<>();
    - The generic go in between the angle brackets `<>`
## Exceptions
---
- **Reading a Stack Trace**
    - A stack trace is a report of the function call hierarchy that is currently in the execution stack
    - The stack is a representation of the order in which methods are being called
    - As a new method is called, it is added onto the stack, and when it resolves it is removed from the stack
    - When an exception is thrown, a stack trace is printed to help the programmer diagnose the problem
    - ```
      Exception in thread "main" java.lang.NullPointerException
          at com.example.myproject.Book.getTitle(Book.java:16)
          at com.example.myproject.Author.getBookTitles(Author.java:25)
          at com.example.myproject.CoAuthor.getBookTitles(CoAuthor.java:19)
          at com.example.myproject.Main.main(Main.java:10)
    - This stack trace indicates that a `NullPointerException` occurred on line 16 of the `Book` class
- **Errors vs Exceptions**
    - Errors and exceptions are both types of throwable object in Java
    - `Throwable` is an interface that is the inherited by both errors and exceptions
    - Errors are serious problems that cannot be handled by the application such as running out of memory
    - Exceptions are less severe problems that can be handled by the application
- **Handling Exceptions**
    - Exceptions can be handled in a try-catch block
    - When an exception is thrown, the catch block is executed, allowing the program to recover from the exception
    - There is also an addition `finally` block that can be included that will always run at the end of the try-catch block even if an exception occurs
    - ```java
      try {
          // code that might throw an exception
      } catch (ExceptionType e) {
          // code to handle the exception
      } finally {
          // code to run at the end of the try catch block
      }
- **Checked vs Unchecked Exceptions**
    - There are two types of excpetions: Checked and Unchecked
    - Checked exceptions are exceptions that must be caught or decalred in the method signature using the `throws` keyword
        - Examples: `IOException` and `SQLException`
    - Unchecked exceptions do not need to be caught or declared
        - Examples: `NullPointerException` and `ArrayIndexOutOfBoundsException`
    - If you do not handle a checked exception and decide to throw it instead
        - ```java
          public int getAge() throws Exception {
            // code that throws checked exception but not handled with try catch
          }
- **Creating Custom Exceptions**
    - Custom exceptions can be created by extending the `Exception` or `RuntimeException` class
    - Custom exceptions can be used to add more information to the exception message or to differentiate between different types of exceptions
    - ```java
      public class MyException extends Exception {
          public MyException(String message) {
              super(message);
          }
      }
- **Try-With-Resources**
    - The try-with-resources statement is a Java 7 feature that allows resources to be automatically closed after they are used
    - The try-with-resources statement uses a try-catch block to declare and initialize one or more resources and automatically closes the resources when the try block is exited
    - Resources that can be closed need to implement `Closeable` interface
    - An example of something that needs to be closed could be files or a database connection
    - ```java
      try (BufferedReader reader = new BufferedReader(new FileReader("file.txt"))) {
          String line = reader.readLine();
          while (line != null) {
              System.out.println(line);
              line = reader.readLine();
          }
      } catch (IOException e) {
          // handle the exception
      }