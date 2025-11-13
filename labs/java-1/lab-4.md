# Calculator Program

**Lab 4:**

### Objective:

In this lab, you will create a **simple calculator** program in Java using the `switch` statement and **functions** (methods). The program will:

- Accept user input: two numbers and an operator
- Perform the selected operation (e.g., addition, subtraction, multiplication, etc.)
- Output the result

This exercise reinforces the use of:

- `switch` statements
- Modular programming through **functions**
- Conditional logic and user input

------

### Lab Requirements

You are expected to:

1. Prompt the user to input **two numeric values** and an **operator** (`+`, `-`, `*`, `/`, `%`)
2. Use a `switch` statement to determine the operation based on the operator input
3. For **each operation**, call a **function** (method) that:
   - Takes three arguments: `val1`, `opt`, and `val2`
   - Performs the correct calculation
   - Prints the result clearly to the console

------

### Code Structure Overview

Here’s a sample outline to guide your implementation:

```java
// Step 1: Import scanner
import java.util.Scanner;

public class CalculatorLab {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);

        // Step 2: Take input
        System.out.print("Enter first number: ");
        // assign user value to a variable

        System.out.print("Enter an operator (+, -, *, /, %): ");
         // assign operator to a variable

        System.out.print("Enter second number: ");
        // assign user value to a variable

        // Step 3: Use switch to handle operation
        switch (opt) {
           	// all of your cases goes here
            default:
                System.out.println("Invalid operator!");
        }

        in.close(); // close scanner
    }

    // CALCULATION:
    public static void addition(parameter1, parameter2) {
        // do you calculations
    }
    // other functions:
}
```

------

### Instructions:

1. **Setup Scanner** to read input from the user.
2. Prompt the user to enter:
   - First number
   - An operator (`+`, `-`, `*`, `/`, `%`)
   - Second number
3. Use a **`switch` statement** in `main()` to evaluate which operator was chosen.
4. **Call a function** (e.g., `calculate(val1, opt, val2)`) that will:
   - Perform the correct computation
   - Handle errors like **division by zero**
   - Print the result in a clean format
5. Test your program with different operators and values.

------

### Final Output Sample

```
Enter first number: 10
Enter an operator (+, -, *, /, %): *
Enter second number: 5
Result: 10.0 * 5.0 = 50.0
```

------

References:

[functions](https://github.com/touraye/under-doz/tree/main/content/Module-7-functions)

Happy coding!
