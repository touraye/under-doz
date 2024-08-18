# Object Oriented Programming

In this lesson, we'll explore one of the most popular paradigms in programming: Object-Oriented Programming (OOP). Up until now, we've covered procedural and functional programming approaches. If you've read [the order of method execution](https://ecodes.gm/java/2023/06/21/order-method-execution-in-java.html), you're already familiar with various software development paradigms. Our focus now shifts to OOP, where the emphasis is on methods (behaviors) that allow us to manipulate the state (attributes, properties, or instance variables) of a class.

What to learn:

1. [TOC]

   

Prerequisites: fundamental of Java programming and subroutine.

## Object Oriented Programming

Object-Oriented Programming (OOP) is a programming paradigm where software is modeled after **real-world entities**, known as **classes**. A **real-world entity** has a state (attributes or properties) and behavior (methods). The properties of a class represent the physical characteristics of an object, while the behavior defines what the object can do.

In this basic definition, we understand that a class represents a **real-world entity**. But what exactly is an **object**? Simply put, an **object** is an instance (or a copy) of a class. It's important to note that a class isn't just a typical Java file, though a Java file can represent a class. In essence, a class is a blueprint from which objects are created.

As a rule of thumb, a class is created first, defining its properties (class variables, instance variables, or state) and behaviors (methods or member functions) before creating an object. Now, let's put this into practice. Imagine we want to create a program that stores and displays a student's information.

Create a Java class named `Tester`, and copy the code below into it. Place the following code above your `Tester` class declaration. All the code related to our student will go inside the `Student` class declaration, like this: `class Student { ... }`.

```java

class Student {
     String firstName;
     String lastName; 
     double gpa;
}

public class Tester {
    
}
```

*The `Student` class is declared with three properties (attributes or state) that every object created from the `Student` class must have. This is why a class is referred to as a blueprint from which objects are created. The `public class Tester` is your standard Java class and will include a `main` method.* 

Remember, a class is more than just a collection of properties; it also defines methods that allow us to modify its attributes. Let's go back to our `Student` class and add some methods.

```java
class Student {
    /**
    
    **/
     
     public void setFirstName(String firstName){
        this.firstName = firstName;
    }
    
    public void setLastName(String lastName){
        this.lastName = lastName;
    }
    
    public void setGpa(double gpa){
        this.gpa = gpa;
    }
}
```

*The `void` methods define their respective parameters, which may seem familiar—they're also known as `setters`. A `setter` method is used to modify the properties of a class. The `this` keyword refers to the current object's properties. When you type `this.`, you'll notice that your class's properties are suggested by your code editor.* 

This alone doesn't fully solve our problem. While we can now set values for the properties, we still can't access those values.

Let's create methods that will return the properties (`firstName`, `lastName`, and `gpa`). Remember, a method that returns a value to the caller must specify a return type in its method signature:

Add each `getter` after each respective `setter`:

```java
// setFirstName

public String getFirstName(){
        return this.firstName;
    }

// setLastName

public String getLastName(){
        return this.lastName;
    }

//setGpa

public double getGpa(){
        return this.gpa;
    }
```

Now that our `Student` class is complete, we still need to create objects. In this case, each object will represent a different student with their individual first name, last name, and gpa.

```java
public class Test {
    public static void main(String[] args) {
        Student student1 = new Student(); // student1 object
    }
}
```

*Student student1 = new Student() creates a new student object name `student1` .*

Let's use our newly created object, `student1`, to invoke the methods defined in our `Student` class. These methods will allow us to set the `firstName`, `lastName`, and `gpa` for the student:

```java
Student student1 = new Student();
student1.setFirstName("Ahmed");
student1.setLastName("Dicko");
student1.setGpa(4.0);
```

Next, let's invoke our `getters`. Consider how we can read the properties of our student object (`student1`).

```java
// reading the properties of student1
System.out.println("Student 1 Information");
System.out.println("First Name: " +student1.getFirstName());
System.out.println("Last Name: " +student1.getLastName());
System.out.println("GPA : " +student1.getGpa());
```

*Your console will display the first and last and gpa for  `student1`*

### Challenge

Challenge yourself to create another student object named `student2`, assign it any desired values, and then print the information to the console.

## Constructor

Once a class is instantiated (an object is created), Java automatically provides a default **constructor** for you. The `Student()` constructor is known as a **no-args constructor**. In the `Student` class, we haven’t defined a constructor ourselves, but Java provides this default one. A no-args constructor means that it takes no arguments since no parameters are defined.

A constructor is a special method, so when creating one:

* It must be defined within the `class` where it is intended.
* It must have the same name as the `class`.
* It must be a `public` method; although it's often declared `public` by convention, this ensures it can be accessed from outside the class.
* It is conventional to define the constructor immediately after the instance variables.
* It can be used to assign initial values to the instance variables.
* The parameters in the constructor must match the instance variables in both order and data type, though their names can differ.
* Within the body of the constructor, values are assigned to the instance variables.
* The constructor does not have a return type, so it does not return any value.

#### Creating a Constructor for our Student class

Getters and setters are not mandatory when creating a class, but they promote modularity and reusability. We will refactor our code to remove the getters and setters and instead use a **constructor** and a `toString()` method.

```java
public Student(String _firstName, String _lastName, double _gpa){
        this.firstName = _firstName;
        this.lastName = _lastName;
        this.gpa = _gpa;
    }
```

*The constructor defines three parameters, which are named similarly to the instance variables. However, I've added an underscore (`_`) at the beginning of the parameter names to clearly differentiate them from the instance variables. For example, `this.firstName = _firstName;` ensures that `_firstName` refers to the parameter rather than the instance variable. Inside the constructor, just like in the setter methods, assign the values of these parameters to the instance variables.*

The `toString()` method:

```java
 @Override
    public String toString() {
        return "Student{" +
                "firstName='" + firstName + '\'' +
                ", lastName='" + lastName + '\'' +
                ", gpa=" + gpa +
                '}';
    }
```

*`toString()` is a method that returns a string representation of an object. The `@Override` annotation indicates that this method overrides a method from a superclass. We'll discuss the `@Override` annotation and method overriding in more detail in the upcoming chapters.*

Continuing with the refactoring, let's address the compile-time error in the main method:

```java
Student student1 = new Student("Ahmed", "Dicko", 4.0);
```

*The `setFirstName`, `setLastName`, and `setGpa` arguments are passed directly to the constructor, separated by commas. In just one line, we initialize the properties of the `student1` object.*

Invoking the `toString()`. 

```java
System.out.println(student1.toString());
//
Student{firstName='Ahmed', lastName='Dicko', gpa=4.0}
```

Creating another student will be much simpler. Go ahead and create two new students, then print their information to the console using the `toString` method.

If you do this, you'll appreciate the beauty of Object-Oriented Programming. Once you have created (or designed) a class, you are not limited in the number of objects you can create. Each object can have distinct properties.  

## Summary

In this lesson you have learn:

- What is Object-Oriented Programming (OOP)?
- What are a Class and an Object in OOP?
- How to create a Class (e.g., `Student`)
- What are the properties (state) and behaviors (methods) of a Class?
- How to create instance variables (class variables, state) in a Class
- How to define methods (behaviors) in a Class
- What is a constructor and how to create one
- How to instantiate a Class (e.g., create an Object like `student1`)
- How to use an Object (e.g., `student1`) to invoke methods (getters, setters, and `toString`) defined in the Class
- How to pass values to setter methods (e.g., `setFirstName`, `setLastName`, and `setGpa`)
- How to set values to the properties of a Class using setter methods
- How to return property values of a Class using getter methods (e.g., `getFirstName`, `getLastName`, `getGpa`)
- How to read the values of an Object using getter methods
- How to use a constructor to assign values to instance variables
- How to use a constructor to pass values (e.g., `Student("Ahmed", "Dicko", 4.0)`)
- How to create a `toString` method and return a string representation of an Object

[Next lesson]()

[Previous lesson](https://github.com/touraye/under-doz/blob/main/102-looking-into-java/L-10-subrutine.md)
