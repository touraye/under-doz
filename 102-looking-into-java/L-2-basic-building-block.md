# Basic Building Of Java Application

The basic building block of a Java program:

* Class 
* Statement
* Method
* Block
* Keywords

A **class** is the basic building block of every Java Application, and this **class** is just a mire file you will create in your project with an file extension of `.java`. Remember when we were creating our very first Java program from the command line. We created a file name `Main.java`, open it in notepad and created a **class** declaration.

If you are using a an IDE it is different case. The IDE does it for you, because you specific due time that you're create a Java **class**, and it prompt you to write the name(without the `.java` extension) of your class upon providing your class name you press on `Enter`. The IDE will create file with the name you have provided and provide a **class** declaration for you out from the box.

**What is a Class Declaration**

A class declaration comprises of the following:

* Access modifier public`
* Specifier `class` 
* Identifier the name of the class `Main`
* The body of the class `{body}`
* Block of code `{}` opening brace and a closing brace

The above listed is for every Java class you will be creating in the feature. You name your class base on the project as we discussed earlier. 

```java
//Example of a Java Class
public class Main {

}
```

## Main Method

The **main method** is a `static` method which serve as the entry point of our Java program or application. If you used an IDE to create a new Java class; you will notice that there are no *green play button* around and if you right-click for option you will not see Run. Meaning the IDE detect that your class doesn't have a main method therefore it would give you chance to run your codes. Therefore you can create variables and methods there no problem, but a print statement outside a method will show you error.

If you create class without a main method and try running it in terminal/git bash it throw error. We will talk more these kind class and their use cases later lessons.

Note! *a class exist in your program without a main method. more about in OOP section*

```java
public class Main {
    // main method
	public static void main(String[] args){
        
    }
}
```

Main method comprises of the following:

* Modifier `public` 
* Specifier `static`
* Specifier `void`
* Identifier name of the method `main`
* Parenthesis `()` with some argument `String[] args`
* Block of code `{}` opening brace and a closing brace

Note: *Any code within the opening brace and the closing brace of the main method is going to get executed when you run your program*

```java
public class Main {   
	public static void main(String[] args){
        
    }
    System.out.println("Hello World");
}
//This is going to throw some errors

public class Main {  
	public static void main(String[] args){
     	 System.out.println("Hello World");   
    }   
}
// Hello World
```

## Method

A method is piece of code that execute a specific task when called. A method is called with it's name.

There are many different types method in Java including a void method(a method that do not return a value), and method that returns a value. The method that returns a value most have type, and the type most confront the value it is returning.

```java
public class MyMehthod {
	public void greetings(){
		System.out.println("Hello from Java");
	}
    
    public int addTwoNumber(){
        int sum = 2 + 2;
		return sum;
	}
    
    public static void main(String[] args){
        greetings();
        // Hello from Java
        System.out.println(addTwoNumber());
        // 4
    }
}
```

Note! *a method can have a keyword static which is not a main method. we will look into that later*

## Keyword

These are language specific word or reserve words which cannot be use by programmers to name a classes, variables, or methods.

Some of the keywords in Java:

* class
* public
* private
* protected
* default
* main
* package
* static
* return
* do
* while

Just to name a few, you lookup on [w3school](https://www.w3schools.com/java/java_ref_keywords.asp)

[Next lesson](https://github.com/touraye/under-doz/blob/main/102-looking-into-java/L-103-data-types.md)

[Previous lesson](https://github.com/touraye/under-doz/blob/main/102-looking-into-java/L-101-java-at-first-look.md)
