# Exercise Two

Here are **five hands-on programming exercises** based on the `if`, `if-else`, `if-else if-else`, `nested if`, and `switch` statements. These exercises will help reinforce conditional logic in Java.

### **1. Age Category Finder (If-Else Statement)**

**Problem:**
 Write a Java program that asks the user to enter their age and determines their category:

- If age is **less than 12**, print `"You are a child."`
- If age is **between 12 and 19**, print `"You are a teenager."`
- If age is **20 or older**, print `"You are an adult."`

**Modify the program to reject negative numbers and ages over 120.**

------

### **2. Leap Year Checker (If-Else If-Else Statement)**

**Problem:**
 A year is a **leap year** if:

1. It is **divisible by 4**
2. But **not divisible by 100**, unless it is also **divisible by 400**

Write a Java program that asks the user for a year and checks if it is a leap year.
 **Example:**

- Input: `2024` → Output: `"2024 is a leap year."`
- Input: `2100` → Output: `"2100 is NOT a leap year."`

------

### **3. Password Strength Checker (Nested If Statement)**

**Problem:**
 Write a Java program that asks a user to enter a password and checks its strength:

- If the password is **less than 8 characters**, print `"Weak password. Must be at least 8 characters."`

- If it is 

  8 or more characters

  , check if it 

  contains a digit

  :

  - If yes, print `"Strong password."`
  - If no, print `"Moderate password. Try adding a number for extra security."`

------

### **4. Grade Calculator (Switch Statement)**

**Problem:**
 Write a Java program that takes a student's score (0-100) and prints their grade using a switch statement:

- `90-100` → `"Grade: A"`
- `80-89` → `"Grade: B"`
- `70-79` → `"Grade: C"`
- `60-69` → `"Grade: D"`
- `Below 60` → `"Grade: F"`

**Hint:** Convert the score into a range by using `score / 10` as the switch condition.

------

### **5. ATM Withdrawal System (If-Else & Switch Statement)**

**Problem:**
 Write a Java program that simulates an ATM withdrawal system:

1. Ask the user to enter their **account balance**.

2. Ask the user how much they want to withdraw.

3. Check conditions:

   - If the withdrawal amount **exceeds the balance**, print `"Insufficient funds!"`
   - If the withdrawal amount is **less than or equal to balance**, proceed to the **next step**.

4. Use a 

   switch statement

    to check the withdrawal amount:

   - If it’s a **multiple of 10**, allow the transaction and print the new balance.
   - Otherwise, print `"Withdrawal must be in multiples of 10!"`

