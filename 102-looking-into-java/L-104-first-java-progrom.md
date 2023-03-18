# Your First Java App

We will begin developing Java App as we discussed about class, and a method, and data types. With the knowledge class, and main method, primitives and non-primitive we are good go.

## **What makes up a Java Application**

Every Java Application comprises of the following:

* Class
* Main method(not for every class)
* Statement
* Expression

Let look that into code:

```java
public class MyFirstJavaApp {
    public static void main(String[] args) {     
        System.out.println("World Hello!");
    }
}
// Hello World!
```

Congrats for developing your first Java App! let's look into our Java App in detail

* Line number 1 is a declaration of class
* Line number 2 is our main method
* Line number 3 is a print statement with a text.

A print statement is going one of our most use statement as far our studies for Java is concern. Every time you want to print to the console you have to use to the print statement. 

Uses of print statement:

1. You can use a print statement to print series of characters like the above example.

2. You can write some put a variable name in the print name and it's value will printed to the console

3. You put a String and variable in one print statement.

4. You can write a expression in print statement

5. You can as well put an expression with a String in a print statement.

Let see that in code the above list:

```java
public class Number1 {
    public static void main(String[] args) {           
        System.out.println("Java is awesome!");
    }
}
// Java is awesome!

public class Number2 {
    public static void main(String[] args) {   
        String myName = "Yabou";
        System.out.println(myName);
    }
}
// Yabou

public class Number3 {
    public static void main(String[] args) {   
        String myName = "Yabou";
        System.out.println("My Name is: " +myName);
    }
}
// My Name is: Yabou

public class Number4 {
    public static void main(String[] args) {         
        System.out.println(2 + 2);
    }
}
// 4

public class Number5 {
    public static void main(String[] args) {         
        System.out.println("2 + 2 = " +(2 + 2));
    }
}
// 2 + 2 = 4
```

We have seen how useful a print statement can be for console applicate. A console application it that application which display it's output in a console.

We also introduce some new things like *expression, and statement*. Let's look into them.

## Statement

In programming we write construction to computer to carry out a task or a computation. These instructions which a programmer writes are called statement, it can as simple as printing a text to the console or adding two whole number and printing the result as we seen above.

In Java every statement should be terminated with a semicolon `;` 

In Java we have five different statements:

* Expression statement
* Declaration statement
* Selection statement
* Iteration statement
* Jump or Flow control statement

We look into all the mentioned above statements later in the course.

## Expression

A expression can be as simple as adding two number, assigning a variable to a value.

In Java program expressions plays a very important role. We use expression to generate new values, assign value to a variable. An expression comprises `values`, `variables`, `operators`, or simple `methods calls`

### Expression Statement

In the code snippets below are some examples of expression statement.

```java

```

