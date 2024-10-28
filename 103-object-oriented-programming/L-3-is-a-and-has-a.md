# Is-a And Has-a Relationship

In Object-Oriented Programming (OOP), **“is-a”** and **“has-a”** relationships are fundamental concepts that describe how objects relate to each other.

### **“Is-a” Relationship (Inheritance)**

- **Definition**: This relationship is established through inheritance. It indicates that one class (subclass) is a type of another class (superclass).

- **Example**: If you have a class `Animal`, a class `Dog` and a `Cat` that extends `Animal`, then `Dog` **is an** `Animal` and `Cat` **is a** `Animal`.

- Usage

  : This is used when you want to create a hierarchy of classes that share a common structure and behavior. For instance:

  ```java
  class Animal {
      void eat() {
          System.out.println("This animal eats food.");
      }
  }
  
  class Dog extends Animal {
      void bark() {
          System.out.println("The dog barks.");
      }
  }
  
  class Cat extends Animal {
      void meow() {
          System.out.println("The cat meows.");
      }
  }
  ```

### **“Has-a” Relationship (Composition)**

- **Definition**: This relationship is established through composition. It indicates that one class contains a reference to another class.

- **Example**: If you have a class `Car` and a class `Engine`, then `Car` **has an** `Engine`.

- Usage: This is used when you want to build complex types by combining objects. For instance:

  ```java
  class Course {
      private String name;
      private String description;
      private double score;
      private boolean isMounting;
      private final int maxNumber;    
  }
  
  class Student {
  	private String full_name;
      private String dob; //format 'dd-mm-yyy'
      private Course course;
      private ArrayList<Course> courses; // student has course that will store in a list hence student can take many course in any given semester
      
      Student(String full_name, String dob, Course course){
          this.full_name = full_name;
          this.dob = dob;
          this.course = course;
          this.courses.add(course);
      }
      
      void computeGPA(){
          // go through the course list of each student and compute their GPA
      }
  }
  
  class Engine {
      void start() {
          System.out.println("Engine starts.");
      }
  }
  
  class Car {
      private Engine engine;
  
      Car() {
          engine = new Engine();
      }
  
      void startCar() {
          engine.start();
          System.out.println("Car starts.");
      }
  }
  ```

In summary, use **inheritance** (“is-a”) when you need to create a clear hierarchical relationship, and use **composition** (“has-a”) when you want to build complex objects from simpler ones



​              