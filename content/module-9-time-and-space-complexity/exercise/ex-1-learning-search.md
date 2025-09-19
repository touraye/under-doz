In this exercise we will:

* Implements **linear search**.
* Measures **runtime** of the algorithm.
* Provides **questions** as an exercise.

Code:

```java
import java.util.Arrays;

public class LinearSearchTest {

    // Linear search function
    public static int linearSearch(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i; // target found
            }
        }
        return -1; // target not found
    }

    public static void main(String[] args) {
        // Create an array with 1,000,000 elements
        int size = 1_000_000;
        int[] arr = new int[size];
        for (int i = 0; i < size; i++) {
            arr[i] = i + 1; // elements from 1 to 1,000,000
        }

        int target = -1; // element not in array

        // Measure runtime
        long startTime = System.nanoTime();
        int result = linearSearch(arr, target);
        long endTime = System.nanoTime();

        long duration = (endTime - startTime) / 1_000_000; // in milliseconds

        if (result == -1) {
            System.out.println("Element not found in array.");
        } else {
            System.out.println("Element found at index: " + result);
        }

        System.out.println("Execution time: " + duration + " ms");
    }
}

```

Sample Output (will vary depending on machine speed)

```bash
Element not found in array.
Execution time: 6 ms
```

On an older machine, the same program might take `~50 ms` (or more), while on a new machine it could be much faster. But in both cases, the **time complexity** is still **O(n)**.

##  Exercise  Questions

1. What is the time complexity of the linear search algorithm? Why?
2. If the target element exists at the beginning of the array, how does this affect runtime?
3. If the target element does not exist in the array, how many comparisons will be made?
4. Why does the same program run faster on a new machine compared to an old machine, even though both have the same time complexity?
5. How would the time complexity change if the array size doubled from 1,000,000 to 2,000,000?