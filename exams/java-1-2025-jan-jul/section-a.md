1. An expression will always evaluate a value.

   1. True
   2. False

2. According to the rules of precedence, which operator will execute first in the statement below:

   ```java
   int x = 9 * 2;
   ```

   1. Assignment operator
   2. Arithmetic operator
   3. Both a and b
   4. None of above

3. Logical operators are said to be Boolean operators because they.

   1. Act upon objects and evaluate to a String

   2. Act upon numeric values and evaluate to a numeric value 

   3. Act upon Booleans and evaluate to a  Boolean value.

   4. None of the above

4. Consider the code snippet below:

   ```java
   int a = 5;
   int b = 4;
   boolean x = a != b;
   ```

   What will x evaluate to?

   1. False

   2. True

5. The type of operator that acts on only one value is called.

   1. Unary operator
   2. Arithmetic operator
   3. Logical operator
   4. Comparison operator

6. Study the code carefully:

   ```java
   boolean flag = fales;
   do {
       System.out.print("Enter something")
   } while (flag);
   ```

   Will the above code print "Enter something" to the console?

   1. No
   2. Yes

7. Control structures or flows change the program execution pattern.

   1. False
   2. True

8. Consider the code snippets below:

   ```java
   boolean flag = true;
   
   if (flag) {
       // if block
   } else {
       // else block
   }
   ```

   Which block of the code will execute?

   1. Th `else` block

   2. The `if` block

   3. Both `if` and `else` block

   4. None will execute

9. A data structure in which elements are positioned in an **index** base is referred to as___.

   1. Class

   2. An Object

   3. An Array

   4. An Exception

10. Study the code snippets carefully:

    ```java
    String[] arr = new String[10];
    ```

    The `new` keyword is used to allocate memory at runtime

    1. True
    2. False

11. Objects are stored in the **heap** memory while their reference are stored in the?

    1. Object memory

    2. Class

    3. Stack memory

    4. Reference variable

12. Study the code carefully:

    ```java
    int count = 5;
    while (count != 2) {
        --count;
    }
    System.out.println("Value of count: " +count);
    ```

    1. 2 

    2. 3

    3. 1

    4. 0

13. Consider the code snippets:

    ```java
    public static void func() {
        System.out.println("This is a function");
    }
    
    public static void main(String[] args) {
        func();
        func();
    }
    ```

    How many times will "This is a function" be printed?

    1. Three time

    2. Once

    3. Two times

    4. None of the above

14. When a function defines a return type within its signature, it is mandatory to return that type.

    1. Yes

    2. No

    3. Some time

    4. None of the above

15. Use the code snippets below to answer questions 15 and 16.

    ```java
    public static void main(String[] args) {
    	int x = 5;
    	
    	if (x > 2) {
    		int y = x * 5;
    	}
    }
    ```

    What will be the value of `y`?

    1. 25

    2. Not define

    3. 5

    4. 0

16. Which variable is considered to be a global variable?

    1. `y`

    2. both `y` and `x`

    3. `x`

    4. None

17. The basic building block for every Java program is__

    1. Statement and Expression
    2. Conditional statement
    3. Class
    4. Main method

18. Consider the code snippet and answer questions 18 and 19.

    ```java
    switch(value){
        case a:
            // code here
            break;
        case b:
            // code here        
        case c:
            // code here
            break;
        default:
            // code here
            
    }
    ```

    A `switch` statement takes a single variable and tests very case against, executes the case that matches the input variable, and breaks or executes the default block.

    1. False
    2. True

19. Suppose the input variable is `b`, both` case: b & c` will execute.

    1. Yes 

    2. No

20. The String class has two methods that are used to compare two String lateral; 

    ```java
    String str = "Java";
    boolean a = str.equals("java") ? true : false;
    boolean b = str.equalsIgnoreCase("java") ? true : false;
    ```

    1-  `a` = `true`, `b` = `false`;

    2 - `a` = `false`, `b` = `false`;

    3 - `a` = `false`, `b` = `true`;

    1. 1 and 2
    2. 1 only
    3. 3 only
    4. 1, 2, and 3

21. Consider the code snippet:

    ```java
    int[] numbers = new int[5];
    System.out.println(Arrays.toString(numbers));
    ```

    What is going to be printed in the console for the `numbers` Array?

    1. Nothing
    2. `[]`
    3. `[0, 0, 0, 0,0]`
    4. `[0, 0, 0, 0]`

22. The `sum` function is expected two input to be passed in whenever called:

    ```java
    public static int sum(int a, int b) {
        if (a == 0 || b == 0) return 0;
    
        int total = a + b;
        return total;
    }
    ```

    The `sum` function has two `return` statements, which will make this function return `0`.

    1 `a = 0` , `b = 0`

    2 `a = 0` , `b = -4`

    3 `a = 3 , b = 4`

    1. 1 and 2
    2. 1 and 3
    3. 2 only
    4. 1 only

23. A ternary operator is shorthand for `if` and `else` statement.

    1. False
    2. True

24. When `x` is given the value of `0` and post-incremented while printing:

    ```java
    int x = 0;
    System.out.println(++x);
    ```

    What will be the value of `x`?

    1. 0
    2. 1
    3. 2
    4. `++x`

25. What will be the outcome of the code snippet?

    ```java
    int[] numbs = {90, 9, 5, 55, 3, 2};
    for (int i = 2; i < numbs.length; i++) {
        System.out.print(numbs[i]+ " ");
    }
    ```

    1. `5 55 3 2 `
    2. `9 5 55 3 2 `
    3. `90 9 5 55 3 2`
    4. `90 9 5`
