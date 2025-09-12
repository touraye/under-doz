

------

### 🔢 **Objective**

Keep asking the user to guess a number until they guess the correct one.

------

### ✅ **Step-by-Step Guide**

#### **Step 1: Import Scanner**

- This allows the program to read user input from the console.

```java
import java.util.Scanner;
```

------

#### **Step 2: Initialize Variables**

- Create a `Scanner` object to read input.
- Set a secret number (e.g., `7`).
- Initialize a `guess` variable with a value that is definitely **not** the secret number.

```java
Scanner scanner = new Scanner(System.in);
int secretNumber = 7;
int guess = -1; // Starting with a wrong guess
```

------

#### **Step 3: Create the `while` Loop**

- Loop continues **as long as** the guess is not equal to the secret number.

```java
while (guess != secretNumber) {
    // loop body
}
```

------

#### **Step 4: Ask for User Input Inside the Loop**

- Prompt the user to guess a number.
- Read and store the guess.

```java
System.out.print("Guess the number (1-10): ");
guess = scanner.nextInt();
```

------

#### **Step 5: Give Feedback if Guess is Incorrect**

- If the guess is wrong, tell the user to try again.

```java
if (guess != secretNumber) {
    System.out.println("Wrong! Try again.");
}
```

------

#### **Step 6: Congratulate the User When They Guess Correctly**

- Once the loop exits (i.e., the guess is correct), print a success message.

```java
System.out.println("Correct! You guessed it.");
```

------

### ✅ **Final Tip**

Emphasize:

- **Condition checking happens before** the loop body runs.
- The loop ensures repeated execution **until** the correct guess is entered.

------

Would you like this turned into a printable one-pager or slide?