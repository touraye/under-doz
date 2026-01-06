# Expression And Statement

**Introduction (What Will Be Learned)**

* **Expressions**: Evaluate to values (arithmetic, boolean, method calls).
* **Statements**: Perform actions (variable declaration, loops, conditionals).
* **Syntax Rules**: Role of semicolons (`;`), braces (`{}`).
* **Interplay**: How expressions are embedded within statements (e.g., `if (x + 5 > 10)`).
* **Impact on Code**: Readability, performance, and error prevention.

Statements and expressions are fundamental to programming. Expressions compute values (e.g., `5 + 3`), while statements execute actions (e.g., `if (x > 0) { ... }`). Their distinction ensures proper syntax, program flow, and logic execution. Mastering these elements is essential for writing efficient, readable code and leveraging Java’s object-oriented capabilities.

### **1. Expressions**  
**Definition**
 An **expression** is a piece of code that is **evaluated by the program to produce a single value**, such as a number, string, boolean, or object.

**Key Characteristics**

- Produces exactly **one result** after evaluation.
- Can be used as part of a **larger statement**.
- Does **not** end with a semicolon (`;`) on its own.

#### **Categories of Expressions**  
| **Type**            | **Example**           | **Evaluates To**        |
| ------------------- | --------------------- | ----------------------- |
| **Arithmetic**      | `5 + 3 * 2`           | `11`                    |
| **Boolean**         | `age > 18`            | `true` or `false`       |
| **Method Call**     | `Math.sqrt(25)`       | `5.0`                   |
| **Assignment**      | `x = 10`              | `10` (value of `x`)     |
| **Object Creation** | `new String("Hello")` | Reference to the object |

#### **Examples**  
```java  
int result = 10 + 5; // Expression: `10 + 5` → evaluates to 15  
boolean isAdult = age >= 18; // Expression: `age >= 18` → evaluates to true/false  
String name = "Ahmed".toUpperCase(); // Expression: `"Ahmed".toUpperCase()` → "AHMED"  
```

**Exercise 1:**

* Develop a Java program that contains multiple expressions. For each expression, indicate the expression itself and specify the value produced after evaluation.

---

### **2. Statements**  
**Definition**
 A **statement** is a **complete unit of execution** in a program that performs an action. While statements may contain expressions, they **do not themselves evaluate to a value**.

**Key Characteristics**

- Represent a full instruction executed by the program.
- Typically **end with a semicolon (`;`)**.
- Are used to **declare variables**, **control program flow**, or **modify program state**.

#### **Categories of Statements**  
| **Type**         | **Example**                           | **Purpose**           |
| ---------------- | ------------------------------------- | --------------------- |
| **Declaration**  | `int x;`                              | Declares a variable   |
| **Assignment**   | `x = 5;`                              | Assigns a value       |
| **Control Flow** | `if (x > 0) { ... }`                  | Conditional execution |
|                  | `for (int i = 0; i < 5; i++) { ... }` | Looping               |
| **Method Call**  | `System.out.println("Hi");`           | Invokes a method      |
| **Return**       | `return x + 1;`                       | Exits a method        |

#### **Examples**  
```java  
int age = 25; // Declaration + assignment statement  
if (age >= 18) { // Control flow statement  
    System.out.println("Adult"); // Method call statement  
}  
```

**Exercise 2:**

* Create a statement that **declares and assigns** a value to a variable.
* Write a statement where the **right-hand side is an expression** whose result is assigned to a variable.
* Write a statement that **calls (invokes) a method** to perform an action.

---

### **Key Differences**  
| **Expressions**                         | **Statements**                       |
| --------------------------------------- | ------------------------------------ |
| Evaluates to a **value**.               | Performs an **action**.              |
| Can be nested inside other expressions. | Cannot be nested inside expressions. |
| Example: `x * 2`                        | Example: `x = x * 2;`                |

---

### **Why They Matter**  
1. **Expressions**: Handle computations and logic (e.g., calculations, comparisons).  
2. **Statements**: Structure the program’s flow (e.g., loops, conditionals, variable declarations).  

---

### **Example in Code**  
```java  
public class Example {  
    public static void main(String[] args) {  
        // Expression: `5 + 3` → evaluates to 8  
        int sum = 5 + 3;  // Statement: declaration + assignment  

        // Expression: `sum > 10` → evaluates to false  
        if (sum > 10) {    // Control flow statement  
            System.out.println("Large sum");  
        } else {  
            System.out.println("Small sum");  
        }  
    }  
}  
```

---

### **Summary**

Statements and expressions work synergistically: expressions generate values, while statements control execution. This relationship underpins Java’s logic flow, enabling dynamic computations and structured programs. Proficiency in both ensures code efficiency and clarity, critical for debugging and scaling applications while adhering to Java’s object-oriented principles.

------

### **Key Takeaways**

1. **Expressions ≠ Statements**: Values vs. actions.
2. **Control Flow**: Statements guide logic (loops, conditionals).
3. **Optimization**: Use primitives for speed, objects for flexibility.
4. **Real-World Application**: Embed expressions in statements for responsive logic.
5. **Syntax Mastery**: Avoid errors through correct usage of `;`, `{}`, and type safety.