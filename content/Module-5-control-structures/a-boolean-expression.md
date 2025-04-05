# Boolean Expressions

We have previously learned about **[expressions]()** as constructs in programming that evaluate to a specific value. For instance, an arithmetic expression like `1 + 1` evaluates to `2`.

Boolean expressions, on the other hand, are expressions that evaluate to either a `true` or `false` value. These expressions form the backbone of decision-making processes in programming.

Moreover, by evaluating conditions as either truthy or falsely, Boolean expressions enable programs to make logical decisions, control the flow of execution, and solve complex problems efficiently—especially in areas such as conditional branching and loop control. 

**Topics to cover:**

1. Relational or comparison operator 
2. Logical operators
3. The flow of executing Boolean expressions

Earlier, we learned about **[arithmetic operators]()**, which operate on numeric values and produce numeric results. However, there are other types of operators that also act on numeric values but return a Boolean result—these form what we call Boolean expressions, as they evaluate to either `true` or `false`.

Furthermore, there are Boolean operators (such as `&&`, `||`, and `!`) that operate specifically on Boolean values and also produce Boolean outcomes. These are essential in constructing logical conditions used in decision-making structures like `if`, `while`, and `for` statements.

### **1 Relational and Comparison Operators**

Relational or comparison operators are used to compare numeric values, including integers and floating-point numbers. These operators evaluate expressions and return a Boolean value (`true` or `false`). Whenever a relational operator is applied to numerical values, the result is always a Boolean .

Below is a table highlighting five key relational or comparison operators along with their descriptions:

| Operator | Name                     | Description                                                  |
| -------- | ------------------------ | ------------------------------------------------------------ |
| `>`      | Greater than             | Returns `true` if the left value is greater than the right; otherwise `false`. |
| `<`      | Less than                | Returns `true` if the left value is less than the right; otherwise `false`. |
| `>=`     | Greater than or equal to | Returns `true` if the left value is greater than or equal to the right; otherwise `false`. |
| `<=`     | Less than or equal to    | Returns `true` if the left value is less than or equal to the right; otherwise `false`. |
| `==`     | Equal to                 | Returns `true` if the left and right values are equal; otherwise `false`. |
| `!=`     | Not equal to             | Returns `true` if the left and right values are **not** equal; otherwise `false`. |

---



```java
/*
-----------------------------------------------------
Operator		|	Examples	|  Return value			
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

As seen above, relational or comparison operators always evaluate to Boolean values.

---

### **2 Logical Operators**

Logical operators, also known as Boolean operators, operate exclusively on Boolean values (`true` or `false`). They evaluate expressions and return a Boolean result. The three primary logical operators are:

- **AND (`&&`)** – Returns `true` only if both conditions are `true`.
- **OR (`||`)** – Returns `true` if at least one condition is `true`.
- **NOT (`!`)** – Reverses the Boolean value, returning `true` if the condition is `false`, and vice versa.

Below is a table highlighting the logical operators along with their descriptions:

| Name | Symbol | Description                                                  |
| ---- | ------ | ------------------------------------------------------------ |
| AND  | `&&`   | Returns `true` **only if** both operands are `true`; otherwise returns `false`. |
| OR   | `||`   | Returns `true` if **at least one** operand is `true`; otherwise returns `false`. |
| NOT  | `!`    | Inverts the Boolean value: returns `true` if the operand is `false`, and `false` if the operand is `true`. |

---

Here’s a **truth table** for the basic logical operators (`AND`, `OR`, `NOT`):

| **A**   | **B**   | **!A** (NOT A) | **A && B** (AND) | **A \|\| B** (OR) |
| ------- | ------- | -------------- | ---------------- | ----------------- |
| `true`  | `true`  | `false`        | `true`           | `true`            |
| `true`  | `false` | `false`        | `false`          | `true`            |
| `false` | `true`  | `true`         | `false`          | `true`            |
| `false` | `false` | `true`         | `false`          | `false`           |

---

### **Key Notes**:  
1. **AND (`&&`)**  
   - Only returns `true` if both operands are `true`.  

2. **OR (`||`)**  
   - Returns `true` if at least one operand is `true`.  

3. **NOT (`!`)**  
   - Flips the Boolean value (`true` → `false`, `false` → `true`).  

4. **Short-Circuit Evaluation** (Java-specific):  
   - For `A && B`, if `A` is `false`, `B` is not evaluated.  
   - For `A || B`, if `A` is `true`, `B` is not evaluated.  

### **Understanding Logical Expressions in Java**

Logical expressions in Java are evaluated step by step, following operator precedence rules. Let's break down some examples:

#### **Example 1: `a > b || b == c`**

At first glance, it may seem like Java evaluates the entire expression at once, but it actually processes each part in sequence:

1. **Operator precedence:** Comparison operators (`>`, `==`) have higher precedence than logical operators (`||`).
2. **First evaluation:** `a > b` is computed. If `a` is greater than `b`, this results in `true`.
3. **Second evaluation:** `b == c` is checked, returning `false` if `b` is not equal to `c`.
4. **Final evaluation:** The logical OR (`||`) operator combines both results: `true || false` evaluates to `true`.

#### **Example 2: `b >= a || !(c == a)`**

1. **First execution:** `b >= a` is evaluated first, resulting in `true`.
2. **Second execution:** The parenthesis will be cleared first, so Java first evaluates `c == a`. If `c` is not equal to `a`, this results in `false`.
3. **Negation applied:** `!(false)` simplifies to `true`.
4. **Final execution:** Combining `true || true` results in `true`.

#### **Example 3: `!(c <= a && c >= a)`**

Here, parentheses force Java to evaluate the inner expressions first following **BODMAS** rules:

1. **First execution:** `c <= a` is checked, returning `false`.
2. **Second execution:** `c >= a` is checked, returning `true`.
3. **Third execution:** `false && true` results in `false`.
4. **Final execution:** The negation operator (`!`) flips `false` to `true`.

The example above combines both relational and logical operators to construct a complex Boolean expression. Regardless of how simple or complex the expression may be, it will ultimately evaluate to a single Boolean value — either `true` or `false`.

Understanding this concept is fundamental, as it will help you navigate and apply logical reasoning effectively in the upcoming modules.

**Summary:**

* A Boolean expression always evaluates to a Boolean value (`true` or `false`).

* Relational (or comparison) operators act on numeric values and return a single Boolean value.

* Common relational operators include:

  * Greater than (`>`) and less than (`<`)

  - Greater than or equal to (`>=`) and less than or equal to (`<=`)

  - Equal to (`==`) and not equal to (`!=`)

* Logical operators operate exclusively on Boolean values and also return a Boolean result.

* Logical operators are also referred to as Boolean operators.

* The primary logical operators are:

  * **AND** (`&&`)

  * **OR** (`||`)

  * **NOT** (`!`)

* A combination of both relational and logical operators can be used to construct more complex Boolean expressions, which still evaluate to a single Boolean value.
* Relational and logical operators are fundamental tools for writing complex conditional logic in programming.
