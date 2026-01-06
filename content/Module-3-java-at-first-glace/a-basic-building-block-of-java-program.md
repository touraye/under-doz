# Basic Building Of Java Application

**Introduction (What Will Be Learned)**

* **Essential Components:**
  * Class Declaration
  * Main Method
  * Syntax and Compilation Unit
* **Common Additional Components:**
  * Package Declaration
  * Import Statements
  * Method and Fields
  * Access Modifiers

The foundational components of a Java application are the structural and syntactic elements required for a valid, executable program. Every Java program adheres to object-oriented principles and must include at minimum: a class declaration encapsulating program logic, a `main` method as the JVM entry point (with signature `public static void main(String[] args)`), and syntactically correct statements within a compilation unit. Optional but common elements include package declarations, import statements, and method/field definitions, all governed by Java’s strict syntax rules and type system.

### **Essential Components**  

#### 1. **Class Declaration**  

- **Purpose**: Defines a blueprint for objects and encapsulates data/behavior. Java is strictly object-oriented, so all code resides within a class.  

- **Syntax**:  

  ```java  
  public class MyClass {  // Class name must match the .java filename if declared 'public'
      // Fields, methods, and constructors go here
  }
  ```

- **Why Required**: The JVM cannot execute code outside a class.  

---

#### 2. **`main` Method**  

- **Purpose**: Entry point for the JVM to start program execution.  

- **Syntax**:  

  ```java  
  public static void main(String[] args) {  
      // Code to execute  
  }
  ```

- **Key Modifiers**:  

  - `public`: Accessible to the JVM.  
  - `static`: No class instance needed to invoke the method.  
  - `void`: No return value.  
  - `String[] args`: Command-line arguments.  

---

#### 3. **Compilation Unit & Syntax**  

- **Compilation Unit**: A `.java` file containing valid Java code.  

- **Syntax Rules**:  

  - Statements end with `;`.  
  - Blocks (e.g., classes, methods) enclosed in `{}`.  
  - Case-sensitive (e.g., `Main` ≠ `main`).  

- **Minimal Example**:  

  ```java  
  public class HelloWorld {  
      public static void main(String[] args) {  
          System.out.println("Hello, World!");  
      }  
  }
  ```

---

### **Common Additional Components**  

#### 4. **Package Declaration**  

- **Purpose**: Organizes classes into namespaces to avoid naming conflicts.  

- **Syntax**:  

  ```java  
  package com.example.myapp;  // Must be the first line in the file
  ```

- **Usage**: Classes in `com.example.myapp` are stored in the directory `com/example/myapp`.  

---

#### 5. **Import Statements**  

- **Purpose**: Includes classes/interfaces from other packages.  

- **Syntax**:  

  ```java  
  import java.util.ArrayList;  // Imports ArrayList
  import java.util.*;          // Imports all classes in java.util
  ```

- **Default Imports**: `java.lang` (e.g., `String`, `System`) is automatically imported.  

---

#### 6. **Methods and Fields**  

- **Fields**: Variables that define the state of a class/object.  

  ```java  
  public class Calculator {  
      private int result;  // Instance field  
      public static final double PI = 3.14;  // Static/constant field  
  }
  ```

- **Methods**: Functions defining behavior.  

  ```java  
  public int add(int a, int b) {  
      return a + b;  
  }
  ```

---

#### 7. **Access Modifiers**  

- **Purpose**: Control visibility/encapsulation.  

  - `public`: Accessible from any class.  
  - `private`: Accessible only within the declaring class.  
  - `protected`: Accessible within the package and subclasses.  
  - Default (no modifier): Package-private.  

- **Example**:  

  ```java  
  public class BankAccount {  
      private double balance;  // Encapsulated field  
      public void deposit(double amount) { ... }  
  }
  ```

---

### **Optional but Common**  

#### 8. **Constructors**  

- **Purpose**: Initialize objects during instantiation.  

- **Syntax**:  

  ```java  
  public class Student {  
      public Student(String name) {  // Constructor  
          // Initialization logic  
      }  
  }
  ```

---

## Keyword

A reserved word in a programming language with a predefined, fixed meaning. Keywords define syntax rules (e.g., `if`, `class`, `return`) and cannot be used as identifiers (e.g., variable names). For example:  

```java  
int public = 5; // Error: 'public' is a keyword  
```
**Role**: Directs the compiler/interpreter to perform specific operations (e.g., control flow, data typing).

Below is a **comprehensive list of Java keywords (reserved words)**. These words have predefined meanings in the Java language and **cannot be used as identifiers** (e.g., variable names, class names).

---

### **Java Keywords (as of Java 17)**  
| **Category**           | **Keywords**                                                 |
| ---------------------- | ------------------------------------------------------------ |
| **Data Types**         | `byte`, `short`, `int`, `long`, `float`, `double`, `char`, `boolean` |
| **Flow Control**       | `if`, `else`, `switch`, `case`, `default`, `for`, `while`, `do`, `break`, `continue`, `return` |
| **Class/Interface**    | `class`, `interface`, `enum`, `extends`, `implements`, `new`, `this`, `super`, `package`, `import` |
| **Modifiers**          | `public`, `private`, `protected`, `static`, `final`, `abstract`, `synchronized`, `transient`, `volatile`, `native`, `strictfp` |
| **Exception Handling** | `try`, `catch`, `finally`, `throw`, `throws`, `assert`       |
| **Multi-threading**    | `synchronized`, `volatile`                                   |
| **Miscellaneous**      | `void`, `instanceof`, `const` (unused), `goto` (unused), `var` (Java 10+), `record` (Java 16+), `sealed` (Java 17+), `permits`, `non-sealed` |

---

### **Reserved Literals (Not Keywords, but Restricted)**  
- `true`, `false`: Boolean literals.  
- `null`: Represents a null reference.  

---

### **Example of Invalid Usage**  
```java  
int class = 5; // Error: 'class' is a keyword and cannot be a variable name  
```

---

### **Full List (Alphabetical Order)**  
```  java
abstract, assert, boolean, break, byte, case, catch, char, class, const, continue, default, do, double, else, enum,  
exports, extends, final, finally, float, for, goto, if, implements, import, instanceof, int, interface, long, module,  
native, new, non-sealed, open, opens, package, permits, private, protected, public, record, requires, return, sealed,  
short, static, strictfp, super, switch, synchronized, this, throw, throws, transient, transitive, try, var, void,  
volatile, while, with, yield  
```

[Next lesson](https://github.com/touraye/under-doz/blob/main/102-looking-into-java/L-103-data-types.md)

[Previous lesson](https://github.com/touraye/under-doz/blob/main/102-looking-into-java/L-101-java-at-first-look.md)