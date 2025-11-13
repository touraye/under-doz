# Java Math Class

## **Overview**
The `Math` class (from `java.lang` package) provides **static methods** for common mathematical operations. Key features:
- No need to create objects (direct class access)
- Handles basic and advanced calculations
- Supports trigonometry, exponents, rounding, and more
- Automatically handles special values (`NaN`, infinity)

---

## **Core Methods & Examples**

### **1. Comparison Operations**
```java
// Find minimum/maximum between two values
int minVal = Math.min(15, 40);     // 15
double maxVal = Math.max(3.7, 9.2); // 9.2

System.out.println("Smallest: " + Math.min(-5, 5));   // -5
System.out.println("Largest: " + Math.max(100, 200)); // 200
```

### **2. Powers & Roots**
```java
// Square root and exponents
double root = Math.sqrt(25);        // 5.0
double power = Math.pow(2, 3);       // 8.0 (2³)
double cubeRoot = Math.pow(27, 1/3.0); // 3.0

System.out.println("√144: " + Math.sqrt(144));      // 12.0
System.out.println("5⁴: " + Math.pow(5, 4));        // 625.0
```

### **3. Absolute Value & Sign**
```java
// Absolute values
int absInt = Math.abs(-15);         // 15
double absDouble = Math.abs(-45.67); // 45.67

System.out.println("|−7.5|: " + Math.abs(-7.5));    // 7.5
```

### **4. Rounding Operations**
```java
// Different rounding methods
long rounded = Math.round(15.3);    // 15
double ceilVal = Math.ceil(4.2);    // 5.0
double floorVal = Math.floor(4.9);  // 4.0

System.out.println("Round 8.7: " + Math.round(8.7)); // 9
System.out.println("Ceil 3.1: " + Math.ceil(3.1));   // 4.0
System.out.println("Floor 6.9: " + Math.floor(6.9)); // 6.0
```

### **5. Random Numbers**
```java
// Generate random double between 0.0 (inclusive) and 1.0 (exclusive)
double random = Math.random();  

// Generate random integer between 1-100
int diceRoll = (int) (Math.random() * 100) + 1;
```

### **6. Logarithmic & Trigonometric**
```java
// Natural logarithm and trigonometry
double logVal = Math.log(Math.E);      // 1.0 (ln(e))
double sinVal = Math.sin(Math.PI/2);   // 1.0 (sin(90°))
```

---

## **Quick Reference Table**

| Method                     | Parameters    | Return Type | Example Usage        | Result        |
| -------------------------- | ------------- | ----------- | -------------------- | ------------- |
| `Math.min(a, b)`           | Two numbers   | Same type   | `Math.min(-5, 3)`    | -5            |
| `Math.max(a, b)`           | Two numbers   | Same type   | `Math.max(7.2, 9.5)` | 9.5           |
| `Math.sqrt(x)`             | Single number | double      | `Math.sqrt(16)`      | 4.0           |
| `Math.pow(base, exponent)` | Two numbers   | double      | `Math.pow(3, 4)`     | 81.0          |
| `Math.abs(x)`              | Single number | Same type   | `Math.abs(-12.5)`    | 12.5          |
| `Math.round(x)`            | float/double  | int/long    | `Math.round(15.7)`   | 16            |
| `Math.ceil(x)`             | double        | double      | `Math.ceil(3.1)`     | 4.0           |
| `Math.floor(x)`            | double        | double      | `Math.floor(6.9)`    | 6.0           |
| `Math.random()`            | None          | double      | `Math.random()`      | 0.0 ≤ x < 1.0 |

---

## **Key Notes & Best Practices**
1. **Data Type Handling**:
   - Most methods return `double` unless specified
   - Use casting for specific types: `(int) Math.round(15.7)`

2. **Edge Cases**:
   ```java
   Math.sqrt(-1)   // Returns NaN
   Math.pow(0, 0)  // Returns 1.0 (special case)
   Math.abs(Integer.MIN_VALUE) // Returns negative due to overflow
   ```

3. **Precision Matters**:
   - For financial calculations, prefer `BigDecimal`
   - Floating-point approximations: `Math.sqrt(2)` ≈ 1.41421356

4. **Performance**:
   - Math operations are optimized at hardware level
   - Cache repeated calculations (e.g., store `Math.PI` in a variable)

---

## **Practical Use Cases**
1. **Game Development**:
   ```java
   // Calculate damage range: 50-150
   int damage = (int) (Math.random() * 100) + 50;
   ```

2. **Data Analysis**:
   ```java
   // Calculate standard deviation
   double variance = 25;
   double stdDev = Math.sqrt(variance); // 5.0
   ```

3. **Geometry Calculations**:
   
   ```java
   // Circle area calculation
   double radius = 7.5;
   double area = Math.PI * Math.pow(radius, 2);
   ```
