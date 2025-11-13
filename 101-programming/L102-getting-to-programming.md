# Getting In To Programming

In Lesson-1 (L101), we covered some fundamentals of programming. Now, let's delve deeper into key components of programming.

Here, I just want to keep it beginner-friendly.

Prerequisite: There is no need for prior programming knowledge.



[TOC]



## Values and Types

A **value** is a fundamental unit of data that a program processes, such as a letter, number, or symbol. For example, a letter can represent a person's name, while a number can denote a monetary value.

Values in a program belong to different **types**, which define how they are stored and manipulated. Textual data is distinct from numerical data, requiring different types for proper handling. In programming, various data types exist to accommodate different forms of values, such as integers, floating-point numbers, strings, and boolean values.

#### **Different Types of Data Types**

- **String**: A value that represents text is classified as a **string**. A string is a sequence of characters, such as `"Lamin"`. In some programming languages, strings are enclosed in **double quotes (`" "`)**, while others allow **single quotes (`' '`)**.
- **Number**: A numerical value can be further categorized into **integers** (whole numbers) and **floating-point numbers** (decimals). For example, an integer can store a person's **age** (`25`), while a floating-point number can represent **monetary values** (`99.99`).
- **Boolean**: This type represents values that can be either **true** or **false**, often used in conditional logic. For example, in a **yes/no** scenario, a boolean variable can store `true` for "yes" and `false` for "no".
- **Collections**: Some data types allow for storing **multiple values** in a structured format. Common examples include:
  - **Arrays (Lists)**: Ordered collections of values (e.g., `[1, 2, 3, 4]`).
  - **Objects (Dictionaries, HashMaps)**: Key-value pairs used to represent structured data (e.g., `{"name": "Lamin", "age": 25}`).
- **User-Defined Types**: In **object-oriented programming (OOP)**, developers can define their own **custom data types** using **classes**. These allow for more structured and reusable code, enabling the creation of complex objects with attributes and behaviors.

In the lessons to come, we will explore values and types.

## **The Variable Concept**

In computing, we use **containers** to store values, similar to how files and folders are organized on a computer. **Folders** act as containers that hold related files or subfolders. When you create a folder or file, it is stored on the computer’s **hard drive**. Programs follow a similar approach to managing data.

Every day, we interact with programs by providing them with **information**—but how do these programs store and manage the data we input? Programs use **containers** to store user-provided information, and these containers are called **variables**. Variables can exist **within the program** or be stored in an **external source** such as a **database**.

------

### **What is a Variable?**

A **variable** is a storage unit within a program that holds a value. These values can represent different types of information, such as a person’s **name**, **age**, **bank account balance**, or a **boolean value** (`true` or `false`). The term **"variable"** signifies that the stored value can **change** during program execution. However, some variables remain **constant** once assigned, depending on how they are defined in the program.

In certain programming languages, variables must be explicitly assigned a **data type**, while in others, variables can store different types of values dynamically. This distinction is referred to as **static typing** (where variable types are fixed) and **dynamic typing** (where types are determined at runtime).

#### **Static Type Languages**

In statically typed languages, variables must be **explicitly declared** with a predefined **data type**. Once assigned, the type **cannot change** throughout the program’s execution. For example, a variable intended to store a **person’s name** must be of type **`string`**, while a variable storing **age** must be of type **`number`**. This strict type enforcement helps prevent type-related errors at **compile time**.

**Example of a static type language:** Java, C, C++

------

#### **Dynamic Type Languages**

In dynamically typed languages, variables **do not require** explicit type declarations. The **type is determined at runtime**, allowing a variable to hold a **string** at one moment and a **number** at another. This flexibility simplifies development but may lead to **runtime errors** if type mismatches occur.

**Examples of dynamically typed languages:** JavaScript, Python, Ruby

Here’s a refined and more technically precise version of your text:

------

## **Operator and Operand**

### **Operator**

In programming, **operators** are special symbols used to perform various computations, such as **addition, subtraction, multiplication, division**, and **assignment**. While these symbols are derived from mathematics, they often have additional meanings and functionalities in programming. Operators act on **operands**, producing new values that can be assigned to variables.

#### **Types of Operators**

- **Assignment Operator (`=`)** – Used to assign a value to a variable.

- **Arithmetic Operators** – Perform mathematical operations on values, including **addition (`+`), subtraction (`-`), multiplication (`\*`), division (`/`), and modulus (`%`, remainder)**.

- **Comparison (Relational) Operators** – Compare two values and return a boolean result (`true` or `false`). Examples include **greater than (`>`), less than (`<`), equal to (`==`), greater than or equal to (`>=`), less than or equal to (`<=`), and not equal to (`!=`)**.

- **Logical Operators** – Used to evaluate **boolean expressions** and control program flow. Examples include **AND (`&&`), OR (`||`), and NOT (`!`)**.

- Ternary Operator (`? :`) – The only conditional operator that takes 

  three operands. It is often used as a shorthand for `if-else` statements.

  - Example: `10 > 9 ? "Do something" : "Do something else";`

- Unary Operators – Operate on a single operand. Examples include 

  increment (`++`), decrement (`--`), and negation (`-`).

  - Example: `++x;` or `x--;`

------

### **Operand**

An **operand** is a value (or variable) on which an **operator** performs an operation.

Example: `result = 3 + 2;`

- Here, `+` is the **operator**, and `3` and `2` are the **operands**.
- The result of the operation (`5`) is a **new value** produced by the computation.

------

## **Expression**

An **expression** is a combination of **values, variables, operators, or function calls** that evaluates to a new value. Expressions are essential in programming as they generate and manipulate data.

Example:

```python
x = (5 + 3) * 2;  # Expression: (5 + 3) * 2
```

- This expression evaluates to `16`, which is then assigned to `x`.

------

## **Statement**

A **statement** is an instruction that directs the computer to perform a specific action. It may include **variables, values, operators, and expressions**. In some programming languages, statements must be terminated with a **semicolon (`;`)**, while others do not require termination.

### **Types of Statements in Programming**

1. **Expression Statement** – Evaluates an expression but does not store the result.
2. **Declaration Statement** – Declares variables or functions.
3. **Block Statement** – A group of statements enclosed in `{}` (curly brackets).
4. **Continue Statement** – Skips the remaining part of a loop iteration and moves to the next iteration.
5. **Compound Statement** – A combination of multiple statements.
6. **Selection Statement** – Controls flow based on conditions (`if-else`, `switch`).
7. **Loop (Iterative) Statement** – Repeats execution (`for`, `while`).
8. **Flow Control (Jump) Statement** – Alters the normal sequence of execution (`break`, `return`, `goto`).

------

## **Algorithm**

Solving a problem in programming requires following **a series of well-defined steps** in a specific sequence to achieve the desired outcome.

For example, if a program asks a user to enter their name and then displays it on the screen, the correct sequence is:

1. Prompt the user for input.
2. Store the input.
3. Display the stored value.

If the steps are not followed in the correct order, the program will not function correctly.

### **Definition**

An **algorithm** is a **systematic sequence of steps** used to solve a problem. It consists of:

- **Actions** – Statements and expressions that execute specific tasks.
- **Order** – The structured sequence in which these actions are placed.

A well-structured algorithm ensures efficiency, correctness, and maintainability in software development.

------

## **Errors and Exceptions**

In programming, an **error** refers to an **illegal operation** or a deviation from the expected behavior of a program. Errors can arise due to **violations of language syntax, flawed logic, or issues encountered during execution**.

### **Types of Errors in Programming**

### **1. Syntax Error**

**Syntax** refers to the set of rules that govern how **variables, values, operators, expressions, and statements** are structured in a programming language. Every language enforces specific syntax rules—some strictly, others more loosely.

A **syntax error** occurs when a statement **violates the grammatical rules** of the programming language, preventing the program from executing.

#### **Common Causes of Syntax Errors:**

- Using a **reserved keyword** as a variable, method, or class name.
- Omitting an **operator** where it is required.
- Forgetting to **terminate a statement** (e.g., missing a semicolon in languages like Java and C++).

Notably, what is considered a **syntax error** in one language may not be in another.

------

### **2. Logical Error**

A **logical error** does not prevent the program from running but causes it to produce **incorrect or unintended results**. These errors occur due to **flaws in the program's logic**, making them difficult to detect, especially in large codebases.

#### **Example of a Logical Error:**

```java
pythonCopyEdit# Intended operation: addition
result = 5 * 3;  # Incorrectly using '*' instead of '+'
```

- The program **runs without errors**, but the output is **incorrect** because multiplication was used instead of addition.

Logical errors require careful **code analysis and testing** to identify and fix.

------

### **3. Runtime Error (Exception)**

A **runtime error** (also called an **exception**) occurs **while the program is executing**. These errors **interrupt program execution** unless properly handled.

#### **Common Causes of Runtime Errors:**

- **Dividing by zero** (`10 / 0`).
- **Accessing an undefined variable**.
- **Using an invalid index in an array or list**.
- **Running out of memory** (infinite loops, excessive recursion).

To handle runtime errors gracefully, many programming languages provide **exception handling mechanisms** (e.g., `try...except` in Python, `try...catch` in Java and JavaScript).

------

## **Debugging**

The process of **identifying and fixing errors in a program** is called **debugging**. Errors in code are commonly referred to as **bugs**, and **debugging is an essential skill** for every programmer.

Early in your coding journey, debugging can feel **challenging and frustrating**, but as you gain experience, you develop techniques to efficiently identify and resolve issues. **Good debugging skills lead to better programming proficiency.**



[Next lesson](https://github.com/touraye/under-doz/blob/main/102-looking-into-java/L-101-java-at-first-look.md)

[Previous lesson](https://github.com/touraye/under-doz/blob/main/101-programming/L101-the-way-we-program.md)
