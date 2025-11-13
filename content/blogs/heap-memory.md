

# Understanding Heap Memory in Java

In Java, memory is divided into two main areas: **Stack** and **Heap**. While the stack handles method calls and local variables, the **heap memory** is where Java stores **objects**.

Think of it as a big storage room where all your created objects live until they are no longer needed.

## How Heap Memory Works

- When you use `new` to create an object, it is placed in the heap.
- Multiple references (variables) can point to the same object in the heap.
- When an object is no longer referenced, the **Garbage Collector (GC)** reclaims it, freeing up memory automatically.

### Example

```java
public class HeapExample {
    public static void main(String[] args) {
        Person p1 = new Person("Alice");
        Person p2 = new Person("Bob");

        p1 = null; // Alice is now eligible for GC
        System.out.println(p2.getName());
    }
}

class Person {
    String name;
    Person(String name) {
        this.name = name;
    }
    String getName() {
        return name;
    }
}
```

### What Happens in Memory

**Step 1:**
 `main()` runs, and objects `p1` and `p2` are created on the heap.

```
Heap: [Person("Alice"), Person("Bob")]
```

**Step 2:**
 `p1 = null;` → the reference to Alice is gone. Garbage Collector can remove it.

```
Heap: [Person("Bob")]
```

## Why It Matters

- **Dynamic memory allocation**: Objects are created at runtime.
- **Larger pool**: Heap can store large and complex objects compared to the stack.
- **Automatic cleanup**: The Garbage Collector removes unused objects for you.

The heap is your app’s storage room, keeping objects alive as long as they’re needed, then quietly cleaning them up.

