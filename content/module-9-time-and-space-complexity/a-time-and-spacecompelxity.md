# Complexity

In computer science, time and space are the two fundamental resources required for executing any operation. Time complexity measures the amount of computational time an algorithm takes to produce a result, whereas space complexity measures the amount of memory utilized by the computer during the execution of the algorithm.

## What is Time Complexity

Imagine you are asked to write a linear search algorithm to find an element in an array of 1,000,000 elements. This algorithm is executed on two machines: a very old computer and the latest high-speed machine. Suppose the element does not exist in the array. On the old computer, the search takes 10 seconds, while on the new computer, it takes just 1 second. Which computer has a better time complexity? Surprisingly, both machines have the *same* time complexity. This is because time complexity is not about the actual time taken to run an algorithm, but about how the runtime grows relative to the input size. In this case, the runtime grows linearly with the input, making the time complexity O(n). 

## Space Complexity

Space complexity of an algorithm refers to the total amount of memory it requires with respect to the input size. It includes both the memory occupied by the input itself and the additional memory needed during execution. **Auxiliary space**, on the other hand, is the extra or temporary memory an algorithm uses beyond the input. This often comes from local variables, recursion stacks, or temporary data structures that may increase the memory usage of the algorithm.

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

Time and space have different variation of complexities:

### **Time complexities**

* **Constant time O(1):** 

  * **Definition:** Execution time does not depend on input size.
  *  **Example:** Accessing an element in an array by index.

  ```java
  public class ConstantTime {
      public static void main(String[] args) {
          int[] arr = {10, 20, 30, 40};
          // Accessing element takes constant time
          System.out.println("Element at index 2: " + arr[2]); 
      }
  }
  
  ```

* **Linear time O(n):**

  * **Definition:** Execution time grows proportionally with input size.

  *  **Example:** Looping through an array.

    ```java
    public class LinearTime {
        public static void main(String[] args) {
            int[] arr = {10, 20, 30, 40};
            for (int num : arr) { // O(n)
                System.out.println(num);
            }
        }
    }
    ```

* **Quadratic time O(n²):**

  * **Definition:** Execution time grows with the square of input size

  *  **Example:** Nested loops comparing all pairs.

    ```java
    public class QuadraticTime {
        public static void main(String[] args) {
            int[] arr = {1, 2, 3};
            for (int i = 0; i < arr.length; i++) {        // O(n)
                for (int j = 0; j < arr.length; j++) {    // O(n)
                    System.out.println(arr[i] + "," + arr[j]); 
                }
            }
        }
    }
    ```

* **Exponential time O(2ⁿ):**

  * **Definition:** Execution time doubles with each increase in input size.

  *  **Example:** Naïve recursive Fibonacci.

    ```java
    public class ExponentialTime {
        public static int fib(int n) {
            if (n <= 1) return n;
            return fib(n - 1) + fib(n - 2); // O(2^n)
        }
    
        public static void main(String[] args) {
            int n = 5;
            System.out.println("Fibonacci of " + n + " = " + fib(n));
        }
    }
    
    ```

### **Space complexity**

* **Constant space O(1):**

  * **Definition:** Memory use is fixed, independent of input size.

  *  **Example:** Finding the maximum in an array.

    ```java
    public class ConstantSpace {
        public static int findMax(int[] arr) {
            int max = Integer.MIN_VALUE; // constant space
            for (int num : arr) {
                if (num > max) {
                    max = num;
                }
            }
            return max;
        }
    
        public static void main(String[] args) {
            int[] arr = {5, 8, 2, 9};
            System.out.println("Max: " + findMax(arr));
        }
    }
    
    ```

* **Linear space O(n):**

  * **Definition:** Memory use grows proportionally with input size.

  *  **Example:** Cumulative sum stored in a new array.

    ```java
    import java.util.*;
    
    public class LinearSpace {
        public static int[] cumulativeSum(int[] arr) {
            int[] cumSum = new int[arr.length]; // O(n) extra space
            cumSum[0] = arr[0];
            for (int i = 1; i < arr.length; i++) {
                cumSum[i] = cumSum[i - 1] + arr[i];
            }
            return cumSum;
        }
    
        public static void main(String[] args) {
            int[] arr = {2, 4, 6, 8};
            System.out.println(Arrays.toString(cumulativeSum(arr)));
        }
    }
    
    ```

* **Logarithmic space O(log n):**

  * **Definition:** Memory use grows with log of input size, usually from recursion stack.

  *  **Example:** Binary search (recursive).

    ```java
    public class LogarithmicSpace {
        public static int binarySearch(int[] arr, int target, int left, int right) {
            if (left > right) return -1; // base case
    
            int mid = left + (right - left) / 2;
    
            if (arr[mid] == target) return mid;
            else if (arr[mid] > target)
                return binarySearch(arr, target, left, mid - 1); // recursion stack O(log n)
            else
                return binarySearch(arr, target, mid + 1, right);
        }
    
        public static void main(String[] args) {
            int[] arr = {2, 4, 6, 8, 10, 12};
            int target = 8;
            System.out.println("Index of " + target + ": " + binarySearch(arr, target, 0, arr.length - 1));
        }
    }
    
    ```

    
