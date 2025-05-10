# Threshold Discount Tracker

**Background:**
 A local shop owner wants to maintain a promotional strategy that rewards customers in a recurring manner. This strategy is designed to increase customer loyalty and incentivize ongoing purchases, especially after reaching specific sales milestones.

**Problem Description:**
 The shop owner wants a Java-based sales tracking application that continuously monitors total sales and applies a 15% discount to the next 5 customers every time cumulative sales exceed another 1,000 Dalasis.

#### Functional Requirements:

1. The program should:
   - Prompt the shop owner to enter the amount of each sale.
   - Continuously accumulate total sales in Dalasis.
   - Detect every time total cumulative sales surpass a new 1,000-Dalasi threshold, e.g., 1,000, 2,000, 3,000, etc.
   - For each new 1,000-Dalasi threshold passed, automatically apply a 15% discount to the next 5 customers.
2. For each customer eligible for a discount:
   - Display:
     - The original sale amount.
     - The discount amount.
     - The final sale price after the discount.
3. After the 5 discounted customers for a given threshold are served, the program should:
   - Resume tracking normally until the next multiple of 1,000 Dalasis is reached.
   - Then again apply discounts to the next 5 customers.
4. The program should continue indefinitely until the shop owner manually terminates it by entering `'exit'`.

#### Constraints:

- The program must rely only on primitive types, conditionals, loops, and user input.
- Ensure all numeric inputs are validated (no negative or invalid numbers).
- Monetary values should be displayed in Dalasis and formatted to two decimal places.

#### Objective:

To provide a **reliable and repetitive discount management system** that:

- Detects every 1,000 Dalasis milestone in total sales.
- Applies a 15% discount to the next 5 customers after each threshold.
- Maintains simplicity in logic and user experience, allowing the shop owner to operate the program easily without technical knowledge.

Happy Coding!

------

###  Assignment: Improving Threshold Discount Tracker Program

You've already made great progress on the discount sales program. Here's a summary of what your current implementation achieves:

- ✅ The program can now execute continuously, allowing users to keep making sales entries until they choose to quit.
- ✅ User input for sales amounts can be converted to `double` using a wrapper class.
- ✅ The program calculates total sales and, once a sales threshold is reached (e.g., 1000 Dalasis), it enters a discount loop.
- ✅ In this discount loop, a 15% discount is applied to the next five customers. Afterward, the loop exits.
- ✅ Once the discount loop ends, the following variables are reset: `thresholdReached = false`, `discountedCustomerCount = 0`, and `tempTotalSales = 0`.
- ✅ The program correctly checks whether the sales threshold has been reached before applying any discounts.

------

### ⚠️ However, the program still has some flaws that need fixing:

1. ❌ The 15% discount is not properly **calculated and applied**.
   - When a customer is eligible for a discount, the sale should be reduced by 15% before being added to the total sales.
   - For example, if a sale is 200 Dalasis, the program should apply the discount (15% of 200 = 30) and only add **170** to the total.
2. ❌ The program is not **user-friendly** when printing messages related to the discount.
   - It should clearly inform the user when a discount is applied, how much the discount is, and what the final sale amount is.
   - There is a comment near the discount section indicating where a helpful message should be printed. Use that spot and include the proper variables.
3. ❌ The program crashes if the user enters any character other than `"q"` or a valid number.
   - For instance, inputting `"hello"` causes an `InputMismatchException`. This can be fixed by handling input exceptions gracefully using a `try-catch` block, as discussed in the course materials.

------

### ✅ Your assignment will be graded based on the following criteria:

1. **Exception Handling**
   - The program must not crash if the user inputs something other than `"q"` or a number.
   - You must handle invalid input and print a helpful error message.
2. **Correct Discount Calculation**
   - The 15% discount should be calculated accurately and subtracted from the original sale.
3. **Proper Discount Application**
   - Only the **first five customers** after each 1000-Dalasi threshold should receive the discount.
4. **Clear and Concise Output**
   - Your program should clearly communicate to the user when a discount is applied, how much the discount is, and what the final sale amount is.
   - Avoid vague or overly technical messages. Prioritize clarity and readability.

The Working is here incase your are left behind:

```java
Scanner input = new Scanner(System.in);
        double totalSales = 0;
        boolean threshold = false;
        int discountedCustomers = 0;
        double tempTotalSales = 0;

        System.out.println("=== Shop Sales Tracker ===");

        while (true) {
            System.out.print("Enter sales: ");
            String action = input.next();

            //terminate the program
            if (action.equals("q")) {
                System.out.println("\nProgram ended by the shop owner.");
                break;
            }

            // change user input from String to double:
            double sale = Double.parseDouble(action);

            tempTotalSales += sale; // accumulate temp sales

            //apply discount
            if (threshold && discountedCustomers <= 5) {
                double discount = sale * 0.15; // calculate 15 percent discount
                double discountedSale = sale - discount; // deduct discount from the original price
                totalSales += discountedSale; // add discounted sales to total sales
                discountedCustomers++; // increment the discounted customer count
                System.out.println("Total Sales: GMD" +totalSales);
                System.out.println(" ======== APPLYING DISCOUNT ========");
                System.out.printf("Discounted Customer %d: Original = GMD%.2f, Discount = GMD%.2f, Final = GMD%.2f\n",
                        discountedCustomers, sale, discount, discountedSale);
                System.out.println();

                //check for discount limit
                if (discountedCustomers == 5){
                    threshold = false; // set the threshold to false
                    discountedCustomers = 0; // reset discounted customer
                    tempTotalSales = 0; // reset tem total sale
                    System.out.println("The First Five Customers Has Reached <<<<\n");
                    System.out
                            .println("Temp sales: GMD" +tempTotalSales);
                }
            }

            //change weather threshold has reached
            if (!threshold && tempTotalSales >= 1000){
                threshold = true;
                totalSales += tempTotalSales; // add the accumulated temp total sales to total sales
                System.out.println("\n>>> Total sales reached D1000! Applying 15% discount to next 5 customers.\n");
            }

            //if (tempTotalSales > 0) totalSales += tempTotalSales;
            System.out.println("End of total sales: " +totalSales);
        }

        input.close(); // close the scanner

        System.out.println("******* REPORT *******");
        System.out.println("Total Sales: GMD" +totalSales);
        System.out.println("Total Temp Sales: GMD" +tempTotalSales);}
```

