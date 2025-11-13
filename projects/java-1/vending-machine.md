# Java-1 Final Project

##  **Java Project: Building a Vending Machine**

###  **Project Objective**

Using the Java skills you’ve developed so far, build a simple **Vending Machine application** that allows users to select and buy products, handles payments, and prints a well-formatted receipt.

------

##  **Project Requirements**

1. **Create a `Product` class**
   - Each product must have:
     - `productId` (int)
     - `productName` (String)
     - `productCost` (double)
   - Add a `toString()` method to return a readable string of the product.
   - You can use a constructor to initialize product details.
2. **Create a `VendingMachine` class**
   - This should contain the `main()` method.
   - Inside this class:
     - Create an **array of 10 `Product` objects** and load it with sample products.
     - Display a welcoming message and show the list of all products.
3. **Buying Products**
   - The user should be able to select multiple products and quantities.
   - The system should calculate the **running total**.
   - User can **exit/cancel** at any time, and the program should print a **summary/receipt**.
4. **Receipt & Output**
   - When the user exits:
     - Show number of products purchased.
     - Show total cost in Dalasis (GMD) with **proper currency formatting**.
     - Include current date/time in the receipt.
5. **Error Handling**
   - The program should not crash if invalid inputs are entered (e.g., entering a string instead of a number).
   - Use loops and `try-catch` to ensure input validation.

## **Guide on how to structure you project:**

### Create the `Product` Class

```java
public class Product {
    int productId;
    String productName;
    double productCost;

    public Product(int productId, String productName, double productCost) {
        this.productId = productId;
        this.productName = productName;
        this.productCost = productCost;
    }

    @Override
    public String toString() {
        return productId + " - " + productName + " | GMD " + String.format("%.2f", productCost);
    }
}
```

### Create the `VendingMachine` Class with `main()`

```java
public class VendingMachine {
    public static void main(String[] args) {
        // your codes go here
    }
}
```

Happy coding!

