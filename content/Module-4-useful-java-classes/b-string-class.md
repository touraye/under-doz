# Some Useful Java Classes

Here's a revised and organized version of your String manipulation guide with corrections and improved explanations:

---

# **String Manipulation in Java**

## **1. String Fundamentals**
- **Non-Primitive Type**: Strings are objects (reference type) with built-in methods
- **Immutability**: Strings cannot be changed after creation (new Strings are created during operations)
- **String Pool**: Java optimizes memory usage by reusing common string literals

## **2. String Concatenation**
Combining strings with variables/values using `+` operator:

```java
public class Employee {
    public static void main(String[] args) {
        String firstName = "Binta";
        String lastName = "Bah";
        int age = 22;
        double salary = 12000;
        String designation = "Account General";
        
        System.out.println("Employee Details:");
        System.out.println("First Name: " + firstName);
        System.out.println("Last Name: " + lastName);
        System.out.println("Age: " + age);
        System.out.println("Salary: GMD" + salary);
        System.out.println("Designation: " + designation);
    }
}
```

**Output**:
```
Employee Details:
First Name: Binta
Last Name: Bah
Age: 22
Salary: GMD12000.0
Designation: Account General
```

## **3. Creating Strings**
Two creation methods with important differences:

```java
public class StringCreation {
    public static void main(String[] args) {
        // Using 'new' - creates new object in heap memory
        String str1 = new String("Java Strings");
        
        // Using literal - reuses from string pool
        String str2 = "More efficient creation"; 
    }
}
```

**Key Difference**:
- `new` forces new object creation
- Literals reuse existing pool objects

## **4. Essential String Methods**
Common methods with examples:

```java
public class StringMethods {
    public static void main(String[] args) {
        String str = "Programming";
        
        System.out.println("Length: " + str.length());
        System.out.println("Is empty? " + str.isEmpty());
        System.out.println("Character at index 5: " + str.charAt(5));
        System.out.println("Contains 'gram'? " + str.contains("gram"));
        System.out.println("Uppercase: " + str.toUpperCase());
        System.out.println("Lowercase: " + str.toLowerCase());
        System.out.println("Equals 'programming'? " + str.equals("programming"));
        System.out.println("Equals ignore case: " + str.equalsIgnoreCase("programming"));
        System.out.println("Substring (0-4): " + str.substring(0, 4));
    }
}
```

**Output**:
```
Length: 11
Is empty? false
Character at index 5: a
Contains 'gram'? true
Uppercase: PROGRAMMING
Lowercase: programming
Equals 'programming'? false
Equals ignore case: true
Substring (0-4): Prog
```

## **5. String Method Reference Table**

| Method                    | Return Type | Description                                                 |
| ------------------------- | ----------- | ----------------------------------------------------------- |
| `length()`                | int         | Returns number of characters                                |
| `isEmpty()`               | boolean     | Returns true if length is 0                                 |
| `charAt(index)`           | char        | Returns character at specified index (0-based)              |
| `contains(sequence)`      | boolean     | Checks if string contains specified character sequence      |
| `toUpperCase()`           | String      | Returns new uppercase string                                |
| `toLowerCase()`           | String      | Returns new lowercase string                                |
| `equals(other)`           | boolean     | Case-sensitive string comparison                            |
| `equalsIgnoreCase(other)` | boolean     | Case-insensitive string comparison                          |
| `substring(start, end)`   | String      | Returns substring from start (inclusive) to end (exclusive) |

## **6. Important Notes**
1. **Method Chaining**: Combine multiple methods:  
   `str.trim().toLowerCase().substring(0,5)`
2. **Escape Characters**: Use `\"` for quotes, `\\` for backslash
3. **Comparison**: Always use `equals()` instead of `==` for content comparison
4. **Immutability**: Operations return new strings rather than modifying original
5. **Null Safety**: Check for `null` before calling methods to avoid exceptions

**Example of Method Chaining**:
```java
String input = "   Hello World  ";
String result = input.trim().toUpperCase().substring(0,5);
System.out.println(result);  // HELLO
```
