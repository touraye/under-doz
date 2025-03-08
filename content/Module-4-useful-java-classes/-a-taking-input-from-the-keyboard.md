# Taking Input From The Keyboard

In this module, you’ll learn to **capture user input** directly in your Java programs. Using the console, you’ll prompt users to enter data (e.g., their name, age, or numbers), process that input, and display dynamic results. To achieve this, we’ll leverage Java’s **`Scanner` class**—a powerful tool for reading input from the keyboard, files, or strings. By the end, you’ll:

- Prompt users with clear messages.
- Use methods like `nextLine()`, `nextInt()`, and `nextDouble()` to read input.
- Transform raw input into meaningful output.

### **Scanner Class in Java**

The **`Scanner`** class in Java (part of the `java.util` package) is used to **read input** from various sources like the keyboard, files, or strings. It simplifies parsing primitive data types (e.g., `int`, `double`) and strings from input streams.

### **Key Use Cases**

1. **Reading user input** from the console (keyboard).
2. **Parsing data** from files or strings.
3. **Breaking input into tokens** (e.g., splitting a sentence into words).

Using the Scanner class:

```java
import java.util.Scanner; // import Scanner class

//To read input from the keyboard:
Scanner scanner = new Scanner(System.in);  
```

### **Read Input**

- `nextInt()`: Read an integer.
- `nextDouble()`: Read a double.
- Reading String:
  - `next()`: Read a single word (stops at whitespace).
  - `nextLine()`: Read an entire line (including spaces).

Sample code:

```java
import java.util.Scanner;  

public class Main {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  

        System.out.print("Enter your name: ");  
        String name = scanner.nextLine();  // Read a full line  

        System.out.print("Enter your age: ");  
        int age = scanner.nextInt();       // Read an integer  

        System.out.println("Hello, " + name + "! You are " + age + " years old.");  

        scanner.close(); // Always close the Scanner to free resources  
    }  
}  
```

Output:

```java
Enter your name: Alice Smith  
Enter your age: 30  
Hello, Alice Smith! You are 30 years old.  
```

#### **Reading Multiple Values**

```java
public class Main {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  

        System.out.print("Enter two numbers (separated by space): ");  
        double num1 = scanner.nextDouble();  
        double num2 = scanner.nextDouble();  

        System.out.println("Sum: " + (num1 + num2));  

        scanner.close();  
    }  
}  
```

Output: 

```java
Enter two numbers (separated by space): 5.5 3.2  
Sum: 8.7  
```

#### **Handling Words and Lines**

```java
public class Main {  
    public static void main(String[] args) {  
        Scanner scanner = new Scanner(System.in);  

        System.out.print("Enter a word: ");  
        String word = scanner.next();  // Reads until whitespace  

        scanner.nextLine(); // Consume the leftover newline character  

        System.out.print("Enter a sentence: ");  
        String sentence = scanner.nextLine();  

        System.out.println("Word: " + word);  
        System.out.println("Sentence: " + sentence);  

        scanner.close();  
    }  
}  
```

Output:

```java
Enter a word: Hello  
Enter a sentence: Java is fun!  
Word: Hello  
Sentence: Java is fun!  
```

### **Important Notes**

1. **Close the Scanner**: Always call `scanner.close()` to avoid resource leaks.
2. **Input Mismatch**: If the user enters the wrong data type (e.g., letters instead of numbers), it throws an `InputMismatchException`.
3. **Whitespace Handling**:
   - `next()` reads until the next whitespace.
   - `nextLine()` reads until the next newline (`\n`).
   - Mixing `next()`/`nextInt()` and `nextLine()` can cause issues (use an extra `nextLine()` to clear the buffer).

------

### **Best Practices**

- Use `hasNextInt()`, `hasNextDouble()`, etc., to validate input before reading.
- For file input, use `Scanner scanner = new Scanner(new File("data.txt"));` (requires exception handling).

**Summary:**

1. **Prompt users with clear messages**:
   - Display instructions (e.g., "Enter your name:") to guide input.
2. **Use methods like `nextLine()`, `nextInt()`, and `nextDouble()` to read input**:
   - `nextLine()` for strings with spaces (e.g., full names).
   - `nextInt()`/`nextDouble()` for numeric values.
3. **Transform raw input into meaningful output**:
   - Process data (e.g., calculate age, format text) and display results.