# Getting In To Programming

As we cover some fundamentals of programming in lesson-1(L101) here we will take a deep dive into some key components of programming.

Here I is just want to keep it beginner-friendly.

Prerequisite: No prior programming knowledge is required

[TOC]



## Values and Types

A value is one of the basic thing a program works with, like a letter or a number. a letter can be a person name and number can be a money value.

These values which a program interact with are of different types. We all know a text is not the same with a number, so that's there types come in to play. There are many types for a value as far as programming is concern.

#### Different Types or Data Types

* A value which takes a text is considered to be of type `string`, string mean series of characters like "lamin" in some programming language and double quotes while others there in single quotes.
* a value of type number can also be subdivided into two or more like whole number and a decimal number.
* There are other values of type different from text or number like in the case of `yes or no` situation. Well in programming we denote these with `true or false`.
* There are another types which can store more than one value like `array` or an `object`

We will cover about values and types in the coming lessons in respective programming languages.

## The Variable Concept

In a computer we can create container to store values(files) and sub-folder. Folders are the container that we use to store other related values either files and sub-folders. If you create a folder or file it is stored into your hard-drive. Our program also behave in a similar manner.

We all interact with a programs and provide them with some information. But, how those a program store this information given by a user? A program in itself have created containers to store information of the user and display this information which are stored in the containers. These containers are called a `variables` in a program.

### What is a Variable

Variable is a store or container that hold a value inside a program. These values can be a name of a person, age of a person, bank-account balance, a truthy or a falsely value etc. The term `variable` means that the value can vary meaning it can change. But, not all the values of a variable can be change in the scope of the program some do not change their values when created, but in most case they do.

Variable has a type in some programming languages while in other variables are not consider to have a type. This refers to as `static and dynamic` type.

#### Static Type Languages:

 Variable most a have a predefined type for example if you are to create a variable that will store a person's name obviously the type is going to be a `string`, likewise a person age is going to be a number type. example of static type language is Java

#### Dynamic Type Languages:

In these type of languages type-checking is very loose, it does not care about the type of variable, it can store a `string` value at one time and can store a `number` at another time. Example of these type of language are JavaScript, Python etc.

## Operator and Operand

### Operator 
In programming, we have special symbols to carry out some operations(computation like addition, subtraction, division, multiplication or even assigning value to a variable etc.). These symbols are driven from Mathematics, but some are called differently and have different use cases in programming. An Operator act on operands; by these a new value is produce,  a new value can be assigned to a variable, a new value can be reassigned to variable.

#### Types of Operators

* Assignment operator: these assign `=` a value to a variable
* Arithmetic operators: they are used to performing arithmetic operations on values. example are addition, multiplication, division, subtraction, and module or reminder
* Comparison or Relational operator: they are used to compared values(or variables). examples are greater than, less than, equal to, greater than or equals to, less than or equals to, and not equals to.
* Logical operator: they are used to applying logics to values or variables. examples are AND, OR, and NOT.
* Ternary operator: is the only conditional operator that take three operands. It can be used to replace `if and else` or `switch`. `10 > 9 ? 'do something' : 'do something;'
* Unary operator: these type of operator act on only one value meaning it has one operand. `10++ or ++10`

### Operand

An operand is a value(or a variable name) which an operator act upon. `3 + 2 ` will produce `5` which a new value is gain as a result of the computation or an operation, the operator there is `+` and the two operands are `3 and 2`. 

## Expression

Expression plays a very important role in programming. We use expression to generate new values, assign value to a variable. An expression comprises `values`, `variables`, `operators`, or simple `methods call`.

## Statement

A statement is a simple instruction that will command a computer to carry out a particular task. This includes variable, value, operator, and an expression as well. In some languages every statement is terminated with a semicolon while others no termination is required.

#### Types of statements

* Expression statement
* Declaration statement
* Selection statement
* Loop or Iterative statement
* Flow control or  jump statement

## Algorithm

Solving a problem with code need a considerable steps and these steps have to perform in a sequence that will give desirable output. For example a program that prompt a user to enter their name and display it to the screen. Well the first thing to do is to ask the user to enter their name then take that value and display it to the screen otherwise the program will not perform correctly.

In a simple tern an **Algorithm** is an action taken by a programmer to solve a problem in a specific other. **Action** are the `statement`, `expression`, and **Order** is how you place your `statements` and `expressions`.

## Errors and Exceptions 

An illegal token or  a misbehavior in a program what refers to as an error. These errors can be violating the rule of the programming language syntax, logical or a runtime error. type of error in programming:

#### Syntax Error 

Syntax refer to the set of rules that govern how words are combined to form a phrase or a sentence. Well, in programming we have these group of words as well which are `variable names`, `values`, `operators`, `expression` and `statement`. All programming language have their onw set of rules some are very strict and other are not. This kind of error will spot the program from execution.

All programming language have certain reserve word which cannot be use by programmers to name their `variable`, `method` or `class`. using a reserve as your variable is a *syntax error*, omitting an operator where it is supposed to be is regarded as a *syntax error* , not terminating each expression or statement is a syntax in other  languages. What is considered as a syntax error in one language might not be the case in another.

#### Logical Error

This kind of error will not prevent the program from executing rather the program will output what was intended the programmer. example a programmer writes a program to add two number instead of put `+` the programmer use `*` operator. This kind of error is very hard to detect especially in a large program.

#### Runtime Error

As the name says **runtime error**, these kind errors occur when the program starts to running, and they are also called exception. A programmer can therefor write an exception to anticipate any feature exceptions. There kind of error will stop the program from executing.



## Debugging

The stage of find error in a program is refers to as debugging, error are call bugs in software code. This is one thing a programmer will always be doing, it can be frustrating at the early stage of your coding journey. Believe it or not, the more good you are with debugging the better you become with programming. 
