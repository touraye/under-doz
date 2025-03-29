# Date and Time Handling in Java

## **1. Overview**
Java offers two generations of date/time APIs:
- **Legacy Classes**: `Date` and `Calendar` (from Java 1.0/1.1)
- **Modern API**: `java.time` package (Java 8+, JSR 310)

**Best Practice**: Prefer the modern `java.time` API for new projects due to:
- Immutable objects (thread-safe)
- Clearer method names
- Better time zone handling
- Comprehensive date/time operations

---

## **2. Legacy Date/Time Classes**

### **2.1 `Date` Class**
Basic timestamp representation (milliseconds since epoch)

```java
import java.util.Date;

public class LegacyDateExample {
    public static void main(String[] args) {
        Date now = new Date();
        System.out.println("Default format: " + now); 
        // Tue Mar 21 07:55:51 PDT 2023
        
        System.out.println("Locale format: " + now.toLocaleString());
        // Mar 21, 2023, 7:55:51 AM
    }
}
```

**Limitations**:
- Mutable (not thread-safe)
- Most methods deprecated
- Poor time zone support

---

### **2.2 `Calendar` Class**
Provides date manipulation capabilities

```java
import java.util.Calendar;
import java.util.Date;

public class CalendarExample {
    public static void main(String[] args) {
        Calendar calendar = Calendar.getInstance();
        
        // Set to June 12, 2021 (month is 0-based)
        calendar.set(2021, 5, 12); // June = 5 (0-11)
        Date futureDate = calendar.getTime();
        System.out.println("Set date: " + futureDate);
        // Sat Jun 12 09:02:11 PDT 2021

        // Extract components
        System.out.println("Year: " + calendar.get(Calendar.YEAR));        // 2021
        System.out.println("Month: " + (calendar.get(Calendar.MONTH) + 1)); // 6 (June)
        System.out.println("Day: " + calendar.get(Calendar.DAY_OF_MONTH)); // 12
    }
}
```

**Key Points**:
- Months are 0-based (0 = January, 11 = December)
- Days of week: 1 (Sunday) to 7 (Saturday)
- Mutable - changes affect the instance directly

---

## **3. Modern `java.time` API**

### **3.1 Core Classes**
| Class           | Description                      | Example Value             |
| --------------- | -------------------------------- | ------------------------- |
| `LocalDate`     | Date without time                | 2023-03-21                |
| `LocalTime`     | Time without date                | 14:30:45                  |
| `LocalDateTime` | Date and time without timezone   | 2023-03-21T14:30:45       |
| `ZonedDateTime` | Date/time with timezone          | 2023-03-21T14:30:45+01:00 |
| `Instant`       | Machine-readable timestamp (UTC) | 2023-03-21T13:30:45Z      |

---

### **3.2 Basic Usage**

```java
import java.time.*;

public class ModernDateTime {
    public static void main(String[] args) {
        // Current dates/times
        LocalDate today = LocalDate.now();
        LocalDateTime now = LocalDateTime.now();
        Instant timestamp = Instant.now();

        System.out.println("Today: " + today);      // 2023-03-21
        System.out.println("Now: " + now);          // 2023-03-21T08:09:15.268
        System.out.println("UTC: " + timestamp);    // 2023-03-21T15:09:15.268Z
    }
}
```

---

### **3.3 Date Formatting/Parse**

```java
import java.time.*;
import java.time.format.*;

public class DateTimeFormatting {
    public static void main(String[] args) {
        LocalDateTime current = LocalDateTime.now();
        
        // Predefined formats
        DateTimeFormatter isoFormat = DateTimeFormatter.ISO_DATE_TIME;
        System.out.println("ISO Format: " + current.format(isoFormat));
        // 2023-03-21T08:09:15.268

        // Custom formats
        DateTimeFormatter customFormat = DateTimeFormatter.ofPattern("E, MMM dd yyyy hh:mm a");
        System.out.println("Custom: " + current.format(customFormat));
        // Tue, Mar 21 2023 08:09 AM

        // Pattern symbols cheat sheet:
        // yyyy - 4-digit year
        // MM - 2-digit month (01-12)
        // dd - 2-digit day
        // HH - 24-hour (00-23)
        // mm - minutes
        // ss - seconds
        // a - AM/PM
    }
}
```

---

### **3.4 Date Manipulation**

```java
import java.time.*;

public class DateManipulation {
    public static void main(String[] args) {
        LocalDate today = LocalDate.now();
        
        // Add 2 weeks
        LocalDate futureDate = today.plusWeeks(2);
        System.out.println("Two weeks later: " + futureDate);

        // Compare dates
        boolean isAfter = futureDate.isAfter(today); // true
        
        // Temporal adjustments
        LocalDate nextFriday = today.with(TemporalAdjusters.next(DayOfWeek.FRIDAY));
    }
}
```

---

## **4. Conversion Between APIs**

```java
import java.util.*;
import java.time.*;

public class DateConversion {
    public static void main(String[] args) {
        // Date -> Instant
        Date legacyDate = new Date();
        Instant modernInstant = legacyDate.toInstant();

        // Calendar -> ZonedDateTime
        Calendar calendar = Calendar.getInstance();
        ZonedDateTime zdt = ZonedDateTime.ofInstant(
            calendar.toInstant(), 
            calendar.getTimeZone().toZoneId()
        );

        // LocalDateTime -> Date
        LocalDateTime ldt = LocalDateTime.now();
        Date legacyDate = Date.from(ldt.atZone(ZoneId.systemDefault()).toInstant());
    }
}
```

---

## **5. Real-World Use Cases**

### **5.1 Event Scheduler**
```java
LocalDateTime eventTime = LocalDateTime.of(2023, 12, 25, 18, 30);
Duration remaining = Duration.between(LocalDateTime.now(), eventTime);
System.out.println("Days until event: " + remaining.toDays());
```

### **5.2 Age Calculator**
```java
LocalDate birthDate = LocalDate.of(1990, Month.AUGUST, 15);
Period age = Period.between(birthDate, LocalDate.now());
System.out.printf("Age: %d years %d months %d days%n", 
    age.getYears(), age.getMonths(), age.getDays());
```

### **5.3 Time Zone Conversion**
```java
ZonedDateTime nyTime = ZonedDateTime.now(ZoneId.of("America/New_York"));
ZonedDateTime londonTime = nyTime.withZoneSameInstant(ZoneId.of("Europe/London"));
System.out.println("NY: " + nyTime + " | London: " + londonTime);
```

---

## **6. Best Practices**
1. **Always specify time zones** when needed
   ```java
   ZonedDateTime zdt = ZonedDateTime.now(ZoneId.of("Asia/Tokyo"));
   ```
2. **Use immutable** `java.time` objects for thread safety
3. **Prefer `Period` for date-based amounts** (days, months, years)
4. **Use `Duration` for time-based amounts** (hours, minutes, seconds)
5. **Validate user input** when parsing dates
   ```java
   try {
       LocalDate.parse("2023-02-30"); // Throws DateTimeParseException
   } catch (DateTimeParseException e) {
       System.out.println("Invalid date!");
   }
   ```

---

## **7. Common Pitfalls**
- **Month numbering**: Always check if API uses 0-based or 1-based months
- **Time zones**: Never assume system default time zone
- **Leap seconds**: `Instant` doesn't account for them
- **Daylight Saving Time**: Use `ZonedDateTime` for proper handling
