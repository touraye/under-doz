# Object Oriented Programming

We have laned to one of the must hype paradigm in programming. So far we have learned procedural programming, functional approach and if you read [the order of method execute](https://ecodes.gm/java/2023/06/21/order-method-execution-in-java.html) you will have a clue about the different paradigm of software development. Well, this chapter will focus mainly on OOP(Object Oriented Programming). In OOP we relay heavily on method(behavior) which allows us manipulate the state(attribute, property or instant variable) of a class.

What to learn:

1. [TOC]

   

Prerequisites: fundamental of Java programming and methods.

## Object Oriented Programming

OOP is a programming paradigm where a software is replicable as a real-world-entity aka object. A real-world entity has a state(property) and a behavior(method). The property of a class will define as the physical characteristic of  an object while as the behavior define what the object can do. 

In this simple definition we understand that an object is a real-world entity, but what an object really is? An object in it's simple definition is an instance(copy) of a class. Well, this class is not actually your typical Java file, anyway, a Java file could be represented as a class. A class in a nutshell is blue-print where objects are created from.

As role of thump, a class is created first with a property(class variable, instance variable, or state) and a  behavior(method, member variable) before the creation of an object. Now let's put it into practice. Imagine we want to create a program that will store the information of a student and display the information.

Create a Java `class` Test and copy below code into it, above your `Test` class declaration. All the codes for our student will go into declaration of `class Student{...}`

```java

class Student {
     String firstName;
     String lastName; 
     double gpa;
}

public class Test {
    
}
```

*A `Student` class declaration and the a definition of three properties(attributes) that every other object which would be created from the `Student` class must have. This why a `class` is said to be blue-print where objects are created from* 

Remember we said a class has more than this; a class also define a `method` that allow us to modify the properties or attributes of a class. Let's return to our class and add method.

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

*The `void` methods defines their respective parameters(params). It seem familiar right? these methods are also called `setters`. A `setter` method is use to modify the state of a class. The `this` keyword points to the properties of a class. You would notice some suggestions of your properties after writing `this.`* 

This alone don't solve our problem. Right now we can set the values to the properties but we cannot access the values we set to our state variables.

Lets create methods that will return the properties(`firstName`, `lastName` and `gpa`). Remember a method that will return a value to the caller must define a return type in the parameter list:

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

Now our `Student` class is done, but we are yet to create one of the important thing and that is an objects. For our case an object is going to represent different students with their individuals first and last names and gpa's.

```java
public class Test {
    public static void main(String[] args) {
        Student student1 = new Student(); // student1 object
    }
}
```

*Student student1 = new Student() creates a new student object name `student1` .*

Let's use our newly created object `student1` to invoke the method we defined in our `Student` class, these method will allow us to set the `firstName`, `lastName` and `gpa` for a student:

```java
Student student1 = new Student();
student1.setFirstName("Ahmed");
student1.setLastName("Dicko");
student1.setGpa(4.0);
```

Let's proceed invoking our `getters`. Think about reading the properties of our student(`student1`). 

```java
// reading the properties of student1
System.out.println("Student 1 Information");
System.out.println("First Name: " +student1.getFirstName());
System.out.println("Last Name: " +student1.getLastName());
System.out.println("GPA : " +student1.getGpa());
```

*Your console will display the first and last and gpa for  `student1`*

### Challenge

Challenge yourself to create another student, name the object as `student2` and set it any desirable values, finally print the information to the console.

## Constructor

Once a class is instantiated(an object is created) Java creates a default  **constructor** for you, the `Student()`  is a constructor and it is called **no args constructor**. From the `Student` class we haven't defined a constructor ourself but Java did so, a no args constructor mean that no arguments will passed to it since no parameter(s) where defined.

A constructor a special method  so therefore when creating:

* It must live within the `class` where it is indented
*  It must have the same name as that of the `class`
* It must be a `public` method, it may have a `public` keyword as a convention
* It is a convention to define it immediately after your instance variables
* It may use to assigned values to the instance variables. 
* Within the parameters list placeholders are provided; they must be the same in chronologically order as that of the instance variable(s), they must have the same data type but their name(s) can be different.
* Within the body of the constructor values are assigned to the instance variables.
* The constructor do not have a return type, therefore, it doesn't returns any value.

#### Creating a Constructor for our Student class

A `getters` and a `setters` are not mandatory when creating a class, anyways, it those promote modularity and reusability. We would refactor our code, get ride of the `getters` and `setters` and make use of a **constructor** and a `toString()` method.

```java
public Student(String _firstName, String _lastName, double _gpa){
        this.firstName = _firstName;
        this.lastName = _lastName;
        this.gpa = _gpa;
    }
```

*The constructor define three parameters, their names are almost the same with that of our instance variables, but I added `_` at the beginning on purpose. Just to point `this.firstName = _firstName;` does not refers to the same variable. Inside the body of the constructor same as `setters` method, assigned the input variable's value to the instance variable's.*

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

*`toString()1`  is a self explanatory, all it those is returns a String representation of an object. Anyways, the `@override` keyword denote it is an override method; we will discuss more about that in the coming chapters.*

Still on refactoring, let's fix the compile-time error with the `main` method:

```java
Student student1 = new Student("Ahmed", "Dicko", 4.0);
```

*The `setFirstName`, `setLastName`, and `setGpa` arguments are passed directly in the constructor separate by comma. In just one line we passed the properties of `student1` object*

Invoking the `toString()`. 

```java
System.out.println(student1.toString());
//
Student{firstName='Ahmed', lastName='Dicko', gpa=4.0}
```

Creating another student will be lot easier. Go ahead and create two new students and print their information to the console using the `toString` method.

If you did so you will see the beauty of Object Oriented Programming, once you have created(design a blue-print) a class you are not limited to the number objects you will have to create. Each object will have a distinct properties.    

## Summary

In this lesson you have learn:

* What is Object Oriented Programming
* What is a Class and Object in Object Oriented Programming
* How to create a Class(Student)
* What is a property(state) and behavior of a Class(Student)
* How to create an instance variable(class variable, state) of a Class(Student)
* How to define behavior(method) of a Class(Student)
* What is a constructor and how to create one
* How to instantiate a Class either create an Object(student1)
* How to use an Object(student1) to invoke methods(getters, setters and `toString`) defined on a Student Class
* How pass value to setter methods(`setFristName`, `setLastName`, and `setGpa`)
* How to set value to the properties of a Class using above mentioned methods
* How to return the property values of a Class using methods(`getFirstName`, `getLastName`, `getGpa`)
* How to read the value of an Object using a getter methods
* How to use a constructor to assign value to the instance variables
* How to use a constructor to pass values `Student("Ahmed", "Dicko", 4.0);`
* How to create a `toString` method and return a String representation of an Object.