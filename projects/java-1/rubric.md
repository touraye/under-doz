# Assignment Grading Criteria

Your project will be evaluated based on the following components. Please make sure each is properly addressed to receive full credit:

###  **1. Product Class **

- A `Product` class must be created with the following properties:
  - `productId` (int)
  - `productName` (String)
  - `productCost` (double)
- Include appropriate behaviors:
  - A constructor to initialize product data.
  - A `toString()` method to print product details in a readable format.

###  **2. VendingMachine Class & Main Method**

- You must have a `VendingMachine` class that contains the `main(String[] args)` method where the program starts.
- This class should manage vending machine operations, including loading products, handling user interaction, and generating receipts.

### **3. Array of Product Objects **

- Create an array of type `Product` with **10 slots**.
- Initialize and store **at least 10 different product instances** in the array.

###  **4. Repeated Purchase Loop **

- Implement a **loop** that allows users to:
  - View products
  - Select and purchase products multiple times
  - Choose when to exit/cancel

### **5. Clear and Detailed Prompts**

- Your program must:
  - Display a welcoming message
  - Provide clear prompts for product selection, quantity input, and exiting
  - Help the user understand how to interact with the vending machine

### **6. Cancel Option at Any Time**

- Allow the user to **exit or cancel the transaction** at any point using a special option (e.g., entering `0`).
- Upon canceling, display a **summary/receipt** if any purchase has been made.

### **7. Input Validation and Error Handling**

- Use `try-catch` blocks to prevent the program from crashing if:
  - A user inputs letters instead of numbers
  - An invalid product ID or quantity is entered
- Your program should continue running after an error is caught.

### **8. Receipt Formatting**

- After the user exits:
  - Print a receipt showing:
    - Number of items purchased
    - Total amount spent (formatted with **GMD** and **2 decimal places**)
    - Date and time of transaction
- The output should look clean and professional.

### **9. Code Review and Documentation**

- Include comments explaining each major block of your code.
- Be ready to explain:
  - What each method or section does
  - Why you structured it that way
  - How your loop, array, and exception handling work



