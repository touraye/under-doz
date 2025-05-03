# Iterative Statements

In the previous module, we explored [conditional statements]() and how they are used to construct control structures within a program. Conditional statements serve as the foundation for iterative statements, which repeatedly execute a block of code based on a specific condition.

**Topics to covered:**

1. [While loop]()
2. [Do while loop]()
3. [For loop]()

Before we delve into the three iterative statements mentioned above, let's first understand the mechanism behind them. As previously stated, conditional statements form the foundation of iterative statements. Let's take a closer look:

* **Condition**: Every iterative statement includes a condition enclosed in parentheses `()`. This condition determines whether the loop continues and can vary depending on the type of statement used.
* **Block**: A block `{}` contains one or more statements that will execute repeatedly as long as the condition remains true.

**Syntax of an iterative statement:**

```java
(condition) {
	// block of code (s)
}
```

Now that we have a basic understanding of how an iterative statement works, let's explore them in detail—starting with the `while` statement, also known as the `while loop`.

**Quick note:** Copy and paste the following expressions into your IDE and observe the results for yourself: `1++`, `++1`, `1--`, `--1`.

Earlier, we learned that **operators** act upon **operands**—for example, in the expression `1 + 1`, the `+` operator acts on two operands. However, in the expressions above, you’ll notice two operators tightly paired with a single operand. This introduces us to **unary operators**, which operate on only one operand. We’ve previously discussed [unary operators]() in this context.

**Unary operators** also serve as shorthand for [arithmetic operations](). For example:

```java
int total = 0;
total = total + 2000; // 200
total = total - 500; // 1500
total = total * 2; // 3000
total = total / 2; // 1500

// short hand
int total = 0;
total += 2000; // 2000
total -= 500; // 1500
total *= 2000; // 3000
total /= 2000; // 1500

// pos, pre increment (++) and decrement (--)
int year1 = 1;
System.out.println(year1++); // 1
System.out.println(++year1); // 3
System.out.println(year1--); // 3
System.out.println(--year1); // 1
// I will explain why `--year` = 0 instead 1
```

### **How it works:**

1. **Post-increment** and **post-decrement** use the current value of the variable *before* updating it.
2. **Pre-increment** and **pre-decrement**, on the other hand, update the variable's value *first* before using it in an expression.

## :one: While Statement 

The `while` statement is a classic example of a loop. It consists of two main parts: a **test condition**—which is a Boolean value or expression enclosed in parentheses `()`—and a **body**, represented by a block `{}` containing one or more statements or expressions.

The test condition serves as the **control mechanism** of the loop. As long as this condition evaluates to `true`, the body of the loop will continue to execute repeatedly. Conversely, if the condition is `false` at the very beginning, the body `{}` will not execute at all. In other words, the `while` loop only runs when its condition is true, and it stops as soon as the condition becomes false.

### **How it works:**

1. The **condition** `()` controls the entire loop. It is evaluated *before* the body executes, and the process continues in a cycle as long as the condition remains `true`.
2. The **body** `{}` executes *immediately* after the condition evaluates to `true`.

**Syntax:**

```java
while (true) {
    //guess how many times this will be printed
    System.out.println("Hello World!");
}
```

The `while` loop above is **syntactically** correct, but **logically** flawed because it will run indefinitely—also known as an *infinite loop*—as long as the computer has sufficient memory. Although a `while` loop appears to be simple, it can be quite tricky to manage effectively.

To prevent unintended infinite execution, **controlling the `while` statement is essential**. Let’s modify the program so it prints only once. To achieve this, we’ll introduce a **control variable** or a **sentinel value** to manage the loop's execution.

```java
int counter = 0; // control variable
while (counter < 1) {
    System.out.println("Hello World!");
    counter = counter + 1; // increment counter by 1
} // end of the loop
// Hello World!
```

Breakdown of the above code assignment, Boolean expression, and reassignment:

- The program starts with an assignment: `int counter = 0;`.
- The condition (Boolean expression) is tested: `while (counter < 1)`, which evaluates to `true`.
- Since the condition is `true`, the body of the loop will execute.
- During the execution of the body, two things will happen:
  - `"Hello World!"` will be printed.
  - The `counter` will be reassigned and incremented by 1.
- After the loop has run once, it will attempt to execute again, but only if the condition is `true`.
- In the second execution of the loop, the condition `counter < 1` is `false` because `counter` is now 1. Therefore, the body will not execute.
- As a result, the program will terminate.

**Note:** The control variable can either be incremented (`counter = counter + 1`, `counter += 1`, or `counter++`) or decremented (`counter = counter - 1`, `counter -= 1`, or `counter--`), depending on your implementation.

Some more examples:

```java
// couting from 1 - 5
int counter = 1; // control variable
while (counter < 6) {
    System.out.println(counter);
    counter += 1; // increment counter by 1
} // end of the loop
// 1 2 3 4 5

// reverce order
// couting from 5 - 1
int counter = 5; // control variable
while (counter >= 1) {
    System.out.println(counter);
    counter--; // decrement counter by 1
} // end of the loop
// 5 4 3 2 1
```

## :two: Do While Loop

The `do`-`while` loop is the exact opposite of a `while` loop. It first executes the body `{}` before checking the condition. Afterward, the condition is checked, which will affect the second execution of the body `{}`. If the condition is `true`, the body `{}` will execute again, and the cycle will repeat as long as the condition remains `true`.

**How is works:**

* A block (body `{}`) of code is to be executed.
* A condition is then tested within the `while ()` loop.
* The condition only affects the second execution of the body.

**Syntax:**

```java
do {
    System.out.println("Greeting from Java");
} while (false);
// Greeting from Java
```

Be sure that the body of a `do-while` loop will always execute at least once, regardless of the condition.

Now, let's continue with the counter program. This time, we are going to count from `0` to `5`:

```java
int counter = 0; // control variable or sentinel value
do {
    System.out.println(counter); // print counter 
    counter++; // increment couter - short-hand
} while (counter < 5); // condition
// 0 1 2 3 4 

int counter = 5; // control variable or sentinel value
do {
    System.out.println(counter); // print counter 
    counter--; // decrement couter - short-hand
} while (counter > 0); // condition
// 5 4 3 2 1 
```

**Note:** Both the `while` and `do-while` loops have three key components: an assignment (control variable or sentinel value), reassignment (increment or decrement), and a Boolean expression (condition). These three elements are decoupled but together form the underlying control of a `while` loop.

## :four: For Loop

A `for` loop might appear a bit different from a `while` and a `do` loop syntactically, but the underlying mechanisms are the same. A `for` loop also has an assignment (control variable or sentinel value), reassignment (increment or decrement), and a Boolean expression (condition), though they are placed differently. A `for` statement also has parentheses `()` and a body `{}`. The parentheses `()` require two mandatory components: the sentinel value and the condition, while the increment or decrement can be placed either in the parentheses or in the body.

**How it works:** 

* The parentheses `()`:
  
  * **Assignment:** The control variable or sentinel value serves as the starting point for the loop.
  * **Boolean Expression:** The condition acts as the control mechanism for the loop, i.e., it dictates whether the loop will execute or not.
  * **Reassignment:** Optional; the increment or decrement updates the sentinel value each time the loop runs. Incrementing can involve adding 1, 2, 3, etc., or subtracting.
  
* The body `{}`:

  - The instructions that will be executed.
  - Optional increment or decrement.

  

  **Syntax:**

  ```java
  //example one
  for (counter, condition) {
  	// instruction
  	increment or decrement
  }
  
  //example two
  for (counter, condition, increment) {
  	// instruction
  }
  
  // incrementing
  for (int i = 0; i < 3;) {
      System.out.println(i);
      i++; // increment
  }
  // 0 1 2
  
  // derementing
  for (int i = 3; i > 0;) {
      System.out.println(i);
      i--; // decrement
  }
  // 3 2 1
  ```
  
  The syntax above will change later as we examine the structure of the `for` loop, but I just want to highlight the flow of execution, step by step:
  
  1. **The counter variable is initialized:**
     1. For incrementing: `int i = 0;`
     2. For decrementing: `int i = 3;`
  2. **The condition is checked:**
     1. For incrementing: `i < 3`; `true`
     2. For decrementing: `i > 0`; `true`
  3. **The body:**
     1. The `print` statement outputs the value of `i`, which is `0` for incrementing and `3` for decrementing.
     2. Finally, the control variable is updated for both incrementing (`i++`) and decrementing (`i--`).
  
  Now you have an understanding of how the flow of execution works. I did this to highlight that the last expression to execute in a `for` loop is actually always the reassignment of the sentinel value (`i++`) or (`i--`).
  
  Let’s restructure it for clarity:
  
  ```java
  for (int i = 10; i > 0; i--) {
      System.out.println(i);
  }
  
  // 10 9 8 7 6 5 4 3 2 1
  ```
  
  **Printing Odd and Even numbers**
  
  **Odd** numbers are numbers that are not divisible by 2, while **Even** numbers are numbers that are divisible by 2. To solve this, we can leverage `if` and `else` statements, along with some arithmetic and Boolean expressions. Let’s check if a given number is divisible by 2 without a remainder:
  
  ```java
  if (1 % 2 == 0)
  	even number
  else
  	odd number
      
  /// run loop from 0 - 10
  for (int i = 0; i <= 10; i++) {
          if (i % 2 == 0)
              System.out.println(i +" is an even number");
          else
              System.out.println(i+ " is a odd number");
  }    
  ```
  
  **Nested Loop**
  
  A nested loop is a structure where one loop (the *inner loop*) is contained entirely within another loop (the *outer loop*). The outer loop acts as a parent, controlling how many times the inner loop executes. The inner loop only runs when the outer loop iterates – each cycle of the outer loop triggers a full execution of the inner loop.
  
  **How it works:**
  
  * **Outer Loop Initialization**:
    The outer loop begins its execution first. It runs based on its own condition (e.g., `i < 5`).
  * **Inner Loop Dependency**:
    The inner loop executes only when the outer loop is in an active iteration. Each cycle of the outer loop triggers a full run of the inner loop.
  * **Inner Loop Completion**:
    The inner loop iterates until its own condition becomes false (e.g., `j < 3`). Once complete, control returns to the outer loop.
  * **Outer Loop Continuation**:
    The outer loop proceeds to its next iteration (if its condition is still true). This repeats until the outer loop’s condition fails.
  
  The key concept is that the **outer loop** begins execution, pauses, and allows the **inner loop** to run **until its condition becomes false**. Only after the inner loop completes does the outer loop resume its iteration.
  
  **Syntax:**
  
  ```java
  // outer loop
  for () {
      // inner loop
      for () {
          
      } // end of inner
      
  }// end of outer
  
  ```
  
  Some example:
  
  Imagine we want to print from `0` plus other `9` digits For example, 0: 1, 2, 3, 4, 5, 6, 7, 8, 9 and 10: 11, 12, ..., 19, and so on up to 99. 
  
  Lets implement a loop that will just print from `0` up to `100`:
  
  ```java
  for (int i = 0; i <= 100; i+= 10) {
      System.out.print(i+ ": ");
  }
  // 0: 
  // 10: 
  // 20: 
  // 30: 
  // 40: 
  // 50: 
  // 60: 
  // 70: 
  // 80: 
  // 90: 
  
  ```
  
  The outer loop is response print number from 0..90. Below we will stitch another loop, inner loop that will print `0: 1, 2, 3, 4, 5, 6, 7,  8, 9`.
  
  ```java
  for (int i = 0; i < 100; i+=10) {
      System.out.print(i+ ": ");
      int end = i + 10;
      for (int j = i + 1; j < end; j++) {
          System.out.print(j+ ", ");
      }
  
      System.out.println();
  }
  /*
  0: 1, 2, 3, 4, 5, 6, 7, 8, 9,
  10: 11, 12, 13, 14, 15, 16, 17, 18, 19,
  20: 21, 22, 23, 24, 25, 26, 27, 28, 29,
  30: 31, 32, 33, 34, 35, 36, 37, 38, 39,
  40: 41, 42, 43, 44, 45, 46, 47, 48, 49,
  50: 51, 52, 53, 54, 55, 56, 57, 58, 59,
  60: 61, 62, 63, 64, 65, 66, 67, 68, 69,
  70: 71, 72, 73, 74, 75, 76, 77, 78, 79,
  80: 81, 82, 83, 84, 85, 86, 87, 88, 89,
  90: 91, 92, 93, 94, 95, 96, 97, 98, 99,
  */
  ```
  
  
  
  
  
  [For more example code challenges]()
  
  **Summary:**
  
  1. An iterative statement repeats a block of code as long as the condition remains `true`.
  2. The iterative statements are `while`, `do-while`, and `for` loops.
  3. 
  4. The three types of iterative statements have the following in common:
     1. **Parentheses:**
        1. Assignment of the control variable or a sentinel value.
        2. A Boolean expression (condition) that controls the iteration.
        3. Reassigning the control variable to keep the loop moving toward the end.
     2. **Body:** A block of code consisting of instructions and expressions.
  5. The `while` loop checks the condition before executing the body.
  6. The `do-while` loop executes the body before checking the condition.
  7. The `for` loop groups everything within the parentheses (assignment, condition, reassignment) and checks the condition before executing the body.
  8. The body of a `for` loop contains instructions or expressions, along with an optional increment or decrement.
  
  
