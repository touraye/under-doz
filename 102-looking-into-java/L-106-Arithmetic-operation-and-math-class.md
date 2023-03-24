# Arithmetic Operation And Math Class

#### Arithmetic Operator
In Java, we use Arithmetic operator do some Mathematical operations like `addition`, `subtraction`, `division`, `multiplication`, and `modules`. The arithmetic operator are binary because they act on two operands:
```java
int a = 10, b = 4;
int sum = a + b;
int product = a * b;
int sub = a - b;
int div = a / b;
int mud = a % b;
// +, *, -, /, % are arithmetic operators
// expression a + b contains the binary operator(+) and the two operans(a and b)
```

Let look at the arithmetic operators in detail:

| Name                | Symbol | Description                                                  |
| ------------------- | :----: | ------------------------------------------------------------ |
| Additional          |   +    | Adds the right operand with the left operand and return the sum |
| Subtraction         |   -    | Minus the right operand from the left operand and return a value |
| Multiplication      |   *    | Multiply the right operand with the left operand and return the result |
| Division            |   /    | Divide the right operand with the left operand and returns the result |
| Modulus or Reminder |   %    | Divide the right operand with the left operand and returns the reminder |

## Rules of Precedence

In programming is not always the case that all Arithmetic expressions have to evaluate together, some to have wait for others to evaluate first because arithmetic operators have different level of rules of precedence. 

* Multiplication, reminder, and division have the higher level of precedence than addition and subtraction
* If an expression contain (*, /, %) it start from left to right hence they have the same level of precedence
* If an expression contain (+, -) it also start from left to right hence they have the same level of precedence
* Assignment operator has the lowest level  precedence

Programmer can also change these rules of precedence by putting expression in a parentheses `()`. Which follows the BODMAS principles. 

```java
Algebra:
Java: m = (a + b + c + d + e) / 5;
Algebra:
Java: y = m * x + b;
 y = (a * x * x) + (b * x) + c;
   
// Assignment operator has a low rules of precedence
int a = 2 * 3; 
// The arithmetic expression of 2 * 3 has to execute first then followed by expression that will assign value to a variable

int z =  p * r % q + w / x - y;
// 
```

## Java Math Class

The Java Math class provides several methods to works on math calculations like:

* `Math.min()` this method takes two parameters and return the minimum value
* `Math.max()` this method tales two parameters and return the maximum value
* `Math.sqrt()` this method takes one parameter and return the square root of the number passed
* `Math.pow()` this method takes two parameter and returns the value of the first argument raised to the power to second argument
* `Math.abs()` this take one parameter and return the absolute value of the passed value
* `Math.round()` this method take one parameter and return the nearest value of the given value.

*The above listed are  some of the methods provided by the Math class we cover more in detail*

## Random Class

```java
Random ran = new Random();
int f1 =  ran.nextInt((9999 - 100) + 1) + 10;
System.out.println(f1);
// 7124
```

## Decimal Format

Formatting decimal is used to format numbers the way you specify by passing your pattern in to the constructor, and we utilize the `format()`. Here I will show two ways of doing it:

```java
double unit = 49.908000000000006;
double amount = 2300.02829;
DecimalFormat format = new DecimalFormat("0.00");
System.out.println(format.format(unit));
System.out.println(format.format(amount));
// 49.91
// 2300.03

String pattern = "###,###.###";
DecimalFormat decimalFormat = new DecimalFormat(pattern);
System.out.println("format 1: " +decimalFormat.format(1200.00));
System.out.println("format 2: " +decimalFormat.format(1200.03));
// format 1: 1,200
//format 2: 1,200.03
```

## Currency Format

The String class has lots of methods for many different purposes. Here we will be utilizing the `format()` method from the String class to format number.

Dealing with monetary value the `format()` from the String is very useful. This method takes two parameters, the first parameter is the pattern which the `format`()  requires(it will throw an exception if you don't provide the right pattern), and second is the values of type floating point if not it will thrown an exception.

```java
double amount = 1200;
System.out.println("Amount: GMD" +String.format("%,.2f", amount));
// Amount: GMD1,200.00
```
