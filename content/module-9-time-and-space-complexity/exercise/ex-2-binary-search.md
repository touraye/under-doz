In this exercise we will:

* Implements **binary search**.
* Measures **runtime** of the algorithm.
* Provides **questions** as an exercise.

Code:

```java
import java.util.Arrays;

public class SearchComparisonTest {
    // Linear search function
    public static int linearSearch(int[] arr, int target) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == target) {
                return i; // target found
            }
        }
        return -1; // target not found
    }

    // Binary search function (iterative)
    public static int binarySearch(int[] arr, int target) {
        int left = 0, right = arr.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (arr[mid] == target) {
                return mid; // target found
            } else if (arr[mid] < target) {
                left = mid + 1; // search right half
            } else {
                right = mid - 1; // search left half
            }
        }

        return -1; // target not found
    }

    public static void main(String[] args) {
        // Create an array with 1,000,000 sorted elements
        int size = 1_000_000;
        int[] arr = new int[size];
        for (int i = 0; i < size; i++) {
            arr[i] = i + 1; // elements from 1 to 1,000,000
        }

        int target = -1; // element not in array

        // Measure runtime for Linear Search
        long startTime = System.nanoTime();
        int resultLinear = linearSearch(arr, target);
        long endTime = System.nanoTime();
        long durationLinear = (endTime - startTime) / 1_000_000; // in ms

        // Measure runtime for Binary Search
        startTime = System.nanoTime();
        int resultBinary = binarySearch(arr, target);
        endTime = System.nanoTime();
        long durationBinary = (endTime - startTime) / 1_000_000; // in ms

        // Print results
        System.out.println("Target: " + target);

        System.out.println("\n--- Linear Search ---");
        System.out.println("Result: " + (resultLinear == -1 ? "Not Found" : "Found at index " + resultLinear));
        System.out.println("Execution time: " + durationLinear + " ms");

        System.out.println("\n--- Binary Search ---");
        System.out.println("Result: " + (resultBinary == -1 ? "Not Found" : "Found at index " + resultBinary));
        System.out.println("Execution time: " + durationBinary + " ms");
    }
}

```

Sample Output (will vary depending on machine speed)

```java
Target: -1

--- Linear Search ---
Result: Not Found
Execution time: 9 ms

--- Binary Search ---
Result: Not Found
Execution time: 0 ms

```

## Exercise Questions

1. What is the time complexity of **Linear Search**?
2. What is the time complexity of **Binary Search**?
3. Why does Binary Search require a **sorted array**?
4. If the array size doubles (from 1,000,000 to 2,000,000), how would the runtime growth differ between Linear Search and Binary Search?
5. Can Binary Search ever be slower than Linear Search? In what scenarios?