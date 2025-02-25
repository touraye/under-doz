# Expression And Statement

Statements and expressions are fundamental to Java programming. Expressions compute values (e.g., `5 + 3`), while statements execute actions (e.g., `if (x > 0) { ... }`). Their distinction ensures proper syntax, program flow, and logic execution. Mastering these elements is essential for writing efficient, readable code and leveraging Java’s object-oriented capabilities.

### **What Should Be Learned**

1. **Expressions**: Evaluate to values (arithmetic, boolean, method calls).
2. **Statements**: Perform actions (variable declaration, loops, conditionals).
3. **Syntax Rules**: Role of semicolons (`;`), braces (`{}`).
4. **Interplay**: How expressions are embedded within statements (e.g., `if (x + 5 > 10)`).
5. **Impact on Code**: Readability, performance, and error prevention.

### **1. Expressions**  
**Definition**: A fragment of code that **evaluates to a single value** (e.g., a number, string, boolean, or object).  
**Key Traits**:  

- Can be part of a larger statement.  
- Do *not* end with a semicolon (`;`).  

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
int result = 10 + 5;      // Expression: `10 + 5` → evaluates to 15  
boolean isAdult = age >= 18; // Expression: `age >= 18` → evaluates to true/false  
String name = "Alice".toUpperCase(); // Expression: `"Alice".toUpperCase()` → "ALICE"  
```

---

### **2. Statements**  
**Definition**: A **complete unit of execution** that performs an action. Statements often contain expressions but do *not* evaluate to a value.  
**Key Traits**:  
- End with a semicolon (`;`).  
- Control program flow, declare variables, or modify state.  

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
int age = 25;                 // Declaration + assignment statement  
if (age >= 18) {              // Control flow statement  
    System.out.println("Adult"); // Method call statement  
}  
```

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