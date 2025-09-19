# Recursion In Practice

It's time to dive into some practice aspect of recursion, we will go through some examples, and try to solve them. Firstly, by understanding the problem, analyzing the problem, and lastly solving it with a recursion. So, its going to be a exhausting one.

  Topics:

* Factorial of a number 
* Iteration
* Recursion
* Recursive tree
* visualization
* Call stack

We will explore some of this problems:

## Factorial of a number

The factorial of a number (`n`) is the product of all integers from `1` to that number or from that number to `1`. In other word factorial of a number is the sum of all positive integer less than or equal to that number and it written as `n! = n * (n- 1)!`. Suppose we want to find the factorial of `5` then we would multiple all the number from `5` up to `1` ; `5! = 5 * 4 * 3 * 2 * 1 = 120` and `4! = 4 * 3 * 2 * 1 = 24`

Given the numbers like `4` and `5` we can simply analyze and write the possible answer, but what of factorial of `10` or even more. It's practically impossible to analyze without writing an algorithms. So, therefore will write an algorithm to find a factorial of any given number. As mentioned in the previous lessons we will be using recursion and iteration to solve problems. 

**Using iteration:**

```java
static int iterativeFactorial(int n) {
    int result = 1;
    for (int i = 1; i <= n; i++){
        result *= i;
    }

    return result;
}
```

The above uses **iterative** to find a factorial of a number which does not create a recursive function either a *stack frame*. However, we will visualize it to understand the concept and we will deepen our understanding with real **recursive call**.

Let's do this in three parts:

1.  **Visualize the Iterative Code**: We'll learn how the *actual* code works.
2.  **Write the Recursive Version**: To answer your question, we need a recursive factorial function.
3.  **Visualize the Recursive Version**: Then, I will draw the recursive tree and call stack for that version, which is what you asked to see.

---

### 1. Visualization the Iterative Code

For an iterative function, we don't look at a growing stack. We just track the state of the variables within its single stack frame as the loop runs.

Let's trace `iterativeFactorial(4)`:

**Initial State:**
When `iterativeFactorial(4)` is called, a single stack frame is created.

| Call Stack                                                   |
| :----------------------------------------------------------- |
| ``` +--------------------------+ | | iterativeFactorial(n=4)  | <-- Top | |   result = 1             | |   i = ?                  | | +--------------------------+ | | main()                   | | +--------------------------+ ``` |

**Loop Execution Trace:**
The program now loops from `i = 1` to `4`.

| Loop Iteration (`i`) | Condition (`i <= 4`) | `result` Before `result *= i` | `result` After `result *= i` |
| :------------------- | :------------------- | :---------------------------- | :--------------------------- |
| 1                    | `true`               | 1                             | `1 * 1 = 1`                  |
| 2                    | `true`               | 1                             | `1 * 2 = 2`                  |
| 3                    | `true`               | 2                             | `2 * 3 = 6`                  |
| 4                    | `true`               | 6                             | `6 * 4 = 24`                 |
| 5                    | `false`              | 24                            | (Loop terminates)            |

**Final State:**
The loop ends. The function returns the final value of `result`, which is `24`. The `iterativeFactorial` stack frame is then popped.

As you can see, the stack never grew deeper. The work all happened inside one function call.

---

### 2. The Recursive Version of Factorial

To demonstrate a recursive tree and call stack, we need a function that calls itself. Here is the standard recursive implementation of factorial:

```java
static int recursiveFactorial(int n) {
    // Base Case: The condition that stops the recursion.
    if (n == 0) {
        return 1;
    }
    // Recursive Step: The function calls itself with a different input.
    else {
        return n * recursiveFactorial(n - 1);
    }
}
```

---

### 3. Recursive Tree and Call Stack for `recursiveFactorial(4)`

This is where we can truly visualize the concepts you asked about.

#### A) Recursive Tree

A recursive tree shows the hierarchy of function calls. The initial call is at the top (the root), and each subsequent call is a child node. The work happens as the results are passed back up the tree.

`recursiveFactorial(4)`

```java
          factorial(4)
         /      ▲
        /       | returns 24
       /        |
      /      n * result = 4 * 6
     /
  calls factorial(3)
         /      ▲
        /       | returns 6
       /        |
      /      n * result = 3 * 2
     /
  calls factorial(2)
         /      ▲
        /       | returns 2
       /        |
      /      n * result = 2 * 1
     /
  calls factorial(1)
         /      ▲
        /       | returns 1
       /        |
      /      n * result = 1 * 1
     /
  calls factorial(0)
             |
             | returns 1 (This is the BASE CASE)
             ▼
```

*   **Going Down:** Each call to `factorial(n)` must wait for the result of `factorial(n-1)`.
*   **Coming Up:** The chain reaction starts when `factorial(0)` hits the **base case** and returns `1`. This value is then passed up, allowing the waiting calls to complete their calculations one by one.

#### B) Call Stack Visualization

This shows how memory is allocated for each function call.

##### Phase 1: Building the Stack (Pushing)

1.  `main` calls `recursiveFactorial(4)`. A frame is pushed on the stack.
    `factorial(4)` must wait for `factorial(3)`.

    ```java
    +------------------------+
    | factorial(n=4)         |  <-- Top
    |   returns 4 * ???      |
    +------------------------+
    | main()                 |
    +------------------------+
    ```

2.  `factorial(4)` calls `recursiveFactorial(3)`. A new frame is pushed.
    `factorial(3)` must wait for `factorial(2)`.

    ```bash
    +------------------------+
    | factorial(n=3)         |  <-- Top
    |   returns 3 * ???      |
    +------------------------+
    | factorial(n=4)         |
    +------------------------+
    | main()                 |
    +------------------------+
    ```

3.  This continues until the **base case** (`n=0`) is reached. The stack is now at its deepest.

    ```bash
    +------------------------+
    | factorial(n=0)         |  <-- Top
    |   (Base Case)          |
    +------------------------+
    | factorial(n=1)         |
    |   returns 1 * ???      |
    +------------------------+
    | factorial(n=2)         |
    |   returns 2 * ???      |
    +------------------------+
    | factorial(n=3)         |
    |   returns 3 * ???      |
    +------------------------+
    | factorial(n=4)         |
    |   returns 4 * ???      |
    +------------------------+
    | main()                 |
    +------------------------+
    ```

##### Phase 2: Unwinding the Stack (Popping)

4.  `factorial(0)` hits the base case. It doesn't call another function. It simply `returns 1`. Its work is done, so its frame is **popped**. The `1` is returned to its caller, `factorial(1)`.

    ```bash
    (factorial(0) is popped)

    +------------------------+
    | factorial(n=1)         |  <-- Top
    |   returns 1 * 1        |  (It received 1 from factorial(0))
    +------------------------+
    | ... below ...          |
    +------------------------+
    ```

5.  `factorial(1)` can now finish its calculation (`1 * 1 = 1`). It `returns 1` to its caller, `factorial(2)`. Its frame is **popped**.

    ```bash
    (factorial(1) is popped)

    +------------------------+
    | factorial(n=2)         |  <-- Top
    |   returns 2 * 1        |  (It received 1 from factorial(1))
    +------------------------+
    | ... below ...          |
    +------------------------+
    ```

6.  This process of returning a value, calculating, and popping continues all the way back up.
    *   `factorial(2)` calculates `2 * 1 = 2`, returns `2`, and is popped.
    *   `factorial(3)` receives `2`, calculates `3 * 2 = 6`, returns `6`, and is popped.
    *   `factorial(4)` receives `6`, calculates `4 * 6 = 24`, returns `24` to `main`, and is popped.

7.  Finally, control returns to `main()`. The stack is back to where it started, and `main` now has the result `24`.

    ```bash
    +------------------------+
    | main()                 |  <-- Top
    +------------------------+
    ```

**Key Takeaway**

* Factorial of number
  * Iterative approach
  * Recursive approach
* Visualization of iterative and recursive approach
  * Recursive tree
  * Call Stack
* 
