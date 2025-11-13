#  Student Register

### Objective:

In this exercise, you'll design a **`Student` class** and use an **array** to store and display information for 5 students. You will also determine whether each student has **passed** or **failed** based on their **GPA**.



------

### Instructions:

#### 1. Define the `Student` Class

Create a class named `Student` with the following attributes:

```java
public class Student {
    String number;
    String firstName;
    String lastName;
    String midName;
    String dob;        // Date of birth
    String department;
    double GPA;        // Grade Point Average

    // Display method to print student information
    public void displayInfo() {}
}
```

------

#### 2. Create 5 Students in `main`

In your `main()` method, do the following:

1. Create **5 `Student` objects**.
2. Store them in a **`Student[]` array**.
3. Assign at least **one student** a GPA **less than 2.0**.
4. Loop through the array and call `displayInfo()` on each student.

------

#### main` Method:

```java
public class StudentRegister {
    public static void main(String[] args) {
        // create array of type studetn
        
        // create object object

        // Print student info and pass/fail status        
    }
}
```

------

### Output Sample

```
-------------------------------
Student Number: S001
Name: Awa Musa Camara
DOB: 2003-05-12
Department: Computer Science
GPA: 3.2
Status: Pass
-------------------------------
Student Number: S002
Name: Ebrima Baba Touray
DOB: 2002-11-22
Department: Mathematics
GPA: 1.9
Status: Fail
...
```

------

### References:

[Intro to OOP](https://github.com/touraye/under-doz/tree/main/content/Module-4-useful-java-classes)

Happy coding!