

# Understanding Recursion with Examples in Java

Recursion is when a function calls itself to solve a problem. While it can make solutions elegant, it also relies heavily on **stack memory**. Each recursive call creates a new frame in the stack, and if calls go too deep, it can cause a **`StackOverflowError`**.

Will learn recursion with some fewer examples

### Example 1: Factorial of a Number

What is a factorial of a number

```java
public class RecursionExample {
    public static int factorial(int n) {
        if (n == 0) {   // Base case
            return 1;
        }
        return n * factorial(n - 1);  // Recursive call
    }

    public static void main(String[] args) {
        int result = factorial(5);
        System.out.println("Factorial of 5 is: " + result);
    }
}
```

 **Explanation**

- The function keeps calling itself with `n-1` until it reaches the base case (`n == 0`).
- Each recursive call is placed on the **stack**.
- When the base case is reached, the stack begins to **unwind** (return values one by one).

 Execution for `factorial(5)` looks like this:

```java
factorial(5)
 → 5 * factorial(4)
   → 4 * factorial(3)
     → 3 * factorial(2)
       → 2 * factorial(1)
         → 1 * factorial(0) = 1
```

Unwinding back:

```java
1 * 1 = 1
2 * 1 = 2
3 * 2 = 6
4 * 6 = 24
5 * 24 = 120
```

### Example 2: Fibonacci Numbers

To understand Fibonacci numbers we first need to know the first two numbers (zeroth and first number) of the Fibonacci numbers/sequence  which are (`0` and `1`). From the first two we can begun finding the 2nd, 3rd, 4th,... Since Fibonacci is Mathematic construct, so therefore, we need to understand the formular: 

The `n(th)` **Fibonacci #** is the sum of the previous two: `fibo(n) = fibo(n -1) + fibo(n -2)`. What's `n(th)`? It is regarded as the **Fibonacci #** 

The zeroth (`0th`) and the first (`1st`) are always given and to find the second (`2nd`), third (`3rd`), fourth (`4th`) and ..... we need to add previous two:

* `2nd` **Fibonacci #**:  going to be sum of the previous two; `0th` **Fibonacci #** + `1st` **Fibonacci #** : `0 + 1` `2nd` = `1`.
* `3rd` **Fibonacci #**: `1st + 2nd` ~ `3rd` = `1 + 1` : `3rd` = `2`
* `4th` **Fibonacci #**: `2nd + 3rd` ~ `4th` = `1 + 2 ` : `4th` = `3`
* `5th` **Fibonacci #**: `3rd + 4th` ~ `5th` = `2 + 3 ` : `4th` = `5`
* `6th` **Fibonacci #**: `4th + 5th` ~ `6th` = `3 + 5 ` : `4th` = `8`
* `7th` **Fibonacci #**: `5th + 6th` ~ `7th` = `5 + 8 ` : `4th` = `13`

Finding the `n-th` **Fibonacci number** cannot be that 

The first two Fibonacci number are `0` and `1`. The rule of thumb is that second Fibonacci number is the sum of the previous which are `0` and `1` which is `1` so forth and on. So therefore, finding the Fibonacci number of any given is the sum of previous two; 

The second Fibonacci number is `0 + 1 = 1`, third Fibo # is `1 + 1 = 2`, fourth Fibo # = `2 + 1 = 3`.

Writing an Algorithm to find out Fibonacci of any given number (`n`):

```java
public class FibonacciExample {
    public static int fibonacci(int n) {
        if (n <= 1) {   // Base cases
            return n;
        }
        return fibonacci(n - 1) + fibonacci(n - 2); // Recursive calls
    }

    public static void main(String[] args) {
        int result = fibonacci(6);
        System.out.println("Fibonacci of 6 is: " + result);
    }
}
```

The above find out the Fibonacci number of `n`. Am sure will be amazing; `fib(n - 1) + fib(n - 2);` Well let's try to understand this abstract code.

* Try to have a picture of the first **Fibonacci** numbers; `0, 1`
* Second **Fibonacci #** ` 0 + 1` = `1`
* Third **Fibonacci #** = `1 + 1` = `2`
* Fourth **Fibonacci #** = `1 + 2` = `3`
* Fifth **Fibonacci #** = `2 + 3` = `5`
* Sixth **Fibonacci #** = `3 + 5` = `8`

**Explanation**

- Each call to `fibonacci(n)` spawns **two new calls** (`fibonacci(n-1)` and `fibonacci(n-2)`).
- This creates a **tree of recursive calls**.

For `fibonacci(6)`, the recursion tree expands like this:

```
fibonacci(6)
 ├─ fibonacci(5)
 │   ├─ fibonacci(4)
 │   │   ├─ fibonacci(3)
 │   │   └─ fibonacci(2)
 │   └─ fibonacci(3)
 └─ fibonacci(4)
     ├─ fibonacci(3)
     └─ fibonacci(2)
```

### Example 3: Recursive String Reversal

```java
public class StringReversal {
    public static String reverse(String str) {
        if (str.isEmpty()) {
            return str; // Base case
        }
        return reverse(str.substring(1)) + str.charAt(0);
    }

    public static void main(String[] args) {
        String result = reverse("hello");
        System.out.println("Reversed: " + result);
    }
}
```

 **Explanation**

- Each recursive call removes the first character and processes the rest.
- When the string is empty, recursion stops.
- The characters are added back in reverse order as the stack unwinds.

Execution for `"hello"`:

```
reverse("hello")
 → reverse("ello") + 'h'
   → reverse("llo") + 'e'
     → reverse("lo") + 'l'
       → reverse("o") + 'l'
         → reverse("") + 'o'
```

Unwinding back → `"olleh"`.

------

**Key Takeaway**

- Recursion is elegant but can be memory-intensive.
- Always define a **base case** to prevent infinite recursion.
- For large inputs, recursion may cause **stack overflow**, so iteration or memorization can be better.



Let's use `fibonacci(4)` as our example. It's complex enough to show the branching but small enough to visualize clearly.

The Fibonacci sequence is: 0, 1, 1, 2, 3, 5, 8, ...
So, we expect `fibonacci(4)` to return `3`.

---

### 1. The Recursive Tree

The recursive tree is the most intuitive way to understand the flow of calls. It shows how the problem is broken down into smaller and smaller pieces until it hits the base cases. Then, the results are passed back up the tree and combined.

The tree is divided into two parts; left and right tree:

The recursive tree is drive from [tree data structure](). A tree is divided into 3 parts: root, left child, and right child. A recursive tree on the hand is the representation of a flow of the function calls. The function always start from the **root**, to the **left child**, and then to the **right child**. Each will return a value when **base case** is hit; `fibo(1), fibo(0)`. 

* The root is `fibo(n)`
* The left child is `fibo(n - 1)`
* The right child is `fibo(n - 2)`

### Recursive Tree

This tree will help us to be able compute for smaller value, but yet the form the base foundation.

```java
                        fib(4)
                     /         \
            returns 2 /           \ returns 1
                   /             \
             fib(3)      +        fib(2)
           /      \             /      \
 returns 1/        \returns 1   returns 1/        \returns 0
         /          \           /          \
    fib(2)    +    fib(1)     fib(1)    +    fib(0)
   /      \          |           |           |
r:1/        \r:0     (Base Case) (Base Case) (Base Case)
 /          \       returns 1   returns 1   returns 0
fib(1)   +   fib(0)
  |            |
(Base Case)  (Base Case)
returns 1    returns 0
```

#### How to read the tree:

1.  **Going Down (The Calls):** The tree expands downwards. `fib(4)` can't solve itself, so it calls `fib(3)` and `fib(2)`. `fib(3)` can't solve itself, so it calls `fib(2)` and `fib(1)`, and so on, until a function hits a base case (`n <= 1`).
2.  **Coming Up (The Returns):** Once a base case is hit (`fib(1)` or `fib(0)`), it returns a value (`1` or `0`). This value is passed up to its parent caller.
3.  **Combining Results:** A parent node waits until **both** of its children have returned a value. It then adds them together and returns the sum to its own parent.
    *   The leftmost `fib(2)` receives `1` and `0`, adds them to get `1`, and returns `1` to `fib(3)`.
    *   `fib(3)` receives `1` (from its `fib(2)`) and `1` (from its `fib(1)`), adds them to get `2`, and returns `2` to the top-level `fib(4)`.
    *   The top `fib(4)` now has the result from its left side (`2`). It then executes its right side, `fib(2)`, which eventually returns `1`.
    *   Finally, `fib(4)` adds its two results: `2 + 1 = 3`.

**A Very Important Observation:** Notice how `fib(2)` is calculated twice, `fib(1)` is calculated three times, and `fib(0)` twice. This is why this particular recursive implementation is very inefficient! Which yet to be discuss, a proper solution to this is with [dynamic programming]().

---

### 2. The Call Stack Visualization

The call stack shows the actual order of execution in memory. It's more complex because the stack grows and shrinks multiple times. In the expression `fib(n-1) + fib(n-2)`, the program must **completely resolve `fib(n-1)`** before it even starts the `fib(n-2)` call.

Let's trace the execution of `fib(4)`.

| Step   | Action                      | Call Stack                                   | Explanation                                                  |
| :----- | :-------------------------- | :------------------------------------------- | :----------------------------------------------------------- |
| **1**  | `main` calls `fib(4)`       | ```[main, fib(4)]```                         | `fib(4)` needs to compute `fib(3) + fib(2)`. It starts with the left side. |
| **2**  | `fib(4)` calls `fib(3)`     | ```[main, fib(4), fib(3)]```                 | `fib(3)` needs to compute `fib(2) + fib(1)`. It starts with the left side. |
| **3**  | `fib(3)` calls `fib(2)`     | ```[main, fib(4), fib(3), fib(2)]```         | `fib(2)` needs to compute `fib(1) + fib(0)`. It starts with the left side. |
| **4**  | `fib(2)` calls `fib(1)`     | ```[main, fib(4), fib(3), fib(2), fib(1)]``` | **Stack is at its deepest.** `fib(1)` is a base case.        |
| **5**  | `fib(1)` returns `1`        | ```[main, fib(4), fib(3), fib(2)]```         | `fib(1)` is popped. The value `1` is returned to `fib(2)`.   |
| **6**  | `fib(2)` calls `fib(0)`     | ```[main, fib(4), fib(3), fib(2), fib(0)]``` | `fib(2)` now executes the right side of its `+`. It calls `fib(0)`. |
| **7**  | `fib(0)` returns `0`        | ```[main, fib(4), fib(3), fib(2)]```         | `fib(0)` is a base case. It's popped. The value `0` is returned to `fib(2)`. |
| **8**  | `fib(2)` returns `1+0=1`    | ```[main, fib(4), fib(3)]```                 | `fib(2)` now has both results. It computes the sum and returns `1` to `fib(3)`. |
| **9**  | `fib(3)` calls `fib(1)`     | ```[main, fib(4), fib(3), fib(1)]```         | `fib(3)` has the result from its left side (`1`). It now executes its right side. |
| **10** | `fib(1)` returns `1`        | ```[main, fib(4), fib(3)]```                 | `fib(1)` is a base case. It's popped. The value `1` is returned to `fib(3)`. |
| **11** | `fib(3)` returns `1+1=2`    | ```[main, fib(4)]```                         | `fib(3)` has both results. It computes the sum and returns `2` to `fib(4)`. |
| **12** | `fib(4)` calls `fib(2)`     | ```[main, fib(4), fib(2)]```                 | **We're halfway!** `fib(4)` has the result from its left side (`2`). It now starts its right side. Notice we are computing `fib(2)` all over again. |
| **13** | `fib(2)` calls `fib(1)`     | ```[main, fib(4), fib(2), fib(1)]```         | `fib(2)` starts its left side.                               |
| **14** | `fib(1)` returns `1`        | ```[main, fib(4), fib(2)]```                 | `fib(1)` is popped.                                          |
| **15** | `fib(2)` calls `fib(0)`     | ```[main, fib(4), fib(2), fib(0)]```         | `fib(2)` starts its right side.                              |
| **16** | `fib(0)` returns `0`        | ```[main, fib(4), fib(2)]```                 | `fib(0)` is popped.                                          |
| **17** | `fib(2)` returns `1+0=1`    | ```[main, fib(4)]```                         | `fib(2)` has its results, computes the sum, and returns `1` to `fib(4)`. |
| **18** | `fib(4)` returns `2+1=3`    | ```[main]```                                 | **Finally!** `fib(4)` has both results. It computes the final sum and returns `3` to `main`. |
| **19** | Program continues in `main` | ```[main]```                                 | The result `3` is now available in the `main` method.        |

**Note!** 

Whenever working with **algorithms** like **recursion** try to solve the problem with a pen and paper first before with code. The code will give you a very abstract understanding, while your effort is to trying memorizing the syntax. Visualize then implement with code.
