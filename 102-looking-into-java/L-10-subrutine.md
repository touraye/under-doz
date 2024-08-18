# Subroutine

As we move further, we will dive deeper into various aspects of programming. We have worked within the `main` method throughout this course. Here we will shift our focus to exploring more about subroutines.

We are stepping into a new programming paradigm all along we have been writing all our programming within the `main` method which can be a nightmare for a larger program. Splitting the program into small chunks is taking a functional approach.

What you will learn:

* [TOC]

  

## Functional Programming

Functional programming is a programming paradigm that allows programmers to create software into reusable modules called methods or functions.

## Subroutines

A subroutine is a piece of code that executes a task(defined with body) whenever called, a subroutine can be reused in many places within your program, it can take a value(**input**) or return a value (**output**). A subroutine can be referred to as a **function** or a **method**, but these two are different based on the context and programming language used.

Before we code subroutines let's try to see the difference between the two in terms of association, calling, and context:

**Association:**

* **Function**: Standalone and not associated with any object or class.
* **Method**: Tied to an object or class.

**Calling:**

* **Function**: Called by their name directly, e.g., `add()`.
* **Method**: Called on an object or class, e.g., `object.method()`.

**Context:**

* **Function**: Can be used in procedural and functional programming.
* **Method**: Specific to object-oriented programming.

In Java, the rule of thumb is that a subroutine is referred to as a **method** this is because Java is an **object oriented programming** language by design. As seen in the association, a **method** is tied to a **class** or an **object**, so therefore, a subroutine is either tied to a **class** or an **object**.

A method in Java can be further divided into different segments:

* A **method signature** starts with the method modifiers, return type, name of the method, and the parameter list. `public static void greeting()`. The parenthesis `()` is a must, but what is optional is the parameters which we will look at later.
* The **body of a method** which starts with an opening `{` and a closing `}` block. Anything wrapped within the `{}` will execute when a method is invoked, this can be as simple as a single `print` statement to over 10 lines of code.

 Creating a method in Java is fairly simple, since our **methods** are only tied to **class** for the time being, so, therefore, our **methods**  are going to be `static`. A `static` means a method is associated with a class, not an object.

The return type of a method is also a very important thing to take note of. Throughout our learning Java we have seen a main method; `public static void main(String[] args){}`.  let's examine the signature of a main method.

* Modifier `public` indicates that the method is public, it can be accessible anywhere in the program.
* The modifier `static` indicates the method belongs to a `class`.
* Return type `void` indicates that the method isn't returning any value to the caller.
* Method name `main`, a method is called or invoked by its name with a parenthesis.
* Parameter list `(String[] args) ` which means the method will take an array of strings, `args` is the actual name of the parameter or input variable.

This applies to all other methods as far as Java is concerned. Methods also have other modifiers apart from `public` which are `private` and `protected` we will learn more about that in a later chapter. For now, we'll stick with the ' public` method.

Let's start creating our custom methods:

```java
public class Greetings {
    public static void greeting(){
        System.out.println("Hello World!");
    }

    public static void main(String[] args) {
        greeting();// Hello World!
    }
}
```

*Calling or invoking a `static` method just with its name. You can invoke a method multiple times, try invoking `greeting()` method multiple times and you will notice that each time 'Hello World will be printed to the console*

### Parameter And Argument

Let's make the `greeting()` method take an input. For a method to take an input, we must specify in the parameter list the data type of the variable and the name of the variable. The name of the variable is not to be persevered or maintained when calling or invoking the method meaning, when calling or invoking a method a different variable name could be passed to it as an argument.

```java
public class Greetings {
    public static void greeting(String name){
        // always print the parameter when working with methods, remember increamental development.
        System.out.println("Hello World!, " +name);
    }

    public static void main(String[] args) {
        String myName = "Ahdem Dicko";
        greeting(myName);// Hello World!, Adhem Dicko
    }
}
```

*Our greeting() now takes an argument by the name myName which has the value of "Ahmed Dicko". As have seen the type of the parameter is the same despite the name being different* 

What is a parameter and an argument; well, it might seem confusing for many, but don't let it be! They both refer to the same thing like the association of a method to a class or an object. A parameter is defined at method creation time, it serves as a placeholder of what the method will expect when called while an argument is passed in as an input to a method when is it called or invoked.

When you define a method, you can specify parameters that the method expects to receive when it is called or invoked. These parameters act as placeholders for the actual values (arguments) that will be passed during the method invocation.

When a method defines a parameter, therefore, the caller should provide that method an argument. The argument must be of the same type as the parameter, but the names can be different.

Let's try to understand the concept of placeholder more. Imagine having a method that will print a person's info.

```java
public static void myInfo(){
        System.out.println("My name is Ahmed Dick");
        System.out.println("I'm here to learn programming");
        System.out.println("I want to be a Software Engineer");
    }
```

*myInfo() method prints information about a person, but the bad thing is that it can only be one person's information unless you change it.*

Let's make it possible myInfo() to be more dynamic by allowing myInfo() to take an argument whenever called. Before a method can accept an argument you need to define parameters in its parameter list. What do you need to do? The approach is quite easy:

1. You need to identify the values(the text with print the statements) that you would like to be placed by another person's information.
2. Provide placeholders for those values(remove those values and plug them in with variable names).
3. Define variables for those values in the parameter list, and be aware of their types. 

Let get to it:

```java
public static void myInfo(String name, String course, String career){
        System.out.println("My name is " +name);
        System.out.println("I'm here to learn "+course);
        System.out.println("I want to be a "+career);
    }
 
public static void main(String[] args){
    myInfo("Ahmed Dick", "programming", "Software Engineer");
    
    myInfo("Lamin Bah", "banking and finance", "Accountant");
}
```

*muInfo() is now dynamic, it can be called and passed in different information about different persons*

### Some More Examples

When a method defines more than one parameter in its parameter list we separate them with a comma as seen above. Below `add()` method defines more than one parameter as well, `val1` is separated from `val2` by a comma; like so when we called and passed two arguments :

```java
public class Calculator {
    public static int addition(int val1, int val2){
        int answer = val1 + val2;
        return answer;
    }

    public static void main(String[] args) {
        int sum = addition(2, 5);
        System.out.println(sum);// 7
    }
}
```

*The `addition()` method unlike the previous examples no longer has `void` as a return type instead of `int`. It defines two parameters both of type `int` namely `val1` and `val2`, adds them together stores the result in a variable called answer, and then returns sum.* 

A `return` statement is always the last statement within the body of a method whatever goes below it is unreachable code. A method can return a single or multiple values, but a method must return only one variable. The return type must be the same as the type which is specified in the method signature(return type). A method might take Boolean as an input and return String, so therefore, the return type is not dictated by the input type.

And what do I mean by `input` and `output`, literally, what the method takes in(argument) is referred to as an input and what will be returned whenever the method is done execution is referred to as an output.

Inside of the `main` method the `addition()` is called and 2 and 5 are passed to it instead of passing the name of the variable. 

### Difference Way To Pass Argument To A Method

In programming there are two ways we can pass an argument to a function or to a method; **pass by reference** or **pass by value**. 

**Pass by value:** A copy of the actual value is passed to the function or method, therefore, any changes or modifications made to it will not affect the original value:

```java
public class PassByValue {
    static void modifyMe(int num){
        num = 4;// assigned 4 to num
        System.out.println("the value get modified: " +num);
    }

    public static void main(String[] args){
        int num = 2;
        // before modifying num: 2
        System.out.println("before modifying num: " +num);
        modifyMe(num);
        // after modifying num remains: 2
        System.out.println("after modifying num remains: " +num);
    }
}
```

*The value of `num` remains unchanged despite `modifyMe()` method has assigned 4 to the input variable (parameter).*

**Pass By References:** For referential or non-primitive data types whenever they are passed to a function or method and get modified by the function or the method because their actual value got affected which leaves them outside of the function or method. This is because their reference is passed instead of their copy as that of the primitive data types.

```java
class Person { // Person class
    String name; // initialized name

    Person(String name){ // constructor
        this.name = name; // assigned input variable 'name' to name
    }
}

public class PassByReference {
    public static void main(String[] args) {
        Person person = new Person("Ahmed"); // Person object
        System.out.println("Before modifying: " +person.name); // Ahmed
        modifyMe(person);
        System.out.println("After modifying: " +person.name); // Ahmed Dicko
    }

    public static void modifyMe(Person person){
        person.name = "Ahmed Dicko";// Person name updated
    }
}
```

 *The value of `name` for the `Person` object got modified which affected the original value because the reference of it was passed. If the code(OOP) is not familiar to you do not worry yourself much next chapter will explain in much more detail.* 

#### Method As An Input And Nesting Method

Method 'a' can take method 'b' as an argument if the return type of method 'b' confronts the type defined by method 'a'. Let's code that up:

```java
public class MethodAsInput {
    public static void a(int age){
        System.out.println("You are " +age+ " year old.");
    }

    public static int b(int yearOfBirth){
        int currentYear = 2024;
        return currentYear - yearOfBirth; // compute person's age and return the value
    }

    public static void main(String[] args) {
        int myBirthYear = 2006;
        // a(b(myBirthYear)) // simplified
        int myage = b(myBirthYear);        
        a(myAge);// You are 18 year old.
    }
}

```

*A method 'a' takes method 'b' as an argument by using its returned value.*

Let's refactor our code to allow method 'a' to consume method 'b' directly, this is called the **nesting method**.

```java
public class MethodAsInput {
    public static void a(int yearOfBirth){
        System.out.println("You are " +b(yearOfBirth)+ " year old.");
    }

    public static int b(int yearOfBirth){
        int currentYear = 2024;
        return currentYear - yearOfBirth; // compute person's age and return the value
    }

    public static void main(String[] args) {
        int myBirthYear = 2006;
        a(myBirthYear);
    }
}

```

*More about nesting read my blog [the order of method execution](https://ecodes.gm/java/2023/06/21/order-method-execution-in-java.html).*

## Refactoring

Let's return to our Cash Power Application where we will introduce some methods, but we will discuss why considering methods. There are use cases where methods become handy and can lead to good code practices.

The benefits of using this method:

* The method allows a program to be split into small manageable chunks.
* Each method can be responsible for carrying out its own individual task.
* Once a method is created it can be used in multiple places reducing redundancy.
* Maintainability becomes easy with method and collaboration among team members.
* It promotes the separation of concern and code readability.
* It encourages abstraction and encapsulation.
* Test and debugging become easy.

The **dry principle in software development** means "*do not repeat yourself".* This principle might work in all scenarios including our case despite the size of our program. We can think of **abstraction and encapsulation** whereby we can hide certain implement and bucket-related logics together.

#### Challenge Yourself

Starter code:

```java
import java.text.DecimalFormat;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.util.Random;
import java.util.Scanner;

public class CashPowerApp {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        LocalDateTime currentDate = LocalDateTime.now();
        DateTimeFormatter dateFormatPattern = DateTimeFormatter.ofPattern("MM-dd-yyyy HH:mm:ss");
        DecimalFormat decimalFormat = new DecimalFormat("0.00");
        Random random = new Random();

        int random4Digits1 = random.nextInt(9000) + 1000;
        int random4Digits2 = random.nextInt(9000) + 1000;
        int random4Digits3 = random.nextInt(9000) + 1000;
        int random4Digits4 = random.nextInt(9000) + 1000;
        int random4Digits5 = random.nextInt(9000) + 1000;

        String tokens = random4Digits1+ " " +random4Digits2+ " " +random4Digits3+ " " +random4Digits4+ " " +random4Digits5;

        String formattedDate = currentDate.format(dateFormatPattern);
        String recieptNumber = "202303EIN005386482";
        String meterNumber = "0948842284921";
        String customer = "Lamin Njie";
        String tellerID = "0123";
        final double KWH = 0.1;
        double serviceFee = 1;
        double powerAmount;
        double totalUnits;

        double dailySale = 0;// track daily sales
        boolean flag = true;

        while (flag) {

            System.out.print("Enter Amount: ");
            double amount = input.nextDouble();

            //check for the amount
            if (amount >= 30) {
                powerAmount = amount - serviceFee;
                totalUnits = powerAmount * KWH;

                System.out.println("************** NAWEC **************");
                System.out.println(formattedDate);
                System.out.println("Receipt Number: " + recieptNumber);
                System.out.println("Meter Number: " + meterNumber);
                System.out.println("Customer Name: " + customer.toUpperCase());
                System.out.println("Paid Amount: GMD" + String.format("%,.2f", amount));
                System.out.println("Power Amount: GMD" + String.format("%,.2f", powerAmount));
                System.out.println("Service Fee: GMD" + serviceFee);
                System.out.println("Total Units: " + decimalFormat.format(totalUnits) + "KWH");
                System.out.println("----------------------------------");
                System.out.println("\t\tToken Number \n \t" + tokens);
                System.out.println("---------------------------------");
                System.out.println("Teller ID: " + tellerID);
                System.out.println("Teller: LAMIN DIBBA");
            } else {
                System.out.println("The minimum amount to purchase cash power is GMD30.00");
            }

            dailySale += amount;// updating the dailySale with every amount entered by the user
            System.out.println();
            System.out.println("It is end of the Day? \nType 'y' for Yes to terminate the App\nType 'n' for No to continue Selling cash power");
            String endOfTheDay = input.next();

            if(endOfTheDay.equals("y")){
                System.out.println("Total daily sales GMD" +String.format("%,.2f", dailySale));
                System.out.println("Transaction Date: " +formattedDate);
                System.out.println("Thanks You");
                flag = false;
            }
        }
    }
}
```

For our case, I would like to keep the `main` method clean. Let it handle only prompting and taking user input, validating user input. So, therefore, all the other business logic will be lifted from the `main` method to their respective methods.

1. Extract token generation into its own method:

   ```java
   public static String tokenGenerator(){
           Random random = new Random();
   
           int random4Digits1 = random.nextInt(9000) + 1000;
           int random4Digits2 = random.nextInt(9000) + 1000;
           int random4Digits3 = random.nextInt(9000) + 1000;
           int random4Digits4 = random.nextInt(9000) + 1000;
           int random4Digits5 = random.nextInt(9000) + 1000;
   
           return random4Digits1+ " " +random4Digits2+ " " +random4Digits3+ " " +random4Digits4+ " " +random4Digits5;
       }
   // invoking the method
   System.out.println("\t\tToken Number \n \t" + tokenGenerator());
   ```

2. I went further to extract `unitFormatter` to which return a string representation of a currency:

   ```java
   public static String unitFormatter(double unit){
           DecimalFormat decimalFormat = new DecimalFormat("0.00");
           return decimalFormat.format(unit);
       }
   
   // invoking the method
   System.out.println("Total Units: " + unitFormatter(calculatePowerUnit(amount, KWH, serviceFee)) + "KWH");
   ```

3. Challenge yourself by extracting `calculatePowerUnit`. All this does is calculate the power unit and return its value:

4. Challenge yourself by extracting `dateFormatter`. Remove all the associated date formats into this method and return a String representation of data.

5. Challenge yourself by extracting `currencyFormatter` into its respective methods. This method takes the amount, formats it, and returns a String representation of the amount.

[Next lesson](https://github.com/touraye/under-doz/blob/main/103-object-oriented-programming/L-1-object-oriented-programming.md)
[Previous lesson](https://github.com/touraye/under-doz/blob/main/102-looking-into-java/L-9-iterations.md)
