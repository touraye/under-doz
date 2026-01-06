# Types of Languages

**Introduction (What Will Be Learned)**

* Definition of formal language
* Components of a language:
  * Token, Syntax, and Parsing
* Interaction flow
* Types of Programming Languages:
  * Lower level languages
  * higher level languages
  * Scripting Languages, 
  * Declarative languages
  * Domain-Specific Languages
* Different approaches to programming
  * Procedural programing 
  * Object Oriented programming
  * Functional programming 

Before we dive into the types of programming language it worth spending time understand what entails a formal language hence it is were our interest lies greatly. 

#### Formal Language

These are languages people have created for a specific purposes. These kind of languages are Mathematic language and Programming languages.

For our interest we will consider Programming languages. Formal Languages have these key components; **token**, **syntax**, and **parsing**.

Formal languages are structured systems used in computer science, particularly in programming languages and compilers, with three fundamental components: **tokens**, **syntax**, and **parsing**. Here's a concise breakdown:

### 1. **Token**

- **Definition**: The smallest meaningful units of a language, analogous to "words" in natural language.
- **Role**: Produced by a **lexer** (lexical analyzer), tokens categorize input characters into valid elements (e.g., keywords, literals, operators).
- **Examples**:
  - In `int x = 5;`, tokens are `int`, `x`, `=`, `5`, and `;`.
  - Errors at this stage (e.g., invalid symbols like `$#`) are **lexical errors**.

### 2. **Syntax**

- **Definition**: Rules governing how tokens are combined to form valid statements, akin to grammar in natural language.
- **Role**: Defined by a **grammar** (e.g., context-free grammar), syntax ensures correct structure (e.g., expression precedence, statement order).
- **Examples**:
  - A `for` loop must follow `for (init; condition; update) { ... }`.
  - Errors here (e.g., `if x = 5` missing a colon in Python) are **syntax errors**.

### 3. **Parsing**

- **Definition**: The process of analyzing token sequences to validate syntax and build a hierarchical structure (e.g., parse tree, abstract syntax tree).

- **Role**: Performed by a **parser**, which checks if tokens conform to grammar rules.

- **Goal**: Verify that the sequence of tokens adheres to the **grammar rules** of the language (i.e., the code is structurally valid).
  **Focus**: *Form* over *meaning*.

- **Methods**:

  - *Top-down* (e.g., recursive descent): Starts from the root (grammar start symbol) and expands rules.
  - *Bottom-up* (e.g., LR parsers): Builds structure from tokens upward.

- **Example**: Parsing `3 + 4 * 2` creates a tree reflecting operator precedence (`4*2` evaluated first).

  - **Valid**: `if (x > 5) { ... }` (correct syntax).
  - **Invalid**: `if x > 5 { ... }` (missing parentheses).
  - **Invalid**: `3 + * 4` (operator misuse

- #### **Limitations**:

  - A parser will accept syntactically valid code even if it’s **logically meaningless**.
    Example:

    ```java
    int x = "hello"; // Syntax is valid, but type mismatch (semantic error).  
    System.out.print(y);        // Syntax valid, but 'y' is undeclared (semantic error).  
    ```

  **Semantic Analysis**

- **Goal**: Verify the **logical correctness** of the code.
  **Focus**: *Meaning* and *context*.

  #### **Key Responsibilities**:

  - **Type Checking**: Ensure operations are valid for data types (e.g., no adding a string to an integer).

  - **Scope Resolution**: Confirm variables/functions are declared before use and accessible in their scope.

  - **Consistency Checks**: Validate function arguments, return types, and language-specific rules (e.g., `break` must be inside a loop).

  - **Symbol Tables**: Track identifiers (variables, functions) and their attributes (type, scope, memory location).

  - #### **Examples of Semantic Checks**:

    ```java
    // valid
    int x = 5;  
    x = x + 3; // Type-compatible assignment.  
    
    // invalid
    int x = "hello"; // Type mismatch (string assigned to int).  
    System.out.print(y);// Undeclared variable 'y'.  
    int a = 3;
     String b = "5";
     if (a > b) { }// Comparing int with string.
    ```


### Interaction Flow:

1. **Lexer** converts raw input (e.g., source code) into tokens.
2. **Parser** verifies token sequences against syntax rules and constructs a parse tree.
3. Subsequent phases (e.g., semantic analysis) handle meaning, context, and code generation.

### Key Distinctions:

- **Tokens vs. Syntax**: Tokens are valid individually; syntax governs their arrangement.
- **Parsing vs. Semantic Analysis**: Parsing checks structure; semantics check logic (e.g., variable declaration before use).

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

**Module Summary:**

1. Learn about low-level language such as machine and assembly language.  Machine language make usage of 0s and 1s, while assembly use `MOV` and `ADD`
2. Higher-level language is more user-friendly which are English like text, easily understandable by humans. Higher-level are broadly divided into 3 namely; procedural, object-oriented, and functional language.
3. Scripting language which are used for server-sides-scripting and system-scripting. These language are interpreted rather compiled
4. Declarative programming language is straight forwarded in a sense that you describe what you want rather how you want it. Example are logic basic, markup and database query language
5. Domain specific language are specific for certain task only like game development and data science