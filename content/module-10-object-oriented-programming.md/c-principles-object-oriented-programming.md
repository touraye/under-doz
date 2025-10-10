## Principles of Object Oriented Programming

Now we have an understand of Object Oriented Programming is time we dive into the **four principles** of Object Oriented Programming which are encapsulation, abstraction, inheritance, and polymorphism. These are the core of Object Oriented Programming understanding them will help you design better systems using OOP approaches.  

To best explain these four principles of **OOP** we will have to design a School system where we have different **users** such as Person, Teacher and Student. You will see how these four principles of **OOP** will help.

1. **Encapsulation:** 

   1. **Definition**: Encapsulation is the concept of bundling the data (attributes) and the methods (functions) that operate on the data into a single unit or class. It also involves restricting access to some of the object's components, which is achieved through access modifiers (like `private`, `protected`, and `public`).

   2. **Purpose**: This principle helps in protecting the internal state of the object from unintended or harmful modifications and provides a controlled interface for interacting with the data.

      ```java
       class Person {
          private String name;
          private int age;
      
          public Person(String name, int age){
              this.name = name;
              this.age = age;
          }
          
          // getter for each instance variable
      }
      ```

2. **Inheritance:** 

   1. **Definition**: Inheritance allows a new class (subclass or derived class) to inherit the properties and behavior (methods) of an existing class (superclass or base class). The subclass can also add its own properties and methods or override the methods of the superclass.

   2. **Purpose**: This principle promotes code reusability and establishes a natural hierarchy between classes.

   3. ```mermaid
      classDiagram
            Person <|-- Student
            Person <|-- Teacher  
      ```

      ```java
      // Teacher class inherite from a Person class
       class Teacher extends Person {
          private final int yearOfExperience;
          private final double salary;
          
          Teacher(String name, int age, int yearOfExperience, double salary) {
              super(name, age);
      
              this.yearOfExperience = yearOfExperience;
              this.salary = salary;
          }
          
          // Sub-class define its method
          public boolean isQualified(){
              return this.yearOfExperience > 2;
          }
      }
      
      // Student class inherite from a Person class
       class Student extends Person {
          private final String department;
          private final String program;
          private final float gpa;
          
          Student(String name, int age, String department, String program, float gpa) {
              super(name, age);
      
              this.department = department;
              this.program = program;
              this.gpa = gpa;
          }
          
          // Sub-class define its method
          public boolean isPromoted(){
              return this.gpa > 2.0;
          }
      }  
      ```

3. **Polymorphism:**

   1. **Definition**: Polymorphism allows objects of different classes to be treated as objects of a common superclass. It also allows one method to be used in different ways depending on the object it is acting upon. This can be achieved through **method overriding** (runtime polymorphism) or **method overloading** (compile-time polymorphism).

   2. **Purpose**: This principle enables flexibility and the ability to define a common interface for different objects, allowing code to be more dynamic and scalable.

      **Runtime Polymorphism:** 

      ```java
      class Person {
          // instances variables
      
          // constrcutor
      
          // define a method which all the subclasses have to override
          public void info(){
              System.out.println("Person information");
          }
      }
      
      class Teacher extends Person {
          // instance variables
          
          // constructor
      
          // polymorphism
          @Override
          public void info(){
              System.out.println("Teacher information");
          }
      }
      
      class Student extends Person {
          // instance variables
          
          // constructor   
      
          @Override
          public void info(){
              System.out.println("Student information");
          }
      }    
      
      // lets create an object and see how runtime polymorphism(method overriding) works
      public class Main {
          public static void main(String[] args) {
          Person myPerson = new Teacher("Mr. Gibba", 30, 3, 17000);
          myPerson.info();// Teacher information
          }
      }
      ```


   **Compile time polymorphism:** the contract is that two or more methods can share the same name, the same return-type, and the same amount of parameters, but of different types.

   ```java
class Cal {
    double sum(int a, int b){
        return a + b;
    }

    double sum(double a, double b){
        return a + b;
    }

    double sum(int a, int b, int c ){
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        Cal cal = new Cal();
        cal.sum(2.0, 5.6);// compile time polymorphism
    }
}
   ```

   

4. **Abstraction:**

   1. **Definition**: Abstraction is the concept of hiding the complex implementation details and showing only the essential features of an object. It allows a programmer to focus on the interactions at a higher level, rather than on the internal workings.

   2. **Purpose**: This principle helps in reducing complexity and making the code easier to manage by providing a clear interface and separating *what an object does* from *how it does it*.

      ```java
      public abstract class Animal {
          public abstract void sound();
          public abstract void move();
      }
      
      class Dob extends Animal{
          @Override
          public void sound() {
              System.out.println("Dog bark!");
          }
      
          @Override
          public void move() {
              System.out.println("Dob move with her four legs");
          }
      }
      
      class Bird extends Animal {
          @Override
          public void sound() {
              System.out.println("Bird Preech");
          }
      
          @Override
          public void move() {
              System.out.println("Bird move by flying!");
          }
      }
      
      ```

      Next lesson, we will build upon this and build a banking application. So, for the meanwhile horn your skill by doing this challenge.

      ### Challenge

      In the world of computers we have difference types and shapes. A text-book definition of a computer is any electronic devices that take input, process and give a desired output. We have a lot of these devices today; the once in our pocket's, bags, offices and server houses. For this challenge I have selected a few which you have to worked on; desktop, laptop, tablet, and smart-phone. 

      * All the above mentioned devices are regarded as a computer so, therefore, create a class called `Computer`  with these properties(`brand`, `processor`, `RAM`, `storage`, `operatingSystem`, `batteryLife`, `price`), behaviors(`powerOn`, `powerOff`, `openApplication`, `checkBattery`, `sleep`) with a print system in each method print what the method those and a construct to initialize the instance variables. This will serve as the parent class. Your project name can be `challenge`.
      * As far as this challenge is concern you need to create sub-classes namely; `Desktop`, `Labtop`, ` Tablet`, and `SmartPhone`. Each sub-class will inherit from super-class(`Computer`).
      * At this stage you can see how **encapsulation** work, hence we have wrap all what is common to computing devices into a single unit(class) and provide method that operates on its data(attribute).
      * For each sub-class override all the method define by the parent class. For example the sleep behavior might not be the same for all of the computing devices, overrides the method for each sub-class by print how each sleeps.