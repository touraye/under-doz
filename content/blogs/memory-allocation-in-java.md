# Memory Allocation In Java

Java uses two memory allocation system to store and hold value for a program. Putting that into context, Java is an object oriented programming language and thus behave differently.

 Java uses **two types of memory** for managing objects and variables:

1. **[Stack Memory]()** (Stores function calls and local variables)
2. **[Heap Memory]()** (Stores objects and instance variables)

Let’s break it down **step by step** to understand how Java allocates memory.

------

## **Stack Memory (Method Execution Memory)**

- Stores **method calls, local variables, and references to objects**.
- Follows the **LIFO (Last In, First Out)** principle.
- Memory is automatically **allocated and deallocated** when methods are called and return.

### **Example: Stack Memory in Action**

```java
public class StackExample {
    public static void main(String[] args) {
        int num = 10;  // Stored in stack
        display(num);
    }

    static void display(int value) {
        int square = value * value;  // Stored in stack
        System.out.println("Square: " + square);
    }
}
```

### **Step-by-Step Execution in Stack**

1. `main()` method starts execution.
   - `num = 10` is stored in **stack memory**.
2. `display(num)` is called.
   - `value = 10` (parameter) and `square = 100` are stored in **stack memory**.
3. `display()` method completes.
   - `value` and `square` are removed from the **stack** (popped).
4. `main()` method completes.
   - `num` is removed, and the stack is cleared.

### **Stack Memory Representation**

```
+-------------------+
| display()        |  <-- (Top of Stack)
|  value = 10      |
|  square = 100    |
+-------------------+
| main()          |
|  num = 10       |
+-------------------+
```

**Key Takeaways:**

- Each method gets its own **stack frame** (temporary memory space).
- When a method finishes, its frame is **removed** from the stack.
- Stack memory is **fast** and has **limited space** (can cause `StackOverflowError`).

------

## **Heap Memory (Object Storage)**

- Stores **objects and instance variables**.
- Objects remain in **heap memory** until they are **garbage collected**.
- Slower than stack memory but much **larger in size**.

### **Example: Heap Memory in Action**

```java
class Computer {
    String brand;  // Stored in heap
    int ram;       // Stored in heap
}

public class HeapExample {
    public static void main(String[] args) {
        Computer myComputer = new Computer();  // Stored in heap
        myComputer.brand = "Dell";  
        myComputer.ram = 16;
    }
}
```

### **Step-by-Step Execution in Heap**

1. `main()` method starts execution **(Stack Memory)**.
2. `Computer myComputer = new Computer();`
   - Creates an **object in heap memory**.
   - The **reference variable** `myComputer` is stored in **stack memory**, pointing to the object in the **heap**.
3. `myComputer.brand = "Dell";`
   - `"Dell"` is stored in the **heap** inside the object.
4. `myComputer.ram = 16;`
   - `16` is stored in the **heap** inside the object.

### **Heap and Stack Memory Representation**

```
Stack Memory:
+----------------------+
| main()              |
|  myComputer (ref)  | --> Points to Heap
+----------------------+

Heap Memory:
+--------------------------------+
| Object (myComputer)           |
|  brand → "Dell"               |
|  ram → 16                     |
+--------------------------------+
```

**Key Takeaways:**

- Objects are created in the **heap** and persist until garbage collection.
- The **reference variable** is stored in **stack memory**, pointing to the heap.
- Java automatically clears unused objects (Garbage Collection).

------

## **Stack vs Heap Memory (Comparison Table)**

| Feature               | **Stack Memory**              | **Heap Memory**             |
| --------------------- | ----------------------------- | --------------------------- |
| **Speed**             | Faster                        | Slower                      |
| **Storage**           | Method calls, local variables | Objects, instance variables |
| **Access**            | Direct (LIFO)                 | Indirect (via references)   |
| **Size**              | Limited                       | Large                       |
| **Memory Management** | Auto-managed (push/pop)       | Garbage Collection          |
| **Error Risk**        | StackOverflowError            | OutOfMemoryError            |

------

## ** Example with Both Stack and Heap**

```java
class Person {
    String name;  // Stored in heap
    int age;      // Stored in heap
}

public class MemoryExample {
    public static void main(String[] args) {
        int num = 5;  // Stored in stack

        Person person1 = new Person();  // Object stored in heap
        person1.name = "Alice";
        person1.age = 25;

        display(person1);
    }

    static void display(Person p) {
        System.out.println("Name: " + p.name + ", Age: " + p.age);
    }
}
```

### **Memory Breakdown**

#### **Step 1: `main()` starts (Stack Memory)**

```
Stack Memory:
+----------------+
| main()        |
|  num = 5      |
+----------------+
```

#### **Step 2: `new Person()` creates an object in Heap**

```
Heap Memory:
+-------------------+
| Object (person1) |
|  name → "Alice"  |
|  age → 25        |
+-------------------+

Stack Memory:
+-----------------------+
| main()               |
|  num = 5             |
|  person1 (ref)  ---> Heap Object
+-----------------------+
```

#### **Step 3: `display(person1)` is called**

```
Stack Memory:
+-----------------------+
| display()            |
|  p (ref)  ---> Heap Object
+-----------------------+
| main()               |
|  num = 5             |
|  person1 (ref)  ---> Heap Object
+-----------------------+
```

#### **Step 4: `display()` completes and stack is cleared**

```
Heap Memory:
+-------------------+
| Object (person1) |
|  name → "Alice"  |
|  age → 25        |
+-------------------+

Stack Memory:
+----------------+
| main()        |
|  num = 5      |
|  person1 (ref) ---> Heap Object
+----------------+
```

When `main()` finishes, **everything in stack is cleared**, but the object **remains in heap until garbage collection**.

------

## **Garbage Collection (Heap Cleanup)**

- Java automatically removes unused objects from the **heap**.
- Example:

```java
Person p1 = new Person();
p1 = new Person();  // Old object is now garbage (no reference)
```

- The **first object** created is **now unreachable** and will be removed by Java’s **Garbage Collector (GC)**.

------

## **Summary**

1. **Stack Memory**
   - Stores **method calls, local variables, and references**.
   - Memory is **automatically** managed (push/pop).
   - Small and **fast**, but can cause `StackOverflowError`.
2. **Heap Memory**
   - Stores **objects and instance variables**.
   - **Garbage Collection** removes unused objects.
   - Large but **slower** than the stack.
3. **Reference Variables**
   - Stored in the **stack**, but they point to **heap objects**.
4. **Garbage Collection**
   - **Unreachable objects** in heap are **automatically removed**.