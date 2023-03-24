# Decision

One most essential thing in programming is decision making and which is why man rely heavily on computer. 

## Relational and Comparison Operator  

 Relational and comparison operator are use to compare number values(integer, and floating point values), they act on number values and evaluate to a boolean value. When you use a relational or comparison operator on number value you will always get a boolean out of the expression.

Below is a table showing 5 relational or comparison operator and their description:

| Operator | Name                      | Description                                                  |
| -------- | ------------------------- | ------------------------------------------------------------ |
| >        | Greater than              | It will compare the left operand against the right, return `true` if  it greater than otherwise  `false` |
| <        | Less than                 | It will compare the left operand against the right, return `true` if  it less than otherwise  `false` |
| >=       | Greater than or equals to | It will compare the left operand against the right, return `true` if it is greater than or equals to otherwise  `false` |
| <=       | Less than or equals to    | It will compare the left operand against the right, return `true` if it is less than or equals to otherwise  `false` |
| ==       | Equals to                 | It will compare the left operand against the right, return `true` if they are equal otherwise  `false` |
| !=       | Not equals                | It will compare left operand against the right, return `true` if they are not equal  otherwise  `false` |



```java
/*
-----------------------------------------------------
Operator		 |	Examples	 |  Return value			
>				|	1 > 2		|  false
<				|	1 < 2		|  true
>=				|	2 >= 2		|  true
<=				|	3 <= 2		|  false
==				|	1 == 2		|  false
!=				|	1 != 2		|  true
*/

// You copy and paste the below code into your code editor to see the outcome
double a = 5, b = 10;
System.out.println(a > b)
System.out.println(a < b)
System.out.println(a >= b)
System.out.println(a <= b)
System.out.println(a == b)
System.out.println(a != b)
```

Tip: *Do not get sick of creating new projects to test our things. One project can contain one or more classes*

## Logical Operator

Logical operators is also regarded as `boolean` operators because they act on boolean values only, and therefor they return or evaluate to a `boolean` value as well. They are AND, OR, and NOT

Let's try to see them:

| Name | Symbol | Description                                                  |
| ---- | ------ | ------------------------------------------------------------ |
| AND  | &&     | These check the right-hand operand against the left-hand operand, and return `true` if both are values are `true` otherwise `false` |
| OR   | \|\|   | These check the right-hand operand against the left-hand operand, and return `true` if one of the value is `true` or both are `true` otherwise `false` |
| NOT  | !      | These operator is use to negate `boolean` values. It will return `true` when it is `false` and return `false` when it is `true` |

Let's see them:

Copy and paste the code snippet below

```java
public class LogicalOp {
    public static void main(String[] args) {
        System.out.println("Logical Operators");
        System.out.printf("%35s%n", "The Truth Table");
        System.out.printf("%-10s%n", "----------------------------------------------------------");
        System.out.printf("%-20s%-25s%s%n", "Operator(Symbol)", "Expression", "Evaluation");
        System.out.printf("%-20s%-25s%s%n", "AND (&&)", "true && true", (true && true));
        System.out.printf("%-20s%-25s%s%n", "AND (&&)", "true && false", (true && false));
        System.out.printf("%-20s%-25s%s%n", "OR (||)", "true || true", (true || true));
        System.out.printf("%-20s%-25s%s%n", "OR (||)", "true || false", (true || false));
        System.out.printf("%-20s%-25s%s%n", "NOT (!)", "!true", (!true));
        System.out.printf("%-20s%-25s%s%n", "NOT (!)", "!false", (!false));
    }
}
```

Note: *Here we are using `printf()` instead of `print() or println()`.*

The `printf()` will helps with indention, creating equal space when print multiple items on the sate print statement. The `printf()` can take a minimum of two argument and a maximum of four, the first argument is the format and the rest are the are items you wish to print. The first argument `"%-20s%-25s%s%n"` have be wrap in a double quotation, the values `20` and `25` are for spacing, and they are only ones which can be change. You can change the number and see the spacing yourself.

Run your program:

<img src="../assets/week4/img1.PNG" />

### Some More Examples on Logical Operators

```java
public class MoreExampleOnLogicalOp {
    public static void main(String[] args) {
        int a = 20, b = 15, c = 35;

        boolean check1 = a > b || b == c;
        boolean check2 = a >= c && b != b;
        boolean check3 = b >= a || !(c == a);
        boolean check4 = !(c <= a && c >= a);
        boolean check5 = !(b >= a || c == a);

        System.out.println("Expression \t\t\t\t\tValue");
        System.out.println("a > b || b == c \t\t\t" +check1);
        System.out.println("a >= c && b != b \t\t\t" +check2);
        System.out.println("b >= a || !(c == a) \t\t" +check3);
        System.out.println("!(c <= a && c >= a) \t\t" +check4);
        System.out.println("!(b >= a || c == a) \t\t" +check5);
    }
}
```

Play with the code snippets above and see what it will evaluate to.

Let's look deep into some of the above expression:

* `a > b || b == c` this may seem to be executed by Java one-off. No Java will extract out one expression before running the other:
  * Comparison operators have the highest rule of precedence  logical operators
  * Frist execution: `a > b` will evaluate to `true`, `b == c` evaluate to `false`
  * Second execution: `true || false` which will evaluate to ` true`
* When a parenthesis is involve: `b >= a || !(c == a)`
  * First execution: `b >= a` which will evaluate to `true`
  * Second execution: `!(c == a)` remember the BODMAS Java focus inside the parenthesis first, `c == d` which is `false`, then `!false` which will evaluate to `true`
  * Last execution: the value of the first execution `true`, the logical operator `||` the value of the second execution `true` which is `true`
* When every thing is wrap in a parenthesis `!(c <= a && c >= a)`:
  * First execution: `c <= a` which will evaluate to `false`
  * Second execution: `c >= a`  which will evaluate to `true`
  * Third execution: `false && true` which will evaluate to `false`
  * Final execution: `!false` which will evaluate to `true`

## IF And Else Statement

## If Statement

An if statement is part of the control statements that takes a single boolean or multiples boolean values in it's condition and execute what is in the body when the condition meet.

Let's see:

* Condition of the if statement: `if(condition)`
* Body comprises  opening and closing brace and get execute when the condition is true: `if(condition){print}`

```java
boolean flag1 = true;
if(flag){
	System.out.println("Flag is true");
}
// Flag is true 

boolean flag2 = false;
if(flag){
	System.out.println("Flag is true");
}
//

//trail
if(ture){
    System.out.println("Java is nice!");
}
// Java is nice
if(!ture){
    System.out.println("Java is nice!");
}
//
```

Note! *if you have a statement or an expression below a if statement it will execute regardless*

## If and Else Statement

This time we have a condition that we will be check first then we have a fallback. As we seen in the previous we print in the console only when the condition is true and nothing is printed when false.

Here we can do it better, is not that a single `if` statement is not a good mechanism. Yes it is in some situations.

Let's see:

*  Condition of the if statement: `if(condition)`
*  Body comprises  opening and closing brace and get execute when the condition is true: `if(condition){print}`
*  Default `else`
*  Body of the else `else {print}`

```java
int age = 17;
if(age >= 18){
	System.out.println("Access granted!");
} else {
	System.out.println("Access denied!");
}
// Access denied!
```

Note! *in a if and else statement something has to execute*

## If, Else if and Else Statement

This is sometime regarded as nested if statement, is a great choice if you are checking more than one conditions.

Let's see:

* Condition of the if statement: `if(condition)`
* Body comprises  opening and closing brace and get execute when the condition is true: `if(condition){print}`
* The second condition `else if(firstCondition)`
* Body of the else if statement `else if(econdCondition) {print}`
* Default `else`
* Body of the else `else {print}`

```java
 int age = 46;
if(age < 10 ){
    System.out.println("Baby");
} else if (age >= 10 && age <= 17){
    System.out.println("Child");
} else if(age >= 18 && age <= 45){
    System.out.println("Youth");
} else {
    System.out.println("Adult");
}
// Adult
```

Note! *we use comparisons and logical operator to have check different range of conditions, you to be really carefully comparison and logical is one expression*

## Nested If Statement

In a nested if statement we nest if statement inside a if statement. There is a outer and inner if statement, the inner statement got executed when the outer condition is true.

Let's see:

```java
boolean flag = false;
     
     if(flag){
         int num = 100;
         if(num > 100){
             System.out.println("The number is greater than 100");
         } else{
             System.out.println("The number is not greater than 100");
         }
     } else {
         System.out.println("Oops!");
     }
```

Note! *we can use nested if statement for checking complicated conditions*

## Switch Statement

A switch works just the same as if statement, it has a condition and case(s) and fallback, the default.

Let's see:

* Condition of a switch `switch(condition)`
* Body comprises  opening and closing brace, some cases and a default : `switch(condition){case 1: print break; case 2: print break; default: print}`

```java
  int num = 100;
   switch (num){
       case 100:
           System.out.println("A");
           break;
       case 20:
           System.out.println("B");
           break;
       default:
           System.out.println("Non of the above!");
   }
//A
```

Note! *switch statement cannot replace if statement in all situations*