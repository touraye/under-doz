# String Class in Java

This is module, you will learn about the String class, different ways of creating a String, some useful String methods, and concatenations techniques. The String is primitive data type and a class in Java. We'll visit the String class and see some methods and their use cases.

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

### **Essential Methods of the String Class**

Below are some of the methods define on the String class which we can leverage in our programs:

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



As we have cover [accessing method on an object]() we will use similar approach, however we will not be creating an [instantiate of a class]().

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

### Understanding the Immutability of Strings in Java

A **String** in Java is **immutable**, meaning that once it is created, its value **cannot be changed**. Any modification to a `String` creates a **new object** instead of modifying the existing one.

Let understand the immutability of a String:

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
