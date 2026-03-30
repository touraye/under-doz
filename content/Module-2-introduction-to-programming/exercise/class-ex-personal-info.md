# My Personal Info

```java
import java.util.Scanner;

public class TakingInput {
     static void main() {
        // ====
        /*`
        VARIABLE DECLARATION:
        personal info
         */
        String name;
        int age;
        String gender;
        String address;
        //====

        // taking input:
        Scanner in = new Scanner(System.in);

        // prompting users
        // ask user to enter their 'name'
         System.out.print("Enter your name: ");
         name = in.next();

         // ask user to enter their 'age'
         System.out.print("Enter your age: ");
         age = in.nextInt();

         // ask user to enter their 'age'
         System.out.print("Enter your address: ");
         address = in.next();

         System.out.print("Enter your gender eg(m)");
          gender = in.next();

         // Print your personal info
         System.out.println("******* MY PERSONAL INFO *******");
         System.out.println("My name is " +name+ ". I live in " +address);

         // My name is Alfusainey Fatty, I live in Bakuteh, I am 46 years old, and my gender is m
    }
}

```

