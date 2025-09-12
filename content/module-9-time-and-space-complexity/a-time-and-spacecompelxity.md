# Complexity

Time and spacing are the two resource a computer need to perform any operation e.i to run any task given to it. Time is actually the amount of time taken for an algorithm to compute and space the amount of memory used to a computer to execute a task.

## What is Time Complexity

Imagine you are tasked to write a **linear search algorithm** to find element from an array with element of 1,000,000. This algorithm will be executed on a very old computer and that of latest machine. And, for this search let's say the element doesn't exist on an array. The analysis of the algorithm; 

* Old computer: 10sec
* New computer: 1sec

Which computer has a better time complexity? To your surprise both this machine have the same time complexity. Time complexity is not equal to time taken to run an algorithm rather is relative to the input grow. Time complexity is a function that give us the relationship of how the time will grows (linearly) as the input grows.

## Space Complexity

Space complexity  of an algorithm is total space taken by an algorithm with respect to its input size. **space complexity** include both **Auxiliary space** and space used by the input.

**Auxiliary space** unlike **space complexity** is the extract space or temporary used by an algorithm.

### Big O Notation

**Big O notation** is a mathematical way to describe **how fast an algorithm grows** (its **time complexity**) or **how much extra memory it uses** (its **space complexity**) as the input size increases.

Instead of measuring exact execution time (which depends on hardware, language, etc.), Big O gives us a **general measure of efficiency** by focusing on the **rate of growth** as input size → ∞.

###  Why use Big O?

- To **compare algorithms** (e.g., is bubble sort slower than merge sort?).
- To **predict performance** for large inputs.
- To **ignore constants and small terms** and focus only on what matters as inputs grow.

We will leverage **Big O** in our studies of **data structures and algorithm (DSA)** to read and analyst algorithms.  

Common **Big O** complexities:

| Big O      | Name         | Growth Example                 |
| ---------- | ------------ | ------------------------------ |
| O(1)       | Constant     | Array access                   |
| O(log⁡ n)   | Logarithmic  | Binary search                  |
| O(n)       | Linear       | Loop through array             |
| O(n log n) | Linearithmic | Merge sort                     |
| O(n^2)     | Quadratic    | Nested loops                   |
| O(2^n)     | Exponential  | Recursive Fibonacci            |
| O(n!)      | Factorial    | Traveling salesman brute force |

