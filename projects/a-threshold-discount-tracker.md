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

------

Happy Coding!