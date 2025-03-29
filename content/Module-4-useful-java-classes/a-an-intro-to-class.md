# Class

Before we begin exploring what is a **class** is worth clearing out the misconception about a typical **Java file**  and a **class**. A **typical Java class** has a `.java` extension and it serve as a container for Java codes, while a **class** is blueprint or a template to create objects. 

A **Java file** can hold multiple **Java classes** but only one class can be public which will bears the name of the **Java file**. 

## What is a Class

In Java, a **class** is a blueprint for creating objects. It defines **fields (variables)** to store data and **methods (functions)** to define behavior. A class encapsulates data and logic, supporting **object-oriented programming** principles like **encapsulation, inheritance, and polymorphism**.

**Example of a typical Java:**

```java
class Person {
    String name;
    int age;

    void displayInfo() {
        System.out.println("My name is " + name + " and I am " + age + " old");
    }
}
```
### **What is an Object in Java?**

An **object** is a **runtime instance** of a class. While a class is just a **blueprint**, an object is a **real entity** that exists in memory and can store data and perform actions.

------

### **Key Characteristics of an Object**

1. **State (Attributes/Fields)**
   - Objects store **data** in **instance variables**.
   - Example: A `Computer` object may have `brand` and `ram` as its attributes.
2. **Behavior (Methods/Functions)**
   - Objects have **methods** that define what they can do.
   - Example: A `Computer` object might have a method `displayInfo()` to print details.
3. **Identity (Memory Reference)**
   - Each object is stored at a **unique memory address**, making it distinct from other objects.

------

### **Creating an Object in Java**

To create an object, use the `new` keyword along with the class constructor.

#### **Example: Defining and Creating an Object**

```java
// Defining a class
class Computer {
    // Attributes (State)
    String brand;
    int ram;

    // Method (Behavior)
    void displayInfo() {
        System.out.println("Brand: " + brand + ", RAM: " + ram + "GB");
    }
}

// Main class to create an object
public class Main {
    public static void main(String[] args) {
        // Creating an object of the Computer class
        Computer myComputer = new Computer();

        // Assigning values to the object properties
        myComputer.brand = "Dell";
        myComputer.ram = 16;

        // Calling the method
        myComputer.displayInfo();
    }
}
```

### **Explanation:**

1. **Class Definition (`Computer`)**
   - Contains attributes (`brand`, `ram`) and a method (`displayInfo()`).
2. **Creating an Object (`myComputer`)**
   - `Computer myComputer = new Computer();` → Creates an instance of `Computer`.
3. **Assigning Values**
   - `myComputer.brand = "Dell";` → Stores `"Dell"` in the `brand` attribute.
   - `myComputer.ram = 16;` → Stores `16` in the `ram` attribute.
4. **Calling Methods**
   - `myComputer.displayInfo();` → Calls the method to print details.

------

### **Multiple Objects Example**

```java
public class Main {
    public static void main(String[] args) {
        // Creating multiple objects
        Computer laptop = new Computer();
        Computer desktop = new Computer();

        // Assigning values
        laptop.brand = "HP";
        laptop.ram = 8;

        desktop.brand = "Apple";
        desktop.ram = 32;

        // Calling methods
        laptop.displayInfo();
        desktop.displayInfo();
    }
}
```

### **Output:**

```
Brand: HP, RAM: 8GB
Brand: Apple, RAM: 32GB
```

------

### **Objects in Memory**

When you create an object using `new`, Java allocates memory for it on the [**heap**](), and a reference variable (like `myComputer`) stores its address.

#### **Memory Representation:**

```
Heap Memory:
+---------------------------+
| Object (myComputer)       |
| brand → "Dell"            |
| ram → 16                  |
+---------------------------+
```

The reference `myComputer` holds the **memory address** of the object.

We have covered **what a Java file is**, **what a Java class is**, and **their differences**. Additionally, we explored the properties and behaviors of a class, **including** what an **object** is, how to create an object, how to assign values to class properties, and how to invoke or call a function (behavior) using an object.

Since we mentioned that Java is a very rich language **that** comprises many built-in classes for **different purposes**, it is worth highlighting at least a few of these classes. Therefore, **we will briefly mention a few examples here**:

| Class Name            | Example                                                      | Class Destination      |
| --------------------- | ------------------------------------------------------------ | ---------------------- |
| Core Java Class       | `Object`, `String`, `Math`, `System`                         | `java.lang`            |
| Wrapper Classes       | `Integer`, `Double`, `Boolean`                               | `java.lang`            |
| Collections Framework | `ArrayList`, `Stack`, `LinkedList`                           | `java.util`            |
| I/O Classes           | `Scanner`, `File`, `FileReader`, `FileWriter`                | `java.io, java.nio`    |
| Concurrency           | `ExecutorService`, `ThreadPoolExecutor`                      | `java.util.concurrent` |
| Networking            | `URL`, `Socket`, `ServerSocket`, `HttpURLConnection`         | `java.net`             |
| JDBC ()               | `Connection`, `Statement`, `PreparedStatement`, `ResultSet`, `DriverManager` | `java.sql`             |
| Date and Time         | `LocalDate`, `LocalTime`, `LocalDateTime`                    | `java.time`            |
|                       |                                                              |                        |

**The above-mentioned** are examples of **some classes Java offers**, their purposes, and the packages they **reside in**. Moving **forward to other modules**, we will **begin** using **some of these classes** in our programs, reusing them **rather than** creating our own **from scratch** – **in other words**, reusing the wheel **instead of** reinventing it.

**Important note:** Always ensure you **understand** the purpose of each class you use, **its name**, key methods, and their **return types**.