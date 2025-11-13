# Understanding Stack Memory in Java

When we run a Java program, memory is divided into two main areas: **Heap** and **Stack**. The **stack memory** is where Java keeps track of method calls and local variables. Think of it as a stack of plates — last plate in is the first one out (LIFO).

## How Stack Memory Works

Every time a method is called, a **stack frame** is created for it. This frame stores:

- The method’s local variables
- References to objects (not the objects themselves, those live in the Heap)
- The return address (where execution should continue after the method ends)

When the method finishes, its frame is popped off the stack.

------

### Example

```java
public class StackExample {
    public static void main(String[] args) {
        int x = 10;
        int y = 20;
        int result = add(x, y);
        System.out.println(result);
    }

    static int add(int a, int b) {
        int sum = a + b;
        return sum;
    }
}
```

### What Happens in Memory

**Step 1:**
 `main()` is called → Stack frame for `main` is created.

```
| main() frame |
```

**Step 2:**
 `add(10, 20)` is called → New frame added on top.

```
| add() frame  |
| main() frame |
```

**Step 3:**
 `add()` returns → Its frame is popped, control goes back to `main()`.

```
| main() frame |
```

**Step 4:**
 `main()` finishes → Stack becomes empty.

## Why It Matters

- **Fast execution**: Accessing local variables from the stack is quick.
- **Automatic cleanup**: Once a method ends, its stack frame disappears — no manual memory management needed.
- **Error handling**: If you exceed stack memory (e.g., with deep recursion), you’ll get a `StackOverflowError`.

 Next time you run a Java program, picture this stack of plates quietly managing your method calls behind the scenes.

