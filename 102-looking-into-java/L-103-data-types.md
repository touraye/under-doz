# Data Types In Java

In the earlier lessons we looked variables and their different data type a program can manipulate, and we said that; a number type, text type or yes and no text. We just brief data type a program interact with. Let's learn about data types in Java.

**What are Data Types in Java**

Data type in Java specify how value of a variable get stored in a computer memory. Each variable has a type that decides what type of value the variable can hold.

Well, in Java there are two data types or types and these are *Primitive Data Type* and *Non-Primitive Data Type*. *Non-Primitives* are also called *Referential*.

## Primitive Data Types

Primitive data type specify the size and type of a variable values. They are the building block of data manipulation and can be further divided into.

* Boolean: `boolean`
* Character: `char`
* Integer: `byte, short, int, long`
* Float: `float, double`

  Every *primitive data type* has *special keyword* which is unique to only one. in Java, primitive data type are predefined by the language you don't need to create them, and there called by a *reserve keyword*.

 Java offers eight *primitive data types*, they are categories by their name aka keyword.

The eight **Primitive Data Types**

**Byte:**

* Byte is of 8bit long

* Byte is the smallest among Integers

* ```java
  byte a = -128, b = 127;
  ```

* Minimum a byte can take is `-128`

* Maximum a byte can take is `127`

* Default value is `0 `

**Short:**

* Short is of 16bit long

* ```java
  short s1 = -32768, s2  = 32767;
  ```

* Minimum a byte can take is `-32768`

* Maximum a byte can take is `32767`

* Default value is `0 `

**Int:**

* Int is 32bit long

* ```java
  int min =  -2147483648, max = 2147483647;
  ```

* Minimum a byte can take is `-2147483648`

* Maximum a byte can take is `2147483647`

* Default value is `0 `

*  Int is generally used as the default data type for integral values unless  there is a concern about memory. 

**Long:**

* Long is of 64bit long

* ```java
  long min = -9223372036854775808L, max = 9223372036854775807L;
  ```

* Minimum a byte can take is `-9223372036854775808L`

* Maximum a byte can take is `9223372036854775807L`

* Long is use to store range of values which other Integer types cannot.

* Default value is `0 `

**Float Type:** floating-point data type are use to store values with decimals

**Float:**

* Float is 32bit long

* ```java
   float f1 = 234.5f;
  ```

*  Default value is 0.0f. 

* Float is not use to store currency.

**Double:**

* Double is 64bit long

* his data type is generally used as the default data type for decimal  values, generally the default choice.

* ```java
  double price = 100.25;
  ```

* Default `0.00`

**Boolean:**

* boolean data type represents one bit of information.

* There are only two possible values: `true` and `false`.

*  Default value is false

* ```java
  boolean isLiving = true;
  ```

**char:**

*  char data type is a single 16-bits Unicode character. 

*  Char data type is used to store any character.

* Char take only one value;

* Char value is within a single quotations `''`.

* Char is use to store people's gender.

* Default value is `null`

* ```
  char gender = 'm';
  ```

  

## Non-Primitive Data Type or Referential

Non-primitive data types or reference data types refer to instances or objects. They cannot store value of variable directly in memory. They store a memory address of the variable.

The non-primitive data type are not predefined rather they are created by the programmers. All Non-primitive data types are of the size.

Example of Non-primitive data type: 

* Array 
* Class
* Interface
* String
* Enum

### Array

Array hold multiples values of the same type. Other primitives data type like double cannot hold more than one value, but you create an Array of type int and store more than one values. Array are refers to as *objects* in Java.

* Array have a fixed size
* Items in an Array are called elements
* Each element has a index, index start from `0`.
* The first element is position at index `0`
* Array has methods on then that helps us to easily works or manipulate Arrays

```java
int[] number = new int[5];
//adding element to an Array
number[0] = 1;
number[1] = 2;
number[2] = 3;
number[3] = 4;
number[4] = 5;
//accessing element from an Array
System.out.println(number[0]) // 1
System.out.println(number[4]) // 5
//know size of number Array
System.out.println(number.length) // 5
```



### String

The String data type store series or sequence of characters. It is a non-primitive data type, String literals are enclosed in a double quotation `""`

* String have method on them which can help us to perform other String manipulations

```java
String string1 = new String("Yabou");// redundant
String string2 = "Yabou";
System.out.println(string2.length()); // 4
```

### Class

A class is user-defined data type from which objects are created from. It describe the set of properties or method that are common to all objects of the same type. Basically, a class is a blueprint where objects are created from.

* Objects are create when a class is invoke. 
* A class have properties and behaviors

```java
public class Rectablge{
	double length;
	double breath;
	
	public void getTheArea(){
		double area length * breath;
		System.out.println("The area of arectangle is " +area);
	}
}

public class Tester{
    public static void main(String[] args){
        Rectangle rectangle = new Rectangle();// object is when a class is invoke
        rectangle.length = 10;
        rectangle.breath = 5;
        rectangle.getTheArea(); // The area of arectangle is 50
    }
}
```

### Interface

An interface is declared as a class. Interface have methods that are abstract by  default, interface not have a body

```java
public interface greetings{
    void greet();
}

public class Hi implements greetings {
    public void greet(){
        Syste.out.println("Hello from interface!")
    }
}

public class Tester{
    public static void main(String[] args){
        Hi hi = new Hi();
        hi.greet(); // Hello from interface!
    }
}
```

## Enum

An enum, similar to a class has attribute and method. However, in contrast to a class. enum cannot be used to create objects and it cannot extend other classes. Anyway, an enum can implement interface. Enums are use to defined constant values

```java
enum {
	LOW(name: "lowest temp", value: "0 to 10"),
	MEDIUM(name: "meduim temp", value: "11 to 20"),
	HIGH(name: "highest temp", value: "21 to 50"),
}
```

## Literal in Java

Java literal is a source code representation of a fixed value. They are constant values that appear directly in the program. We can assign literal directly to a variable.

Literal in Java:

* Integer literal `int age = 10;`
* Character literal `char gender = 'm';`
* String literal `String name = "Mariama";`
* Boolean literal `boolean flag = true`medium

## What is a Variable

We have discus broadly about variable concept in the prevision lessons now lets see it in Java. A   variable in Java can be really different hence Java static type language.

Well, what do mean by that? In a static type language a variable most a data type. Java is a static type language which why before you can give a variable a name or a value you have specify the data type.

```java
String course = "Java programming";
```

Lets extract the components from the statement above:

* `String` is a data type 
* `course` is a name of a variable
* `=` is an assignment operator
* `"Java programming"` is a value
* `;`is a termination

There are two way creating a variable:

1. Initialize a variable: a variable will have an initial value
2. Declare a variable: not initial value is given

### Initializing a Variable

These is when decide to give a value to a variable right at creation time or in another word assign a value to a variable.

The first operator we are dealing with is the assignment operator `=`

```java
//to initialize a variable
int age = 20;
```

### Declaring a  Variable

In your program you can create a variable without an initial value

```java
//to declare a variable
int amount;
```

### Reassigning a Variable

In the above we have created a variable `amount` and give it no value. When creating the `amount` we don't have a value for it but we have specific a type for it. 

Now we want to give `amount` variable a value:

```java
amount = 200;
```

reassigning a variable is not limited to only declared variable, but even the ones with initial value:

```java
age = 21;
```

Java update the `age` variable with a new value.

If you print `age` to the console you should see 21 instead of 20

## Naming Convention

It is a good practice to give your variables, methods, and classes names which relate to what they do or the value they store in them. Java doesn't care about the way the you name your variables, methods, or classes.

Imagine in your program you are to store student gpa in a variable:

```java
double gpa = 4.0;
double studentGpa = 3.50;
```

 Why are joining two words together? Is gpa not enough?

Well, variable, methods, and class names should be descriptive. Joining words together to form a descriptive name is a good way of programming, and these way joining words to form a long name is called *camel casing*. Java support other casing like *snake casing* that will require using an underscore `student_gpa`. Anyways, *camel casing* is the convention in Java.

## Exercise 102

After completing the part i expect you to have a solid understanding of data type in Java, the two different data types in Java, how ways of creating a variable, reassigning a variable, and how to give variable good names. In that note I challenge you to develop a Java Application that looks below:

Your first name, last name, and the name of your course. Remember best naming convention in Java!

```java
Alieu
Saidy
I am learning Java
```

