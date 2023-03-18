# String Manipulation

String belong to non-primitive data type. String and other non-primitive have predefined methods on them which can be really useful to us.

Before we move into String let's look at concatenation. Concatenation is process of printing a String within a double quotation along with a variable or an expression.

Let's see we can make concatenation in Java: 

```java
public class Employe{
	public static void main(String[] args){
		String firstName = "Binta";
        String secondName = "Bah";
        int age = 22;
        double salary = 12000;
        String designation = "Account General";
        
        System.out.println("Employe Detail");
        System.out.println("First Name: " +fisrtName);
        System.out.println("Second Name: " +secondName);
        System.out.println("Age : " +age);
        System.out.println("Salary: GMD" +salary);
        System.out.println("Designation: " +designation);
	}
}
//output:
// First Name: Binta
// Second Name: Bah
// Age: 22
// Salary: GMD12000.0
// Designation: Account General
```

Now we can interact with program efficiently. Concatenation is really helpful!

### Creating a new String 

To make a new object in Java we need the new keyword, but that is necessary for String.

```java
public class TheString{
	public static void main(String[] args){
		String str1 = new String("We are learning string");
        //we can do it better
        String str2 = "This is a better way!";
	}
}
```

 ## Accessing Methods on String

We can use the dot to see all the method that are available on the String class.

```java
public class TheString{
	public static void main(String[] args){		
        String str = "Programming";
        System.out.println("The number characters in " +str+ " is " +str.length());
        System.out.println("Is str empty: " +str.isEmpty());
        System.out.println("The character at index 5 is: " +str.charAt(5));
        System.out.println("Those '" +str+ "' contain 'E': " +name.contains("E"));
        System.out.println("Changed case to Upper case " +str.toUpperCase();
        System.out.println("Changed case to lower case " +str.toLowerCase();
	    System.out.println("Those " +str+ " is equals to 'programming': " +str.equals("programming"));
        System.out.println("Those " +str+ " is equals to 'programming': " +str.equalsIgnoreCase("programming"));
        System.out.println("Get the characters from index '0 to 4' in '" +m+ "' are: " +m.substring(0,4));
	}
}
//out:
// The number characters in Programming is 11
// Is str empty: false
// The character at index 5 is: a
// Those 'Programming' contain 'E': false
// Changed all case to Upper case: PROGRAMMING
// Changed all case to lower case: programming
//Those Programming is equals to 'programming': false
//Those Programming is equals to 'programming': true
// The characters from index '0 to 4' in 'Programming' are: Prog
```

Let's look at some of the String methods in java. You can find on the internet!

| Name                        | Return Type | Description                                                  |
| --------------------------- | ----------- | ------------------------------------------------------------ |
| `length()` method           | integer     | count the number of characters in a String                   |
| `isEmpty()` method          | boolean     | check whether the String contain any character               |
| `charAt()` method           | char        | It takes a parameter of type integer, return element at a certain position if found otherwise error. index start from `0` |
| `contain()` method          | boolean     | it takes a char as a parameter, and check within the whole String whether the provided character is found return true if found otherwise false |
| `toUpperCase()` method      | String      | Change all the characters in a String  to capital letters    |
| `toLowerCase()` method      | String      | Change all the characters in a String to lower case letters. |
| `equals()` method           | boolean     | This method takes a String as parameter, return true if the provided parameter is found in the String otherwise false. This method is case sensitive |
| `equalsIgnoreCase()` method | boolean     | This method is the same the above one `equals()`. The only it relax the case checking. |
| `m.substring()`             | String      | This method takes two parameters(integer), first is the index you are starting and second is not actually the index you are going to stop, but rather `-1` of that. If the last parameter is `4` it will stop at `3` meaning last index exclusive, first index inclusive. |

Note! *we use dot, `.` to access the available method on String. Every method has a return type(on the left hand-side) be sure to check the return type of a method before using it*

