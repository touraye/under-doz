### **Types of Programming Languages**

Programming languages can be categorized based on their purpose, execution style, and abstraction level. Here are the main types:

#### **1. Low-Level Languages**

These languages are closer to machine code and provide minimal abstraction.

- **Machine Language** – The most basic form of programming, using binary (0s and 1s) directly understood by the CPU.
- **Assembly Language** – Uses mnemonic codes (e.g., `MOV`, `ADD`) instead of binary, requiring an assembler for translation.

#### **2. High-Level Languages**

These languages are more human-readable and require translation (via a compiler or interpreter) into machine code.

- **Procedural Languages** – Follow a step-by-step execution approach (e.g., C, Pascal).
- **Object-Oriented Languages (OOP)** – Use objects and classes to structure programs (e.g., Java, C++, Python).
- **Functional Languages** – Emphasize mathematical functions and immutable data (e.g., Haskell, Lisp).

#### **3. Scripting Languages**

Designed for automating tasks, often interpreted rather than compiled.

- **Server-Side Scripting** – Used for web applications (e.g., JavaScript, PHP, Python).
- **System Scripting** – Used for automating OS tasks (e.g., Bash, PowerShell).

#### **4. Declarative Languages**

Focus on describing what should be done rather than how to do it.

- **Logic-Based** – Uses rules and facts for computation (e.g., Prolog).
- **Markup Languages** – Define data structures and presentation (e.g., HTML, XML).
- **Database Query Languages** – Used to interact with databases (e.g., SQL).

#### **5. Domain-Specific Languages (DSLs)**

Tailored for specific tasks rather than general-purpose programming.

- **Game Development** – (e.g., GDScript for Godot).
- **Data Science & Statistics** – (e.g., R, MATLAB).

Each type of programming language serves different needs, and the choice depends on the application domain and execution requirements.



Let's dive deeper into **Procedural, Object-Oriented, and Functional Programming**, their principles, characteristics, and examples.

------

## **1. Procedural Programming**

### **Definition**

Procedural programming is a programming paradigm that follows a step-by-step approach, breaking down a problem into a series of procedures (also called functions or subroutines). It focuses on **code reusability, sequence, selection, and iteration** to structure programs.

### **Characteristics**

✔ **Linear Execution** – Programs execute in a sequential manner.
 ✔ **Functions/Procedures** – Code is divided into reusable functions to improve modularity.
 ✔ **Global & Local Variables** – Variables can be accessed within functions or globally.
 ✔ **Control Structures** – Uses loops (`for`, `while`) and conditionals (`if-else`).

### **Example (C Language - Procedural Style)**

```c
#include <stdio.h>

// Function (Procedure)
void greet() {
    printf("Hello, World!\n");
}

int main() {
    greet(); // Function Call
    return 0;
}
```

### **Pros & Cons**

✅ Simple and easy to understand.
 ✅ Good for small applications.
 ❌ Hard to manage large projects due to lack of data encapsulation.
 ❌ Code duplication is common.

### **Common Procedural Languages**

- C
- Pascal
- FORTRAN
- BASIC

------

## **2. Object-Oriented Programming (OOP)**

### **Definition**

Object-Oriented Programming is a paradigm based on **objects** (instances of classes) that encapsulate data (attributes) and behaviors (methods). It promotes **modularity, reusability, and abstraction** through key principles like **encapsulation, inheritance, and polymorphism**.

### **Key Principles**

✔ **Encapsulation** – Data is hidden within objects and accessed via methods.
 ✔ **Abstraction** – Hides complex details and exposes only necessary functionality.
 ✔ **Inheritance** – One class can inherit attributes and behaviors from another.
 ✔ **Polymorphism** – Allows the same function to behave differently in different contexts.

### **Example (Java - OOP Style)**

```java
// Class Definition
class Animal {
    String name;

    void speak() {
        System.out.println(name + " makes a sound.");
    }
}

// Subclass (Inheritance)
class Dog extends Animal {
    void speak() {
        System.out.println(name + " barks.");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.name = "Buddy";
        myDog.speak(); // Output: Buddy barks.
    }
}
```

### **Pros & Cons**

✅ Promotes **code reuse** through **inheritance**.
 ✅ More scalable and manageable for large applications.
 ❌ Can be **complex** to implement and may have **higher memory usage**.

### **Common OOP Languages**

- Java
- C++
- Python
- C#
- Ruby

------

## **3. Functional Programming (FP)**

### **Definition**

Functional programming is a paradigm where computation is treated as **evaluating mathematical functions**. It avoids **changing state and mutable data**, focusing on **pure functions and immutability**.

### **Key Principles**

✔ **Pure Functions** – Functions always return the same result for the same input and have no side effects.
 ✔ **Immutability** – Data cannot be modified once created.
 ✔ **Higher-Order Functions** – Functions can take other functions as arguments or return functions.
 ✔ **Recursion** – Loops are often replaced by recursive functions.

### **Example (Python - Functional Style)**

```python
# Pure Function
def square(x):
    return x * x

# Higher-Order Function
def apply_function(func, values):
    return [func(val) for val in values]

numbers = [1, 2, 3, 4, 5]
squared_numbers = apply_function(square, numbers)

print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

### **Pros & Cons**

✅ Reduces **side effects** and **bugs** due to immutability.
 ✅ Code is **easier to test and debug**.
 ❌ Can be **harder to understand** for those used to imperative programming.
 ❌ May have **performance issues** if not optimized properly.

### **Common Functional Languages**

- Haskell
- Lisp
- Clojure
- Scala
- Elixir

------

## **Summary Table**

| Paradigm       | Key Feature                       | Example Languages    | Pros                          | Cons                             |
| -------------- | --------------------------------- | -------------------- | ----------------------------- | -------------------------------- |
| **Procedural** | Step-by-step execution, functions | C, Pascal, FORTRAN   | Simple, easy to debug         | Hard to scale for large projects |
| **OOP**        | Objects, classes, encapsulation   | Java, C++, Python    | Modular, reusable, scalable   | Complex for small projects       |
| **Functional** | Pure functions, immutability      | Haskell, Lisp, Scala | No side effects, easy to test | Harder to learn, may be slower   |

Each paradigm has its strengths and is best suited for different types of applications. Some modern languages, like Python and JavaScript, **support multiple paradigms**, allowing a mix of procedural, object-oriented, and functional styles.