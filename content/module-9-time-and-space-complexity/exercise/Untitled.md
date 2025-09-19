# Analytic of Time and Space Complexity

**Topic: Time and Space Complexity with Practical Examples**

## 1. Average Stock Price

### Problem

Given stock prices for multiple days, calculate the average price.

### Java Implementation

```java
static double calculateAveragePrice(int[] stockPrice) {
    if (stockPrice == null || stockPrice.length == 0) {
        throw new IllegalArgumentException("Input array is empty or null");
    }

    double totalPrice = 0; // accumulator
    for (int price : stockPrice) {
        totalPrice += price; // constant time addition
    }

    return totalPrice / stockPrice.length; // division is O(1)
}

// Example usage
int[] stockPrices = {209, 589, 193, 204, 109, 120, 200, 120, 877, 453};
System.out.println("Average stock price: " +
    NumberFormat.getCurrencyInstance(new Locale("en", "US"))
        .format(calculateAveragePrice(stockPrices)));
```

### Complexity Analysis

- **Time Complexity:** O(N) → One pass through the array of size N.
- **Space Complexity:** O(1) → Only a few variables are used, independent of input size.

### Practical Example

*Suppose you run a stock analysis app*. Each night, you receive prices of a stock over the day. Calculating the average helps you know the "typical price" to decide whether to buy or sell.

##  2. Find Maximum Price

### Problem

Find the highest stock price from an array of stock prices.

### Java Implementation

```java
static double findMaximumPrice(int[] inputArr) {
    double maxPrice = 0;
    for (int price : inputArr) {
        if (price > maxPrice) {
            maxPrice = price;
        }
    }
    return maxPrice;
}

// Example usage
System.out.println("Maximum stock price: " +
    NumberFormat.getCurrencyInstance(new Locale("en", "US"))
        .format(findMaximumPrice(stockPrices)));
```

### Complexity Analysis

- **Time Complexity:** O(N) → Each element checked once.
- **Space Complexity:** O(1) → Only one variable (`maxPrice`) is used.

### Practical Example

*An investor* checks the peak price in the last 10 days to decide the best selling opportunity.

##  3. Count Occurrences

### Problem

Count how many times a specific stock price appears.

### Java Implementation

```java
static int countOccurrences(int[] inputStockPrices, int targetPrice) {
    int counter = 0;
    for (int price : inputStockPrices) {
        if (price == targetPrice) {
            counter++;
        }
    }
    return counter;
}

// Example usage
int target = 120;
System.out.println("The target price of " +
    NumberFormat.getCurrencyInstance(new Locale("en", "US")).format(target)
    + " appears " + countOccurrences(stockPrices, target) + " times");
```

### Complexity Analysis

- **Time Complexity:** O(N) → Each element compared once.
- **Space Complexity:** O(1) → Only a single counter variable is needed.

### Practical Example

*A trader* wants to see how many times a specific threshold price occurred to understand market stability.

## 4. Cumulative Value

### Problem

Calculate cumulative stock values (running total).

### Java Implementation

```java
static ArrayList<Integer> cumulativeSum(ArrayList<Integer> inputArr) {
    ArrayList<Integer> cumulativeSumArr = new ArrayList<>();
    cumulativeSumArr.add(inputArr.get(0));

    for (int i = 1; i < inputArr.size(); i++) {
        int sum = cumulativeSumArr.get(i - 1) + inputArr.get(i);
        cumulativeSumArr.add(sum);
    }

    return cumulativeSumArr;
}

// Example usage
ArrayList<Integer> stockPricesList = new ArrayList<>(Arrays.asList(
    209, 589, 193, 204, 109, 120, 200, 390, 540, 890
));
System.out.println(cumulativeSum(stockPricesList));
```

### Complexity Analysis

- **Time Complexity:** O(N) → Each element added once.
- **Space Complexity:** O(N) → New list of size N created.

### Practical Example

*Portfolio managers* use cumulative stock value tracking to observe growth trends over a period.

------

## Summary Table

| Problem          | Time Complexity | Space Complexity | Notes             |
| ---------------- | --------------- | ---------------- | ----------------- |
| Average Price    | O(N)            | O(1)             | Iterates once     |
| Maximum Price    | O(N)            | O(1)             | Iterates once     |
| Count Occurrence | O(N)            | O(1)             | Iterates once     |
| Cumulative Value | O(N)            | O(N)             | Needs extra array |

