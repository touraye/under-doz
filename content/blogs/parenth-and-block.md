# Parenthesis And A Block

In programming we have seen a parenthesis `()` and block `{}` played themselves in multiple places, all trying to achieve a different thing, and despite their different applications these two are always glue to together to form a robust logics expect while places. In this blog we will explore their differences in terms of syntax, what each embodies, and their use cases.

## What is Parenthesis

A parenthesis comes from the word parent; you can think of it as a wrapper that groups expression or logic together. Both Mathematic and Programming uses the same but refer to it differently, so therefore, if you are coming from Mathematic you would argue. Mathematic refer to it as round-bracket, yes you right. 

## What is a Block

A block on the other hand is groups related codes 



**Programming and Mathematics**

Similar use cases of a parenthesis in both Math and Programming; is to [change the order of expression](https://github.com/touraye/under-doz/blob/main/content/Module-2-introduction-to-programming/c-getting-into-programming.md#rule-of-precedence) for example; `3 * 4 + 5` is not the same as `3 * (4 + 5)`.

**General Programming**

Programming in general it is used in different places; a parent is use in **[conditional statement]()** were we group **[boolean expressions]()** 

```java
if (true) // simple
if (5 > 4) // boolean expression
if ((5> 4) && (10 != 10)) // complex boolean expression
```

Furthermore, a parenthesis is use in an **[iterative statement]()** were we leverage conditional statements. A conditional statement is wrapped within a parenthesis that serve as the control mechanism for the iterative statement:

```java
while (true) // a simple boolean value
while (a <= 5) // boolean expression
for (int i = 0; i <= 5; i++) // a statment and two expressions
```

Parenthesis is also use to in a sub-routines aka function. A subroutine is denote by parenthesis were we pass in augments aka inputs and separate them by a comma if more than one:

```java
void displayInfo() // 
int sum(int a, int b) //
```

Last but no the least is the sub-routine invocation:

```java
displayInfo(); // 
sum(5, 4); // 
```

