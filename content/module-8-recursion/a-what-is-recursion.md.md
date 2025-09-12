# What is Recursion?

Have you ever wanted to repeat an action in code, like printing numbers from 1 to 5? Sure, you could write multiple print statements or call different functions for each number, but that gets repetitive quickly.

This is where **recursion** comes in.

## The Idea Behind Recursion

Recursion is when a function **calls itself** to solve a smaller piece of a problem, until eventually reaching a point where no further calls are needed.

Think of it like standing in front of two mirrors facing each other: your reflection keeps repeating, smaller and smaller, until it fades away. That “fade away” is what we call the **base case** in recursion. Without it, the reflections (or function calls) would go on forever!

## A Non-Recursive Approach

Before we dive into recursion, let’s see how we might try solving a simple problem without it. Suppose we want to print the numbers 1 through 5.

One way is to create multiple functions and chain them together:

```java
public static void main(String[] args) {
    print1(1);
}

static void print1(int n) {
    System.out.println(n);
    print2(2);
}

static void print2(int n) {
    System.out.println(n);
    print3(3);
}

static void print3(int n) {
    System.out.println(n);
    print4(4);
}

static void print4(int n) {
    System.out.println(n);
    print5(5);
}

static void print5(int n) {
    System.out.println(n);
}

// Output: 1 2 3 4 5
```

This works, but it’s bulky and impractical. We had to create **five separate functions** just to print five numbers. Imagine printing up to 100 — it would be a nightmare!

## Debugging the Non-Recursive Version

If you debug this program (say, starting with `print1(1)` inside `main()`), you’ll notice something interesting about the **call stack**:

1. The **first function** registered is `print1`.
2. The **last function** registered is `print5`.

Each new function call gets added on top of the stack until the program starts returning back down; from `print5` all the way to `print1`. This is exactly how recursion behaves under the hood.

## Enter Recursion

Recursion allows us to refactor the above into a single, elegant function:

```java
static void print(int n) {
    if (n > 5) {
        return; // base case
    }
    System.out.println(n);
    print(n + 1); // recursive call
}
```

**Output:**

```
1
2
3
4
5
```

### The Key Ingredients of Recursion

1. **Recursive call** → The function calls itself to keep the process going.
2. **Base case** → A condition that stops the recursion, preventing infinite loops and `StackOverflowError`.

Without a base case:

```java
static void print(int n) {
    System.out.println(n);
    print(n + 1); // no stopping condition!
}
```

This will eventually crash with a `StackOverflowError` because the stack memory fills up. The function `print(n + 1)` forever calls itself and each calls takes up a memory.

With a base case:

```java
static void print(int n) {
    if (n > 5) return; // stop when n > 5
    System.out.println(n);
    print(n + 1);
}
```

## Why Recursion Matters

- It help solve bigger problems in a simple way
- Complex problems a brake down into small chunks
- You can convert recursion solution in iterations which require no functions call.
- With recursion your code become readable and easy to follow through

Note! Recursion is a powerful tool, but always remember the **base case**. Without it, you’ll end up with infinite calls and eventually crash your program with a `StackOverflowError`.

Recursions solution can also be solve with iterations, vise versa. Let's refactor the number counter with  a iteration. With iteration no function calls are required. And, putting the issue of memory into contest recursion take more memory and iteration. Each function call take a memory in the stack memory. ****

### Visualize Recursion

Visualizing a recursion is yet another important skill as it is to code in a recursive problem. One important concept to carry is the stack memory: draw a **call stack** diagram, place functions into the call stack in a hierarchical order. Remember the call was once empty, it will be fill with functions, and off course will be empty again. So therefore, depicting how functions calls are removed from the stack is as equally as important. 



With our code example: `print1 → print2 → print3 → print4 → print5` is a **perfect way to see the call stack in action**.
 Although it isn’t recursion in the strict sense (since each function calls a different one, rather than itself), it **demonstrates exactly how stack memory works**.

------

## 🔹 What is the Call Stack?

Think of the **Call Stack** like a pile of plates:

- **Push** → When a function is called, a new “plate” (called a **stack frame**) is added on top.
- **Top of the Stack** → The CPU always executes the function on top. Functions below are paused.
- **Pop** → When a function finishes, its plate is removed, and control goes back to the one just below.

This is called **LIFO** (Last-In, First-Out).

------

## 🔹 Execution Flow with Example

We’ll trace the program step by step, showing both the **stack memory** and the  **console output**.

Step 1: Program Starts – `main` is called

The JVM begins by calling `main()`.

```bash
					  +-------------+
                      |    main()   |  <-- TOP
                      +-------------+
                     THE CALL STACK
```

| Console Output | Call Stack         |
| -------------- | ------------------ |
| (empty)        | `+-------------+`` |

------

### Step 2: `main` calls `print1(1)`

A new frame for `print1` is pushed.

```bash
        PUSH --->     +-------------+
                      | print1(n=1) |  <-- TOP
                      +-------------+
                      |    main()   |
                      +-------------+
                     THE CALL STACK
```

| Console Output | Call Stack         |
| -------------- | ------------------ |
| (empty)        | `+-------------+`` |

------

### Step 3: `print1` runs → prints `1` and calls `print2(2)`

```bash
        PUSH --->     +-------------+
                      | print2(n=2) |  <-- TOP
                      +-------------+
                      | print1(n=1) |
                      +-------------+
                      |    main()   |
                      +-------------+
                     THE CALL STACK
```

| Console Output | Call Stack         |
| -------------- | ------------------ |
| `1`            | `+-------------+`` |

------

### Step 4: `print2` runs → prints `2` and calls `print3(3)`

```bash
        PUSH --->     +-------------+
                      | print2(n=2) |  <-- TOP
                      +-------------+
                      | print1(n=1) |
                      +-------------+
                      |    main()   |
                      +-------------+
                     THE CALL STACK
```

| Console Output | Call Stack         |
| -------------- | ------------------ |
| `1``2`         | `+-------------+`` |

------

### Step 5: `print3` runs → prints `3` and calls `print4(4)`

```bash
        PUSH --->     +-------------+
                      | print3(n=3) |  <-- TOP
                      +-------------+
                      | print2(n=2) |
                      +-------------+
                      | print1(n=1) |
                      +-------------+
                      |    main()   |
                      +-------------+
                     THE CALL STACK
```

| Console Output | Call Stack         |
| -------------- | ------------------ |
| `1``2``3`      | `+-------------+`` |

------

### Step 6: `print4` runs → prints `4` and calls `print5(5)`

```bash
        PUSH --->     +-------------+
                      | print4(n=4) |  <-- TOP
                      +-------------+
                      | print3(n=3) |
                      +-------------+
                      | print2(n=2) |
                      +-------------+
                      | print1(n=1) |
                      +-------------+
                      |    main()   |
                      +-------------+
                     THE CALL STACK
```

| Console Output | Call Stack         |
| -------------- | ------------------ |
| `1``2``3``4`   | `+-------------+`` |

------

## 🔹 Phase 2: Unwinding the Stack (Popping)

Now that the deepest call `print5` has been reached, the stack begins to **unwind**.

```bash
        PUSH --->     +-------------+
                      | print5(n=5) |  <-- TOP
                      +-------------+
                      | print4(n=4) |
                      +-------------+
                      | print3(n=3) |
                      +-------------+
                      | print2(n=2) |
                      +-------------+
                      | print1(n=1) |
                      +-------------+
                      |    main()   |
                      +-------------+
                     THE CALL STACK
```

------

### Step 7: `print5` runs → prints `5` and finishes

`print5`’s frame is popped off.

```bash
        POP  <---     +-------------+
                      | print5(n=5) |  <-- (This frame is removed)
                      +-------------+
                      | print4(n=4) |  <-- NEW TOP
                      +-------------+
                      | print3(n=3) |
                      |    ...      |
                      +-------------+
                     THE CALL STACK
```

| Console Output  | Call Stack         |
| --------------- | ------------------ |
| `1``2``3``4``5` | `+-------------+`` |

------

### Step 8–10: `print4`, `print3`, `print2`, `print1` finish in order

Each function ends and its frame is popped, one by one.

```bash
        POP  <---     +-------------+
                      | print4(n=4) |  <-- (This frame is removed)
                      +-------------+
                      | print3(n=3) |  <-- NEW TOP
                      +-------------+
                      |    ...      |
                      +-------------+
                     THE CALL STACK
```

| Console Output        | Call Stack         |
| --------------------- | ------------------ |
| (no change in output) | `+-------------+`` |

```bash
                      +-------------+
                      | print3(n=3) |  --POP-->
                      +-------------+
                      | print2(n=2) |  --POP-->
                      +-------------+
                      | print1(n=1) |  --POP-->
                      +-------------+
                      |    main()   |  <-- BECOMES THE TOP
                      +-------------+
                     THE CALL STACK
```

------

### Step 11: `main` finishes → stack is empty

Finally, `main` returns, and the program ends.

```bash
        POP  <---     +-------------+
                      |    main()   |  <-- (This frame is removed)
                      +-------------+

                      (STACK IS EMPTY)
```

| Console Output | Call Stack  |
| -------------- | ----------- |
| (no change)    | **(empty)** |

------

##  Key Takeaways

- The call stack follows **LIFO (Last-In, First-Out)**.
- Every function call creates a **new stack frame**.
- When a function ends, its frame is popped, and execution returns to the caller.
- This is exactly how recursion works too — the only difference is that in recursion, a function is calling **itself** instead of a different one.



