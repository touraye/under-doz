# Types of Classes in Java

In Java, *classes* are the foundation of object-oriented programming. They define the structure and behavior of objects — the core building blocks of every Java program.
 However, not all classes serve the same purpose. Java provides different types of classes to help developers organize, reuse, and manage code efficiently.

This module introduces you to the **major types of classes** in Java, explaining how each type works, when to use them, and why they matter in real-world programming.

### **Topics Covered**

This module focuses on **seven key types of Java classes**:

1. **Concrete Classes** – The standard, instantiable classes used to create objects.
2. **Abstract Classes** – Blueprint classes that define shared structure and behavior for subclasses.
3. **Interface** – Contracts that define *what* methods must be implemented, not *how*.
4. **Final Classes** – Classes that cannot be extended, ensuring immutability or security.
5. **Static Nested Classes** – Classes defined within another class, used to group related logic.
6. **Non-Static (Inner) Classes** – Classes nested inside another class that can access its instance members.
7. **Enum Classes** – Special classes that represent a fixed set of named constants.

##  **1. Concrete Class**

### **Definition**

A **concrete class** is a standard class in Java that can be **instantiated directly** to create objects.
 It typically defines **complete implementations** for all its methods.

Concrete classes are the most common type — they form the backbone of most Java programs.

### **Example**

```java
// Concrete Class Example
public class Car {
    private String model;

    public Car(String model) {
        this.model = model;
    }

    public void startEngine() {
        System.out.println(model + " engine started.");
    }

    public static void main(String[] args) {
        Car car = new Car("Toyota");
        car.startEngine();
    }
}
```

 **Key Point:**
 Concrete classes can be **instantiated** and can contain **fields, constructors, and fully defined methods.**

##  **2. Abstract Class**

### **Definition**

An **abstract class** serves as a **blueprint** for other classes.
 It **cannot be instantiated** on its own and may include both **abstract methods** (without implementation) and **concrete methods** (with implementation).

Used when you want to **define a general concept** that subclasses must specialize.

### **Example**

```java
// Abstract Class Example
public abstract class Animal {
    abstract void makeSound(); // abstract method (no implementation)

    public void sleep() { // concrete method
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bark!");
    }

    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound();
        dog.sleep();
    }
}
```

**Key Point:**
 Abstract classes help in **partial abstraction** and **code reuse** through inheritance.

## **3. Interface**

### **Definition**

An **interface** defines a **contract** or **blueprint** that a class must follow.
 It contains **abstract methods** (implicitly `public` and `abstract`) and **constants**.
 Classes that implement an interface must **provide implementations** for all its methods.

Since Java 8, interfaces can also include **default** and **static** methods.

### **Example**

```java
// Interface Example
interface Playable {
    void play(); // abstract method
}

class Guitar implements Playable {
    @Override
    public void play() {
        System.out.println("Playing the guitar...");
    }

    public static void main(String[] args) {
        Playable instrument = new Guitar();
        instrument.play();
    }
}
```

**Key Point:**
 Interfaces support **multiple inheritance** and promote **loose coupling**.

## **4. Final Class**

### **Definition**

A **final class** cannot be **extended (inherited)** by other classes.
 It’s often used to **prevent modification** or **ensure immutability**, providing security and consistency.

### **Example**

```java
// Final Class Example
public final class Constants {
    public static final double PI = 3.14159;

    public static double circleArea(double radius) {
        return PI * radius * radius;
    }

    public static void main(String[] args) {
        System.out.println("Area: " + circleArea(5));
    }
}
```

**Key Point:**
 Final classes are **immutable**, **secure**, and **non-inheritable** — like Java’s built-in `String` class.

##  **5. Static Nested Class**

### **Definition**

A **static nested class** is a class defined **inside another class** and marked as `static`.
 It **does not depend** on an instance of the outer class and can **access only static members** of the outer class.

### **Example**

```java
// Static Nested Class Example
public class Outer {
    static int outerValue = 10;

    static class Nested {
        void display() {
            System.out.println("Outer Value: " + outerValue);
        }
    }

    public static void main(String[] args) {
        Outer.Nested nested = new Outer.Nested();
        nested.display();
    }
}
```

**Key Point:**
 Static nested classes help in **grouping related logic** and keeping code **organized** without needing an outer instance.

##  **6. Non-Static (Inner) Class**

### **Definition**

A **non-static inner class** is a class defined **inside another class** but **without the static keyword**.
 It can **access all members** (even private ones) of the outer class but **requires an instance** of the outer class to be created.

### **Example**

```java
// Non-Static Inner Class Example
public class Outer {
    private String message = "Hello from Outer!";

    class Inner {
        void showMessage() {
            System.out.println(message);
        }
    }

    public static void main(String[] args) {
        Outer outer = new Outer();
        Outer.Inner inner = outer.new Inner();
        inner.showMessage();
    }
}
```

**Key Point:**
 Inner classes are useful when one class is **closely associated** with another and needs **direct access** to its members.

## **7. Enum Class**

### **Definition**

An **enum (enumeration)** class defines a fixed set of **named constants**.
 Enums are **type-safe** and can include **fields, methods, and constructors**.

### **Example**

```java
// Enum Class Example
public enum Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY;

    public boolean isWeekend() {
        return this == SATURDAY || this == SUNDAY;
    }

    public static void main(String[] args) {
        for (Day day : Day.values()) {
            System.out.println(day + " is weekend? " + day.isWeekend());
        }
    }
}
```

 **Key Point:**
 Enums represent **constant sets of values** (like days, directions, or statuses) and enhance **readability** and **safety**.

### **Summary Table**

| Type                 | Can Instantiate?       | Can Inherit? | Common Use                      |
| -------------------- | ---------------------- | ------------ | ------------------------------- |
| **Concrete**         | Yes                    | Yes          | General-purpose class           |
| **Abstract**         | No                     | Yes          | Base blueprint class            |
| **Interface**        | No                     | Multiple     | Define contracts                |
| **Final**            | Yes                    | No           | Immutable/safe class            |
| **Static Nested**    | Yes                    | Yes          | Group related logic             |
| **Non-Static Inner** | (via outer)            | Yes          | Tight coupling with outer class |
| **Enum**             | (predefined constants) | No           | Represent fixed constant sets   |



