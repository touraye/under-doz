# String Class

This is module, you learn about how to use a String, concatenations techniques with String, some useful String methods, and the different ways of creating a String. The String is primitive data type and a class in Java. We'll visit the String class and see some methods and their use cases.

## **1. String Fundamentals**

- **Non-Primitive Type**: Strings are objects (reference type) with built-in methods
- **Immutability**: Strings cannot be changed after creation (new Strings are created during operations)
- **String Pool**: Java optimizes memory usage by reusing common string literals

## **2. String Concatenation**
Combining strings with variables/values using `+` operator:

```java
public class Employee {
    public static void main(String[] args) {
        String firstName = "Ahmed";
        String lastName = "Dicko";
        int age = 18;
        double salary = 12000;
        String designation = "Software Engineer";
        
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
First Name: Ahmed
Last Name: Dicko
Age: 18
Salary: GMD12000.0
Designation: Software Engineer
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





# String Class in Java

In Java, a **String** is an **immutable** sequence of characters. It is a built-in class in `java.lang` and is used to represent **textual data**. Strings in Java are **objects**, not primitive data types.

**Key Features of String:**

- **Immutable:** Once created, a String **cannot** be changed.
- **Stored in String Pool:** Java optimizes memory by storing String literals in a **shared pool**.
- **Implements Comparable & CharSequence:** Supports comparison and character operations.

------

### **Ways to Create a String in Java**

There are **two main ways** to create a `String`:

#### **(A) Using String Literals (Stored in String Pool)**

```java
String s1 = "Hello"; // Stored in String Pool
String s2 = "Hello"; // Points to the same object in the pool
```

 **Efficient:** Uses a shared memory pool to save space.

#### **(B) Using `new` Keyword (Stored in Heap Memory)**

```java
String s3 = new String("Hello"); // New object in Heap
String s4 = new String("Hello"); // Different object in Heap
```

 **Less Efficient:** Creates **a new object** each time, even if the value is the same.

**Difference:**

| **Creation Type** | **Stored In** | **Memory Optimization**     |
| ----------------- | ------------- | --------------------------- |
| String Literal    | String Pool   | Yes, reuses existing values |
| `new` Keyword     | Heap Memory   | No, creates a new object    |

------

### ** Essential Methods of the String Class**

Here’s a table of **commonly used methods**:

| **Method**              | **Description**                                | **Example**                                  |
| ----------------------- | ---------------------------------------------- | -------------------------------------------- |
| `length()`              | Returns the length of the string.              | `"Java".length()` → `4`                      |
| `charAt(index)`         | Returns character at a specific index.         | `"Java".charAt(1)` → `'a'`                   |
| `substring(start, end)` | Extracts a substring.                          | `"Hello".substring(1, 4)` → `"ell"`          |
| `toUpperCase()`         | Converts to uppercase.                         | `"java".toUpperCase()` → `"JAVA"`            |
| `toLowerCase()`         | Converts to lowercase.                         | `"JAVA".toLowerCase()` → `"java"`            |
| `trim()`                | Removes leading & trailing spaces.             | `"  Hello  ".trim()` → `"Hello"`             |
| `replace(old, new)`     | Replaces characters.                           | `"cat".replace('c', 'b')` → `"bat"`          |
| `equals(str)`           | Checks if two strings are equal.               | `"Java".equals("java")` → `false`            |
| `equalsIgnoreCase(str)` | Case-insensitive equality check.               | `"Java".equalsIgnoreCase("java")` → `true`   |
| `startsWith(prefix)`    | Checks if a string starts with a given prefix. | `"Hello".startsWith("He")` → `true`          |
| `endsWith(suffix)`      | Checks if a string ends with a given suffix.   | `"Hello".endsWith("lo")` → `true`            |
| `contains(str)`         | Checks if the string contains another string.  | `"Java".contains("av")` → `true`             |
| `split(regex)`          | Splits a string based on regex.                | `"a,b,c".split(",")` → `["a", "b", "c"]`     |
| `indexOf(str)`          | Finds the first occurrence of a string.        | `"banana".indexOf("na")` → `2`               |
| `lastIndexOf(str)`      | Finds the last occurrence of a string.         | `"banana".lastIndexOf("na")` → `4`           |
| `concat(str)`           | Joins two strings.                             | `"Hello".concat(" World")` → `"Hello World"` |

------

### **Example: Using String Methods**

```java
public class StringExample {
    public static void main(String[] args) {
        String text = "  Java Programming  ";

        System.out.println("Length: " + text.length()); // 19
        System.out.println("Trimmed: " + text.trim()); // "Java Programming"
        System.out.println("Uppercase: " + text.toUpperCase()); // "  JAVA PROGRAMMING  "
        System.out.println("Substring: " + text.substring(2, 6)); // "Java"
        System.out.println("Replaced: " + text.replace("Java", "Python")); // "  Python Programming  "
        System.out.println("Contains 'gram': " + text.contains("gram")); // true
    }
}
```

------

### Understanding the Immutability of Strings in Java

A **String** in Java is **immutable**, meaning that once it is created, its value **cannot be changed**. Any modification to a `String` creates a **new object** instead of modifying the existing one.

#### **Example: Demonstrating Immutability**

```java
public class StringImmutableExample {
    public static void main(String[] args) {
        String str = "Hello";
        str.concat(" World"); // This does NOT modify str
        System.out.println(str); // Output: "Hello"

        // The correct way to modify a string
        str = str.concat(" World"); // A new object is created and assigned to str
        System.out.println(str); // Output: "Hello World"
    }
}
```

**Explanation:**

- The statement `str.concat(" World")` **creates a new object**, but `str` still points to `"Hello"`.
- To **actually modify** `str`, we must **reassign** it: `str = str.concat(" World");`.

#### **Why is String Immutable?**

1. **Memory Optimization:** Strings are stored in the **String Pool**, allowing reuse.
2. **Thread-Safety:** Since Strings **cannot change**, multiple threads can use them without issues.
3. **Security:** Used in **passwords, URLs, and database queries**, preventing unintended modifications.

------

### **String Implements Comparable & CharSequence**

#### **(A) String Implements `Comparable<String>`**

The `String` class implements the `Comparable<String>` interface, meaning **Strings can be compared using `compareTo()`**.

**`compareTo()` Method:**

- Returns `0` if strings are **equal**.
- Returns a **negative value** if the first string is **lexicographically smaller**.
- Returns a **positive value** if the first string is **lexicographically greater**.

```java
public class StringComparableExample {
    public static void main(String[] args) {
        String str1 = "Apple";
        String str2 = "Banana";

        System.out.println(str1.compareTo(str2)); // Output: -1 ("Apple" is smaller)
        System.out.println(str2.compareTo(str1)); // Output: 1 ("Banana" is greater)
        System.out.println(str1.compareTo("Apple")); // Output: 0 (Equal strings)
    }
}
```

**Explanation:**

- `"Apple".compareTo("Banana")` returns **-1** because `"Apple"` comes **before** `"Banana"` in dictionary order.
- `"Banana".compareTo("Apple")` returns **1** because `"Banana"` is **after** `"Apple"`.
- If two strings are equal, `compareTo()` returns `0`.

------

#### **(B) String Implements `CharSequence`**

The `CharSequence` interface represents a **read-only sequence of characters**, and `String` is one of its implementations.

**Other Implementations of `CharSequence`:**

1. `String`
2. `StringBuilder`
3. `StringBuffer`
4. `CharBuffer`

Since `String` implements `CharSequence`, it can be used where a `CharSequence` is expected.

**Example: Using `CharSequence` Methods**

```java
public class CharSequenceExample {
    public static void main(String[] args) {
        CharSequence cs = "Hello World"; // String as CharSequence

        System.out.println(cs.length()); // Output: 11
        System.out.println(cs.charAt(0)); // Output: 'H'
        System.out.println(cs.subSequence(0, 5)); // Output: "Hello"
    }
}
```

**Explanation:**

- `length()` → Returns the number of characters.
- `charAt(index)` → Returns a character at a given position.
- `subSequence(start, end)` → Extracts a **portion** of the sequence.

------

### **Summary**

| **Concept**                | **Description**                                | **Example**                                                |
| -------------------------- | ---------------------------------------------- | ---------------------------------------------------------- |
| **Immutability**           | Strings **cannot** be modified after creation. | `String s = "Hello"; s.concat(" World"); // Still "Hello"` |
| **Comparable Interface**   | Allows comparing strings lexicographically.    | `"Apple".compareTo("Banana") // -1`                        |
| **CharSequence Interface** | Provides a read-only character sequence.       | `cs.length(), cs.charAt(0)`                                |

------

Java's **String immutability** ensures **security, efficiency, and reliability**, while implementing `Comparable` and `CharSequence` makes it **flexible** for comparisons and character manipulation.
