# Getting In To Programming

In Lesson-1 (L101), we covered some fundamentals of programming. Now, let's delve deeper into key components of programming.

Here, I just want to keep it beginner-friendly.

Prerequisite: There is no need for prior programming knowledge.



[TOC]



## Values and Types

A value is one of the basic elements that a program operates with, such as a letter or a number. A letter can represent a person's name, and a number can represent a monetary value.

The values with which a program interacts come in various types. Text is distinct from a numerical value, so different types come into play. In programming, there are numerous types for values.

#### Different Types or Data Types

* A value that takes a text is considered to be of type 'string'. A string refers to a series of characters, such as "Lamin" in some programming languages, enclosed in double quotes or, in some cases, single quotes.
* A value of type 'number' can also be further subdivided into categories like whole numbers and decimal numbers.
* There are other value types distinct from text or numbers, such as in a 'yes or no' situation. In programming, we represent these with 'true or false'.
* Another type allows for the storage of more than one value, such as an 'array' or an 'object'.

In the lessons to come, we will explore values and types.

## The Variable Concept

In a computer, we have the ability to create containers for storing values (files) and sub-folders. Folders act as containers used to store other related values, be they files or sub-folders. When you create a folder or file, it is stored on the computer's hard drive. Our program follows a similar behavior.

We all interact with programs and provide them with information. However, have you ever wondered how a program stores the information given by a user? Programs create containers to store user information, and these containers are referred to as 'variables' within the program. These variables can exist either within the program or in an external source known as a database.

### What is a Variable

A variable is a storage or container within a program that holds a value. These values can represent various information such as a person's name, age, bank account balance, or a truthy or falsely value. The term 'variable' implies that the stored value can vary, meaning it can change. However, not all variable values can be changed within the scope of the program; some remain constant once created, though in most cases, they are subject to change.

In certain programming languages, variables are assigned a type, whereas in others, variables are not designated with a specific type. This distinction is often referred to as 'static and dynamic' typing.

#### Static Type Languages:

 Most variables must have a predefined type. For instance, if you create a variable to store a person's name, its type will be 'string,' and similarly, a person's age will be of the 'number' type. An example of a static-type language is Java.

#### Dynamic Type Languages:

In such languages, type-checking is very lose; it does not concern itself with variable types. A variable can hold a 'string' value at one moment and a 'number' at another. Examples of such languages include JavaScript, Python, etc.

## Operator and Operand

### Operator 
In programming, specific symbols are utilized to perform various operations such as addition, subtraction, division, multiplication, and the assignment of values to variables. While these symbols are inspired by mathematics, they are sometimes referred to by different names and serve distinct purposes in programming. Operators operate on operands, producing new values that can be assigned or reassigned to variables.

#### Types of Operators

* The assignment operator `=` is used to assign a value to a variable.
* Arithmetic operators perform arithmetic operations on values. Examples include addition, multiplication, division, subtraction, and modulus or remainder.
* Comparison or Relational operators are used to compare values (or variables). Examples include greater than, less than, equal to, greater than or equal to, less than or equal to, and not equal to.
* Logical operators apply logic (conditions) to values or variables. Examples include AND, OR, and NOT.
* The ternary operator is the only conditional operator that takes three operands. It can be used to replace `if` and `else` or `switch`. Example: `10 > 9 ? 'do something' : 'do something;'`
* Unary operators act on only one value, meaning they have one operand. Examples include `10++` or `++10`.

### Operand

An operand is a value(or a variable name) which an operator act upon. `3 + 2 ` will produce `5` which a new value is gain as a result of the computation or an operation, the operator there is `+` and the two operands are `3 and 2`. 

## Expression

Expression plays a very important role in programming. We use expression to generate new values, assign value to a variable. An expression comprises `value`, `variable`, `operator`, or simple `method call`.

## Statement

A statement is a simple instruction that gives command to a computer to carry out a particular task. This includes variable, value, operator, and an expression as well. In some languages every statement is terminated with a semicolon while others no termination is required.

#### Types of statements

* Expression statement
* Declaration statement
* Block Statement
* Selection statement
* Loop or Iterative statement
* Flow control or  jump statement

## Algorithm

Solving a problem with code need a considerable steps and these steps have to perform in a sequence that will give desirable output. For example a program that prompt a user to enter their name and display it to the screen. Well, the first thing to do is to ask the user to enter their name then take that value and display it to the screen otherwise the program will not perform correctly.

In a simple tern an **Algorithm** is an action taken by a programmer to solve a problem in a specific other. **Action** are the `statement`, `expression`, and **Order** is how you place your `statements` and `expressions`.

## Errors and Exceptions 

An illegal token or  a misbehavior in a program refers to an error. These errors can be violating the rule of the programming language syntax, logical or a runtime error. type of error in programming:

#### Syntax Error 

Syntax refer to the set of rules that govern how words are combined to form a phrase or a sentence. Well, in programming we have these group of words as well which are `variable names`, `values`, `operators`, `expression` and `statement`. All programming language have their onw set of rules some are very strict and other are not. This kind of error will spot the program from execution.

All programming language have certain reserve word which cannot be use by programmers to name their `variable`, `method` or `class`. using a reserve as your variable is a *syntax error*, omitting an operator where it is supposed to be is regarded as a *syntax error* , not terminating each expression or statement is a syntax in other  languages. What is considered as a syntax error in one language might not be the case in another.

#### Logical Error

This kind of error will not prevent the program from executing rather the program will not output what was intended by the programmer. example a programmer writes a program to add two number instead of put `+` the programmer use `*` operator. This kind of error is very hard to detect especially in a large program.

#### Runtime Error

As the name says **runtime error**, these kind errors occur when the program starts to running, and they are also called exception. A programmer can therefor write an exception to anticipate any feature exceptions. There kind of error will stop the program from executing.

A Key Note: All the above mention are general programming concepts, they are applicable in a all programming languages. The only difference is that each programming languages have their implementations.

## Debugging

The stage of finding error in a program is refers to as debugging, error are called bugs in software code. This is one thing a programmer will always be doing, it can be frustrating at the early stage of your coding journey. Believe it or not, the more good you are with debugging the better you become with programming. 



[Next lesson](https://github.com/touraye/under-doz/blob/main/102-looking-into-java/L-101-java-at-first-look.md)

[Previous lesson](https://github.com/touraye/under-doz/blob/main/101-programming/L101-the-way-we-program.md)
