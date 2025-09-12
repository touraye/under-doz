# Programming Assignment -- Unit 4

**Topic: Time and Space Complexity with Practical Examples**

##  1. Average Stock Price

**Problem:**
Given stock prices for multiple days, calculate the average price.

``` java
static double calculateAveragePrice(int[] stockPrice) {
    if (stockPrice == null || stockPrice.length == 0) {
        throw new IllegalArgumentException("Input array is empty or null");
    }
    double totalPrice = 0;
    for (int price : stockPrice) {
        totalPrice += price;
    }
    return totalPrice / stockPrice.length;
}
```

### Complexity Analysis

-   **Time Complexity:** O(N) → One pass through the array.\
-   **Space Complexity:** O(1) → Only variables used.

**Practical Example:** Suppose you run a stock analysis app. Each night,
you receive prices of a stock over the day. Calculating the average
helps you know the "typical price" to decide whether to buy or sell.

**Solved Example:** Input
`[209, 589, 193, 204, 109, 120, 200, 120, 877, 453]` → Average = `307.4`

## 2. Find Maximum Price

**Problem:**
Find the highest stock price from an array.

``` java
static double findMaximumPrice(int[] inputArr) {
    double maxPrice = 0;
    for (int price : inputArr) {
        if (price > maxPrice) {
            maxPrice = price;
        }
    }
    return maxPrice;
}
```

### Complexity Analysis

-   **Time Complexity:** O(N)\
-   **Space Complexity:** O(1)

**Practical Example:** An investor checks the peak price in the last 10
days to decide the best selling opportunity.

**Solved Example:** Input
`[209, 589, 193, 204, 109, 120, 200, 120, 877, 453]` → Maximum = `877`

## 3. Count Occurrences

**Problem:**
Count how many times a specific stock price appears.

``` java
static int countOccurrences(int[] inputStockPrices, int targetPrice) {
    int counter = 0;
    for (int price : inputStockPrices) {
        if (price == targetPrice) {
            counter++;
        }
    }
    return counter;
}
```

### Complexity Analysis

-   **Time Complexity:** O(N)\
-   **Space Complexity:** O(1)

**Practical Example:** A trader wants to see how many times a specific
threshold price occurred to understand market stability.

**Solved Example:** Input
`[209, 589, 193, 204, 109, 120, 200, 120, 877, 453]`, target=`120` →
Occurrences = `2`

##  4. Cumulative Value

**Problem:**
Calculate cumulative stock values (running total).

``` java
static ArrayList<Integer> cumulativeSum(ArrayList<Integer> inputArr) {
    ArrayList<Integer> cumulativeSumArr = new ArrayList<>();
    cumulativeSumArr.add(inputArr.get(0));
    for (int i = 1; i < inputArr.size(); i++) {
        int sum = cumulativeSumArr.get(i - 1) + inputArr.get(i);
        cumulativeSumArr.add(sum);
    }
    return cumulativeSumArr;
}
```

### Complexity Analysis

-   **Time Complexity:** O(N)\
-   **Space Complexity:** O(N)

**Practical Example:** Portfolio managers use cumulative stock value
tracking to observe growth trends over a period.

**Solved Example:** Input
`[209, 589, 193, 204, 109, 120, 200, 390, 540, 890]` → Cumulative =
`[209, 798, 991, 1195, 1304, 1424, 1624, 2014, 2554, 3444]`

## 5. Space Complexity vs. Auxiliary Space

**Space Complexity:**
The total memory used by an algorithm/program during execution. Includes
input, variables, recursion stack, and data structures.

**Auxiliary Space:**
The extra space used by an algorithm beyond the input. Focuses only on
temporary or additional memory.

### Examples:

1.  **Fibonacci Recursive (Naïve)**

-   Time: O(2^n)
-   Space: O(n) (recursion stack)
-   Auxiliary: O(n)

2.  **Fibonacci Iterative Optimized**

-   Time: O(n)
-   Space: O(1)
-   Auxiliary: O(1)

3.  **Merge Sort**

-   Time: O(n log n)
-   Space: O(n) (extra array)
-   Auxiliary: O(n)

4.  **Quick Sort (In-Place)**

-   Time: O(n log n) average
-   Space: O(n) total (array + stack)
-   Auxiliary: O(log n) (recursion stack only)

## Summary Table

------------------------------------------------------------------------------
  Problem           Time Complexity Space Complexity Auxiliary Space Notes
----------------- --------------- ---------------- --------------- -----------
  Average Price     O(N)            O(1)             O(1)            Iterates
                                                                     once

  Maximum Price     O(N)            O(1)             O(1)            Iterates
                                                                     once

  Count Occurrence  O(N)            O(1)             O(1)            Iterates
                                                                     once

  Cumulative Value  O(N)            O(N)             O(N)            Needs extra
                                                                     array

  Fibonacci         O(2\^n)         O(n)             O(n)            Very slow
  Recursion                                                          

  Fibonacci         O(n)            O(1)             O(1)            Best
  Iterative                                                          practical

  Merge Sort        O(n log n)      O(n)             O(n)            Needs temp
                                                                     array

  Quick Sort        O(n log n)      O(n)             O(log n)        In-place

------------------------------------------------------------------------
