# Authentication System

**Program Description**  

This program implements a secure **user authentication system** that enforces a 3-attempt login limit to prevent unauthorized access. The system prompts users to enter a username and password, validating the credentials against predefined correct values. If the user exceeds three consecutive failed attempts, the program blocks access and terminates.  

**Key Features**:  
- **Attempt Tracking**: A counter variable tracks failed login attempts in real-time.  
- **Loop Control**: A `while` loop keeps the program running until valid credentials are entered or the attempt limit is reached.  
- **Input Validation**: Checks username/password matches and provides immediate feedback.  
- **Security Measure**: Automatically blocks the account after 3 failed attempts to deter brute-force attacks.  

**Outcome**:  
- On successful login, the user gains access with a confirmation message.  
- On failure, the program displays remaining attempts or a blocking notification.  

### **Step-by-Step Implementation Guide**

1. **Initialize Variables**
   - Store valid credentials (`username`, `password`).
   - Create a counter variable (`attempts = 0`) to track failed attempts and make it `final`.
2. **Loop Until Attempts Are Exhausted**
   - Use a `while` loop to keep the program running while `attempts < 3`.
3. **Take User Input**
   - Prompt for `username` and `password` each iteration.
4. **Validate Credentials**
   - If credentials match, grant access and **break** the loop.
   - If invalid, increment `attempts` and display an error.
5. **Block User After 3 Failed Attempts**
   - After the loop, check if `attempts == 3` and block the account.

## Resources

1. [String methods](https://github.com/touraye/under-doz/blob/main/content/Module-4-useful-java-classes/c-string-class.md)
2. [Conditional statements](https://github.com/touraye/under-doz/blob/main/content/Module-5-control-structures/c-conditional-statments.md)
3. [Iterative statements](https://github.com/touraye/under-doz/blob/main/content/Module-5-control-structures/d-iterative-statements.md)

Happy Coding!