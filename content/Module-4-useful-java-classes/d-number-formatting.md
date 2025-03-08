# # Number Formatting in Java

## **1. Decimal Formatting with `DecimalFormat`**
**Class**: `java.text.DecimalFormat` (requires import)  
**Purpose**: Custom numeric formatting using pattern strings

### **Pattern Symbols**
- `0` - Enforces digit (shows trailing zeros)
- `#` - Optional digit (omits leading/trailing zeros)
- `.` - Decimal separator
- `,` - Grouping separator

### **Basic Usage**
```java
import java.text.DecimalFormat;

public class DecimalFormatExample {
    public static void main(String[] args) {
        double unit = 49.908000000000006;
        double amount = 2300.02829;
        
        // Pattern 1: Fixed two decimal places
        DecimalFormat strictFormat = new DecimalFormat("0.00");
        System.out.println(strictFormat.format(unit));    // 49.91
        System.out.println(strictFormat.format(amount));  // 2300.03

        // Pattern 2: Flexible formatting
        DecimalFormat flexibleFormat = new DecimalFormat("###,###.###");
        System.out.println(flexibleFormat.format(1200.00));  // 1,200
        System.out.println(flexibleFormat.format(1200.03));  // 1,200.03
    }
}
```

### **Advanced Features**
- **Rounding Control**: Defaults to `RoundingMode.HALF_EVEN`
- **Currency Symbols**: Can be added directly to patterns (`"¤#,##0.00"`)
- **Percentage Formatting**: Use `%` symbol in pattern

---

## **2. Currency Formatting**

### **Method 1: `String.format()`**
**Best for**: Quick formatting with standard patterns

```java
public class CurrencyFormatting {
    public static void main(String[] args) {
        double amount = 1200;
        
        // Basic currency formatting
        System.out.println(String.format("Amount: GMD%,.2f", amount));  // GMD1,200.00
        
        // Localized formatting
        System.out.println(String.format("USD: $%,.2f", amount));       // USD: $1,200.00
        System.out.println(String.format("EUR: €%,.2f", amount));       // EUR: €1,200.00
    }
}
```

### **Method 2: `NumberFormat` (Recommended)**
**Class**: `java.text.NumberFormat`  
**Advantages**: Automatic localization and proper currency handling

```java
import java.text.NumberFormat;
import java.util.Locale;

public class ProperCurrencyFormatting {
    public static void main(String[] args) {
        double amount = 1200.5;
        
        // Default locale formatting
        NumberFormat localFormat = NumberFormat.getCurrencyInstance();
        System.out.println(localFormat.format(amount));  // $1,200.50 (US locale)
        
        // Specific currency formatting
        NumberFormat gambianFormat = NumberFormat.getCurrencyInstance(new Locale("en", "GM"));
        gambianFormat.setCurrency(java.util.Currency.getInstance("GMD"));
        System.out.println(gambianFormat.format(amount)); // GMD1,200.50
    }
}
```

---

## **3. Critical Considerations**

1. **Precision Issues**:
   ```java
   // Floating-point precision problem
   System.out.println(0.1 + 0.2);  // 0.30000000000000004
   
   // Solution: Use BigDecimal for financial calculations
   BigDecimal exactAmount = new BigDecimal("1200.00");
   ```

2. **Pattern Validation**:
   - Invalid patterns throw `IllegalArgumentException`
   - Always test patterns with edge cases

3. **Locale Differences**:
   - US: 1,000.00 vs Europe: 1.000,00
   - Use locale-specific patterns for international applications

4. **Custom Formatting**:
   ```java
   // Combine text and formatting
   DecimalFormat customFormat = new DecimalFormat("'Balance:' ###,##0.00 'units'");
   System.out.println(customFormat.format(1500.75));  // Balance: 1,500.75 units
   ```

---

## **Comparison Table**

| Method            | Pros                         | Cons                        | Best Use Case              |
| ----------------- | ---------------------------- | --------------------------- | -------------------------- |
| `DecimalFormat`   | Highly customizable patterns | Requires pattern knowledge  | Custom numeric displays    |
| `String.format()` | Simple syntax                | Limited customization       | Quick formatting           |
| `NumberFormat`    | Automatic localization       | Slightly more complex setup | International applications |
| `BigDecimal`      | Exact precision              | Verbose syntax              | Financial calculations     |

---

## **Real-World Example: E-Commerce System**
```java
import java.text.NumberFormat;
import java.util.Locale;

public class ShoppingCart {
    public static void main(String[] args) {
        double subtotal = 1234.567;
        double tax = subtotal * 0.075;
        double total = subtotal + tax;
        
        NumberFormat currency = NumberFormat.getCurrencyInstance(Locale.US);
        
        System.out.println("Subtotal: " + currency.format(subtotal));  // $1,234.57
        System.out.println("Tax (7.5%): " + currency.format(tax));     // $92.59
        System.out.println("Total: " + currency.format(total));       // $1,327.16
    }
}
```

**Key Takeaways**:
- Choose formatting method based on use case
- Always consider localization requirements
- For monetary values, prefer `BigDecimal` over `double`
- Test formatting with various edge cases (zeros, large numbers, fractions)
