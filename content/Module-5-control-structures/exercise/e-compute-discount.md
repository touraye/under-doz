# Discount Calculation

The first part of this exercise it to find out the first time a shop owner make a sales of thousand Dalasis and allocate a 15% discount to first five preceding customers. The program will keep track of every sales by accumulating its value and compute 15% discount  to those preceding five customers. The program should be in operation as long as the shop owner needs it and he/she should be able  kill it whenever necessary. 

Coming up with possible variables:

1. `sale` to keep track of the sales.
2. Each sale should be accumulated together; `sumOfSales`
3. A constant variable to hold 15% discount hence discount isn't changing.
4. A Boolean value that will be use to check whether  sales has reached 1000; `hasReachedThousand` 
5. A variable that will keep track of the preceding 5 customer
6. A sentinel value that will be use to kill the program

Coming up with an Algorithm:

A program will simulate an operational shop so therefore, it make sense to use of an `iterative` statement. Hence the user will should be able to kill the program at any given time, therefore a `conditional` statement would be require.

```java
Scanner in = new Scanner(System.in);
double sale; // sales per customer
double sumOfSale = 0; // accumulated sale
String opt;

while (true) { // the loop will foreever run
    // ask user a prompt
    System.out.println("Press 'Q' to kill the program, any other to continue");
    opt =in.next(); // take what the user  typed in

    // check if the user types in Q
    if (opt.equals("Q")) break; // break the program
}
```

The program is very basic, but it form the fundaments. We have a program that will continuously run until a sentinel value is enter, which is `Q` . 

The next step will be to take sales from the user, sum it to sum of sales, and check whether the total sale is up to 1000.

Below we make use of our `sale` and `sumOfSale` variables by taking input from the user and summing it . And `if` condition that is checking whether `sumOfSales` has reach 1000 if so a print to the console:

```java
Scanner in = new Scanner(System.in);
double sale; // sales per customer
double sumOfSale = 0; // accumulated sale
String opt;

while (true) {
    System.out.println("Press 'Q' to kill the program, any other to continue");
    opt =in.next();

    // check if the user types in q
    if (opt.equals("Q")) break; // break the program

    // tackle the business
    System.out.print("Enter amount: GMD" );
    sale = in.nextInt(); // take sale from the user
    sumOfSale = sumOfSale + sale; // take sale and it to sum of sale

    // check whether sumOfSale is up 1000 or more
    if (sumOfSale >= 1000) {
        System.out.println("Sale has reached a grand");
    } // end if
} // end while
```

Next we will start taking care of; keeping track of the preceding sales after accumulated sales of 1000 and allocate a 15% discount to them.