# Conditional Statements

Conditional statements allow a program to **make decisions** and execute different blocks of code based on whether a condition is `true` or `false`. They are fundamental for controlling program flow and making logical decisions.

Types of conditional statement:

1. `if` Statement
   1. `if and else`
   2. `if and else if`
   3. nested `if` statement
2. `switch` Statement

### **Key Differences Between `if-else` and `switch`**

| Feature         | `if-else` Statement                                          | `switch` Statement                                           |
| --------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Usage**       | Works with **boolean conditions** and complex expressions    | Works with **fixed values** (integers, characters, enums, strings) |
| **Flexibility** | Can evaluate **ranges** and **complex conditions**           | Can only check for **specific values**                       |
| **Execution**   | Evaluates **each condition sequentially** until a match is found | Jumps **directly** to the matching case                      |
| **Performance** | Slower if there are many conditions                          | Faster for many fixed values due to **direct lookup**        |

## `IF` Statement

An `if` statement is one of the fundamental control structures in Java. It allows the program to **execute a block of code only when a certain condition is met** (i.e., when the condition evaluates to `true`).

### **1 Condition of the `if` Statement**

The **condition** in an `if` statement is a Boolean expression—meaning it must return either `true` or `false`. The syntax is:

```java
if (condition) {
    // Code to execute if condition is true
}
```

- The **condition** inside the parentheses `( )` is evaluated first.
- If the condition is `true`, the code inside the **body** (inside `{}`) runs.
- If the condition is `false`, the body is **skipped** and execution moves to the next statement after the `if` block.

**Example:**

```java
int number = 10;

if (number > 5) { 
    System.out.println("The number is greater than 5");
}
// Output: The number is greater than 5
```

- The condition `number > 5` is `true`, so the body of the `if` statement executes.
- If `number` were `3`, the condition would be `false`, and nothing would be printed.

------

### **2 Body of the `if` Statement**

The **body** refers to the block of code inside `{}` that executes when the condition is true.

#### **Example with Multiple Statements**

```java
int temperature = 35;

if (temperature > 30) { 
    System.out.println("It's a hot day.");
    System.out.println("Drink plenty of water.");
}
// Output:
// It's a hot day.
// Drink plenty of water.
```

- Since `temperature > 30` is `true`, **both** statements inside the `{}` are executed.
- If `temperature` were `25`, nothing would be printed.

------

### **3 What Happens If We Omit `{}`?**

If you write an `if` statement **without curly braces `{}`**, only the **first statement** after `if` will be considered part of the condition.

#### **Example Without `{}`**

```java
int age = 20;

if (age >= 18) 
    System.out.println("You are an adult.");
    System.out.println("You can vote.");
```

**Output:**

```
You are an adult.
You can vote.
```

**What happened here?**

- Only `"You are an adult."` is inside the `if` block.
- `"You can vote."` **executes regardless of the condition** because it's outside the `if` statement.

#### **Correct Way (Using `{}`)**

```java
int age = 20;

if (age >= 18) {
    System.out.println("You are an adult.");
    System.out.println("You can vote.");
}
```

 Now both statements run **only if** `age >= 18`.

---

## **If-Else Statement**

An **if-else** statement is used when we want to execute **one block of code if a condition is true** and **another block if it is false**.

### **How It Works:**

1. The `if` condition is checked first.
2. If `true`, the `if` block executes.
3. If `false`, the `else` block executes.

#### **Example: Checking Age for Access**

```java
int age = 17;

if (age >= 18) {
    System.out.println("Access granted!");
} else {
    System.out.println("Access denied!");
}
// Output: Access denied!
```

- If `age` is `18` or more, "Access granted!" is printed.
- Otherwise, "Access denied!" is printed.

## **If, Else If, and Else Statement**

The **if-else if-else** structure is useful when checking **multiple conditions**. Instead of writing multiple separate `if` statements, we use **else if** to efficiently evaluate different conditions in sequence.

### **How It Works:**

1. The program evaluates the first condition inside the `if` statement.
2. If the first condition is **true**, the corresponding block executes, and the rest are ignored.
3. If the first condition is **false**, the program moves to the `else if` condition.
4. If the `else if` condition is **true**, that block executes, and the remaining conditions are ignored.
5. If none of the conditions are `true`, the **default `else` block** executes.

**Syntax:**

```java
if (condition1) {
    // Code executes if condition1 is true
} else if (condition2) {
    // Code executes if condition1 is false and condition2 is true
} else if (condition3) {
    // Code executes if previous conditions are false and condition3 is true
} else {
    // Code executes if none of the conditions above are true
}

```

### **Key Concepts:**

 **First Condition (`if`)** → Checked first. If `true`, executes, and the rest are ignored.
 **Additional Conditions (`else if`)** → Checked only if the previous conditions are `false`.
 **Default (`else`)** → Executes only if **none** of the above conditions are `true`.

---

## **Nested If Statement**

A **nested if statement** occurs when an `if` statement is placed **inside another `if` statement**. This allows us to create **hierarchical conditions**, where the **inner condition is only checked if the outer condition is true**.

------

### **How It Works:**

1. The **outer `if` statement** is evaluated first.
2. If the **outer condition is true**, the program moves to evaluate the **inner `if` statement**.
3. If the **inner condition is also true**, its block executes.
4. If the **outer condition is false**, the inner condition is **never checked**.

------

### **Syntax:**

```java
if (outerCondition) {
    // Executes if outerCondition is true
    if (innerCondition) {
        // Executes only if both outerCondition and innerCondition are true
    }
}
```

#### **Example: Checking Nested Conditions**
```java
boolean flag = false;
if (flag) {
    int num = 100;
    if (num > 100) {
        System.out.println("The number is greater than 100");
    } else {
        System.out.println("The number is not greater than 100");
    }
} else {
    System.out.println("Oops!");
}
// Output: Oops!
```
> **Note!** Nested `if` statements help handle **complex conditions**.

------

## **Switch Statement**

A **`switch` statement** is a control structure that allows a variable to be tested **against multiple cases**. It functions similarly to a series of `if-else` statements but is often **more readable and efficient** when dealing with multiple conditions.

### **How It Works:**

1. The `switch` statement **evaluates an expression** (a variable or value).
2. It **compares** the expression to each `case` value.
3. If a **matching case** is found, its corresponding block **executes**.
4. The **`break` statement** ensures that execution **exits the switch block** after a match is found.
5. If **no case matches**, the `default` block (if provided) **executes**.

------

### **Syntax:**

```java
switch (expression) {
    case value1:
        // Code to execute if expression == value1
        break;
    case value2:
        // Code to execute if expression == value2
        break;
    default:
        // Code to execute if no case matches
}
```

### **Important Notes:**

The `break` statement **prevents fall-through** (unintended execution of the next case).
 The `default` case acts as a **fallback** if no cases match.
 Switch works with:

- **`int`, `char`, `String`, `byte`, `short`, and `enum` types** (but not floating-point numbers like `float` or `double`).
   **Without `break`**, execution continues to the next case, which can be useful in some scenarios.

#### **Example: Evaluating an Integer**
```java
int num = 100;
switch (num) {
    case 100:
        System.out.println("A");
        break;
    case 20:
        System.out.println("B");
        break;
    default:
        System.out.println("None of the above!");
}
// Output: A
```
#### **Example: Evaluating a String**
```java
String userChoice = "A";
switch (userChoice) {
    case "A":
        System.out.println("Buy megabyte");
        break;
    case "B":
        System.out.println("Buy megabyte for others");
        break;
    default:
        System.out.println("No thanks");
}
// Output: Buy megabyte
```
> **Note!** If a `case` is missing a `break`, execution continues into the next case.

### **When to Use `switch` vs. `if-else`?**

**Use `switch`** when checking a **single variable** against **multiple known values**.
 **Use `if-else`** when conditions involve **ranges, logical expressions, or complex conditions**.

---

### Key Takeaways
- single `if` statement:
  -  **Use parentheses `( )`** to define conditions in an `if` statement.
  - **Use `{}` braces** to ensure multiple statements execute correctly.
  - The body **only executes when the condition is `true`**.
  - If there’s only **one statement**, `{}` is optional, but using them is a good practice.
  - `if` statements execute code **only when a condition is true**.

- `if-else` statement:
  - Use `if-else` when you need a **default action** if the condition is not met.
  - One of the two blocks **must execute**—either `if` or `else`.
  - Helps in **decision-making scenarios** where two possible outcomes exist.
  - `if-else` provides a **fallback mechanism**.
  - `if-else if-else` allows **multiple conditions to be checked**.

- `nested if` statements **evaluate conditions within conditions**.
  - **Nested `if` statements** allow for more specific condition checking.
  - The **inner `if` statement only runs** if the outer condition is **true**.
  - Be mindful of **proper indentation** to improve readability.
- `switch` statements provide a **structured way** to evaluate **fixed values**.
