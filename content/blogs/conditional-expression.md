### **Conditional Expressions in Programming**

A **conditional expression** is an expression that evaluates to either **true** or **false**, controlling the flow of a program. These expressions are used in decision-making structures like `if-else`, `switch-case`, and loops (`while`, `for`).

Any expression that evaluate to either `true` or `false` is said to be a **conditional expression**. From the beginning of program you most have came across `Boolean` value.   

### **Types of Conditional Expressions**

1. **Comparison Expressions**

   - Use **comparison operators** to compare values.

   - Example (Java):

     ```java
     int a = 10, b = 20;
     boolean result = a < b; // true
     ```

2. **Logical Expressions**

   - Combine multiple conditions using **logical operators** (`&&`, `||`, `!`).

   - Example:

     ```java
     int age = 25;
     boolean isAdult = age >= 18 && age < 60; // true
     ```

3. **Ternary Expressions (Conditional Operator)**

   - Shortens `if-else` into a single line.

   - Example:

     ```java
     int x = 10, y = 5;
     int min = (x < y) ? x : y; // min = 5
     ```

4. **Boolean Function Calls**

   - Conditions can be results of method calls.

   - Example:

     ```java
     if (isValidUser(username)) {
         System.out.println("Access granted");
     }
     ```

Conditional expressions enable **dynamic decision-making** in programs, making them responsive to varying inputs.



A **decision** in programming is made based on **conditional expressions** that evaluate to either **true or false** (Boolean logic). These conditions typically involve:

1. **Comparison Operators** (`==, !=, >, <, >=, <=`) – Used to compare values.
2. **Logical Operators** (`&&, ||, !`) – Combine multiple conditions.
3. **Control Structures** (`if-else, switch-case, ternary operator`) – Determine which code executes based on conditions.

A decision occurs when a program **evaluates a condition** and chooses between different execution paths, ensuring **dynamic and responsive behavior**.