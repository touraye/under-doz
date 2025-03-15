# Decision Making in Programming

Decision-making is a fundamental aspect of programming, enabling computers to process information and make logical choices, much like humans rely on them for complex problem-solving.

### **Relational and Comparison Operators**

Relational or comparison operators are used to compare numeric values, including integers and floating-point numbers. These operators evaluate expressions and return a boolean value (`true` or `false`). Whenever a relational operator is applied to numerical values, the result is always a boolean.

Below is a table highlighting five key relational or comparison operators along with their descriptions:

Here's a revised version with cleaner formatting and concise descriptions:

---

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

---

### **Logical Operators**

Logical operators, also known as boolean operators, operate exclusively on boolean values (`true` or `false`). They evaluate expressions and return a boolean result. The three primary logical operators are:

- **AND (`&&`)** – Returns `true` only if both conditions are `true`.
- **OR (`||`)** – Returns `true` if at least one condition is `true`.
- **NOT (`!`)** – Reverses the boolean value, returning `true` if the condition is `false`, and vice versa.

| Name | Symbol | Description                                                  |
| ---- | ------ | ------------------------------------------------------------ |
| AND  | `&&`   | Returns `true` **only if** both operands are `true`; otherwise returns `false`. |
| OR   | `||`   | Returns `true` if **at least one** operand is `true`; otherwise returns `false`. |
| NOT  | `!`    | Inverts the boolean value: returns `true` if the operand is `false`, and `false` if the operand is `true`. |

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
   - Only returns `true` if **both operands** are `true`.  

2. **OR (`||`)**  
   - Returns `true` if **at least one operand** is `true`.  

3. **NOT (`!`)**  
   - Flips the boolean value (`true` → `false`, `false` → `true`).  

4. **Short-Circuit Evaluation** (Java-specific):  
   - For `A && B`, if `A` is `false`, `B` is **not evaluated**.  
   - For `A || B`, if `A` is `true`, `B` is **not evaluated**.  

### **Understanding Logical Expressions in Java**

Logical expressions in Java are evaluated step by step, following **operator precedence** rules. Let's break down some examples:

#### **Example 1: `a > b || b == c`**

At first glance, it may seem like Java evaluates the entire expression at once, but it actually processes each part in sequence:

1. **Operator precedence:** Comparison operators (`>`, `==`) have higher precedence than logical operators (`||`).
2. **First evaluation:** `a > b` is computed. If `a` is greater than `b`, this results in `true`.
3. **Second evaluation:** `b == c` is checked, returning `false` if `b` is not equal to `c`.
4. **Final evaluation:** The logical OR (`||`) operator combines both results: `true || false` evaluates to `true`.

#### **Example 2: `b >= a || !(c == a)`**

1. **First execution:** `b >= a` is evaluated first, resulting in `true`.
2. **Second execution:** The **negation (`!`)** operator has high precedence, so Java first evaluates `c == a`. If `c` is not equal to `a`, this results in `false`.
3. **Negation applied:** `!(false)` simplifies to `true`.
4. **Final execution:** Combining `true || true` results in `true`.

#### **Example 3: `!(c <= a && c >= a)`**

Here, parentheses force Java to evaluate the **inner expressions first** following **BODMAS** rules:

1. **First execution:** `c <= a` is checked, returning `false`.
2. **Second execution:** `c >= a` is checked, returning `true`.
3. **Third execution:** `false && true` results in `false`.
4. **Final execution:** The negation operator (`!`) flips `false` to `true`.

