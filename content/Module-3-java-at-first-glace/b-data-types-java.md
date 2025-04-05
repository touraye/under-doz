# Data Types In Java

In previous lessons, we explored [variables](https://github.com/touraye/under-doz/blob/main/content/Module-2-introduction-to-programming/c-getting-into-programming.md#the-variable-concept), including the various data types programs can handle, such as numeric values, textual content, and boolean (true/false) values. We briefly covered how programs interact with these foundational data types. Now, let’s delve into Java’s specific data types, which include primitive types and object-oriented structures.

**What are Data Types in Java**

Here's a structured explanation of **data types in Java**:

---

### **Data Types in Java**  
**Data types** define the type and size of values a variable can hold. They ensure **type safety** (preventing invalid operations) and determine how data is stored in memory. Java has two categories:  

---

### **1. Primitive Data Types**  
Predefined, non-object types that store raw values directly in memory.  

| **Type**  | **Size** | **Description**                 | **Example**                         |
| --------- | -------- | ------------------------------- | ----------------------------------- |
| `byte`    | 1 byte   | 8-bit integer                   | `byte age = 25;`                    |
| `short`   | 2 bytes  | 16-bit integer                  | `short temp = -200;`                |
| `int`     | 4 bytes  | 32-bit integer                  | `int count = 1000;`                 |
| `long`    | 8 bytes  | 64-bit integer                  | `long population = 8_000_000_000L;` |
| `float`   | 4 bytes  | 32-bit floating-point           | `float pi = 3.14f;`                 |
| `double`  | 8 bytes  | 64-bit floating-point (default) | `double salary = 4500.50;`          |
| `char`    | 2 bytes  | Single Unicode character        | `char grade = 'A';`                 |
| `boolean` | ~1 bit   | `true` or `false`               | `boolean isActive = true;`          |

#### **Key Notes**:  
- **Default Values** (for instance variables):  
  - Numeric types: `0`  
  - `boolean`: `false`  
  - `char`: `'\u0000'` (null character).  
- **Literals**: Suffixes like `L` (long), `f` (float), or `d` (double) specify types.  

---

### **2. Reference Data Types**  
Hold references (memory addresses) to dynamically created objects (instances of classes).  

| **Type**       | **Description**                   | **Example**                              |
| -------------- | --------------------------------- | ---------------------------------------- |
| `Class/Object` | User-defined or library classes   | `String name = "Alice";`                 |
| `Array`        | Fixed-size collection of elements | `int[] numbers = {1, 2, 3};`             |
| `Interface`    | Abstract contracts for classes    | `List<String> list = new ArrayList<>();` |

#### **Key Notes**:  
- **Default Value**: `null` (no object reference).  
- **Memory Allocation**: Stored in the **heap** (unlike primitives in the stack).  

---

### **Example Code**  
```java  
public class DataTypesExample {  
    public static void main(String[] args) {  
        // Primitive Types  
        int age = 30;  
        double price = 19.99;  
        char symbol = '$';  
        boolean isLoggedIn = false;  

        // Reference Types  
        String message = "Hello, Java!";  
        int[] scores = {90, 85, 77};  
    }  
}  
```

---

### **Key Differences**  
| **Primitive**                       | **Reference**                           |
| ----------------------------------- | --------------------------------------- |
| Stored in **stack** memory.         | Stored in **heap** memory.              |
| Fixed size (e.g., `int` = 4 bytes). | Size varies (depends on object).        |
| Faster access.                      | Slower (indirect access via reference). |
| No methods; only data.              | Can have methods and fields.            |

---

### **Why Data Types Matter**  
1. **Memory Efficiency**: Allocates the right amount of memory (e.g., `byte` vs. `int`).  
2. **Type Safety**: Prevents invalid operations (e.g., `int + String` is disallowed).  
3. **Performance**: Primitives are faster for calculations.  

---

### **Special Cases**  
- **Autoboxing/Unboxing**: Automatic conversion between primitives and their **wrapper classes** (e.g., `int` ↔ `Integer`).  
  ```java  
  Integer num = 10;  // Autoboxing (int → Integer)  
  int value = num;   // Unboxing (Integer → int)  
  ```
- **Strings**: Technically reference types but often treated as primitives in syntax.  

[Next lesson](https://github.com/touraye/under-doz/edit/main/content/Module-3-java-at-first-glace/c-expression-and-statment.md)

[Previous lesson](https://github.com/touraye/under-doz/edit/main/content/Module-3-java-at-first-glace/a-basic-building-block-of-java-program.md)
