# Exception

As we continue to build more robust programs, it becomes increasingly clear that user input can cause a program to misbehave. As [discussed earlier](https://github.com/touraye/under-doz/blob/main/content/Module-3-java-at-first-glace/b-data-types-java.md#data-types-in-java-1), Java is a statically typed language, meaning every variable must be bound to a specific data type. For example, if a program prompts the user to enter a string and they input `"44"`, it will be treated as a valid string. However, if the program expects a numeric value and the user enters `"s"`, the program will crash—this is known as an exception. The input `"s"` is not a valid numeric value, and therefore the program cannot process it correctly. In this module, we will learn what exceptions are, explore the different types of exceptions in Java, and understand how to handle them gracefully.

## **What is an exception:**  

An **exception** is a deviation from the normal [flow of control](https://github.com/touraye/under-doz/blob/main/content/Module-5-control-structures/README.md) in a program. While exceptions are often thought of as **errors**, they are not necessarily errors in every case. In Java, exceptions are represented as objects of the ***Exception*** class. Each specific type of exception is a subclass of ***Exception***, meaning that all exceptions in Java inherit from the ***Exception*** class. For now, it's important to understand that every exception is an object derived from the ***Exception*** type.

### **Types of Exceptions:**

Here are the most common exceptions we will cover in this course:

1. **`ArithmeticException`**: This exception occurs when an invalid arithmetic operation is performed. For example, dividing an integer by zero.
2. **`InputMismatchException`**: This occurs when the input provided does not match the expected type. For instance, entering a string when a number is expected.
3. **`NumberFormatException`**: This occurs when a value cannot be converted to a number. For example, entering the letter `"t"` instead of a number like `5` when a numeric input is expected.
4. **`IllegalStateException`** *(Assuming you meant this instead of "IllegalMisMatchedException")*: This occurs when a method is called at an inappropriate time or when an object is in an illegal state.
5. **`IndexOutOfBoundsException`**: This occurs when you try to access an array or list element at an index that doesn’t exist — for example, accessing the 5th element in a 3-element array.
6. **`IllegalArgumentException`**: This occurs when a method receives an argument that is inappropriate or outside the acceptable range.
7. `AthrimeticException`:

## **Handling Exception**

Exceptions are handled using two main statements: `try` and `catch`. The `try` block contains the code that might cause an exception, while the `catch` block handles the exception and displays an appropriate error message.

`try` and `catch` block:

```java
try {
    // code that might cause an exception
} catch (exception-class object) {
    // error message from the exception
}
```

Integer division by zero is not allowed in Java and will result in a program crash due to an `ArithmeticException`

```java
System.out.println(4 / 0);
```

In Java, dividing an integer by zero causes an `ArithmeticException`. To prevent your program from crashing, you can use a `try-catch` block to handle this exception gracefully.

```java
int a = 10;
int b = 0;

try {
    int result = a / b;
    System.out.println("Result: " + result);
} catch (ArithmeticException e) {
    System.out.println("Error: Cannot divide by zero.");
}

// Error: Cannot divide by zero.
```

Another example:

```java
Scanner in = new Scanner(System.in);
int totalGrades= 0;

while (true) {
    System.out.println("Enter grades or 'q' to quite");
    String input = in.next();

    if (input.equals("q")) break;

    int convertedInput = Integer.parseInt(input);
    totalGrades += convertedInput;
}

System.out.println("Total Grades: " +totalGrades);

in.close();
```

The code above functions correctly as long as the user inputs valid numeric values for grades and uses `"q"` to terminate the program. However, if the user enters any non-numeric character other than `"q"`, the program will crash due to a `NumberFormatException`. This occurs because the program attempts to convert an invalid string to an integer using `Integer.parseInt()`.

To handle this exception gracefully, we can wrap the code inside the `while` loop — along with the final output for total grades — inside a `try` block. We then use a `catch` block to handle the exception and print the associated error message using `ex.getMessage()`.

```java
Scanner in = new Scanner(System.in);
int totalGrades= 0;

try {
    while (true) {
        System.out.println("Enter grades or 'q' to quite");
        String input = in.next();

        if (input.equals("q")) break;

        int convertedInput = Integer.parseInt(input);
        totalGrades += convertedInput;
    }

    System.out.println("Total Grades: " + totalGrades);
} catch (NumberFormatException ex) {
    System.out.println(ex.getMessage());
}
in.close();
```

When a user inputs a value other than a valid number or `'q'`, the program crashes and terminates with an error like: `For input string: "u"`

This happens because the `try` block wraps the entire `while` loop. As a result, once an exception occurs, the loop is exited and the program terminates.

To improve the behavior, we can **refactor the program** so that the `try-catch` block is placed **inside** the loop. This way, if an exception occurs, the error is handled, and the loop continues running — allowing the user to try again without crashing the program.

```java
Scanner in = new Scanner(System.in);
int totalGrades= 0;

while (true) {
    try {
    System.out.println("Enter grades or 'q' to quite");
    String input = in.next();

    if (input.equals("q")) break;

    int convertedInput = Integer.parseInt(input);
    totalGrades += convertedInput;
        System.out.println("Total Grades: " + totalGrades);
    } catch (NumberFormatException ex) {
        // you can print a custom error as well
        System.out.println(ex.getMessage());
    }
}
in.close();
```

Upon entering an invalid input such as `"u"`, the program will gracefully handle the `NumberFormatException` by displaying an appropriate error message. Instead of crashing, the program will continue to run, allowing the user to input values again.

In the upcoming module, we will explore other common types of exceptions and learn how to handle multiple exceptions within a single program effectively.

### **Summary:**

* An **exception** is an abnormal event that disrupts the normal flow of a program.
* When an exception occurs, it can cause the program to **crash** if not properly handled.
* Java provides different **types of exceptions**, each representing a specific kind of error.
* All exception types are **derived from the `Exception` class**.
* To handle exceptions in Java, we use the **`try` and `catch` blocks**:
  - The `try` block contains the code that may throw an exception.
  - The `catch` block handles the specific type of exception and can display an appropriate error message using `ex.getMessage()`.