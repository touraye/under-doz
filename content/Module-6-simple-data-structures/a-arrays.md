# Arrays

Throughout the course we have been dealing variables that store a single value at any given time.  Unlike *single value*, **data structures** can store multiples values at any given time. And, as far as Java is concerned multiple values of the same type. Arrays are the fundamentals of data structures as far as Java is concern,  despite array is said to be a simple data structure. 

Topic to cover:

1. What is an Array
2. Declaring an Array
3. Initialing an Array
4. Accessing Element from an Array

## What is an Array

A fixed-size, contiguous block of memory that stores elements of the same data type. In an Array each value is know as **an element** which is store at a specific position refer to as an **index**. The **index** of every Array start from `0...` till the last element. An Array also possess a property called the **length**  that is use to know the *size*. 

### Declaring an Array

Array can be declare like any other types, but remember Array is not a type, it is a data structure. To declare an Array we start off the *type* like any other variable, then the follow by Array bracket `[]`, name of the variable, assignment operator `=`, the `new` keyword, and lastly Array bracket `[3]` with the *size* of the number element that will be stored in that Array. 

Like any other data-type, when an Array declared it said to be either `0` for **primitives** or `null` for **referential** . Trying accessing elements from Array become will thrown *`IndexBoundException`* .

```java
int size = 5; // size of an Array
int[] numbers = new int[size];
// print the size of the numbers Array
System.out.println(numbers.length); // 5

// directly pass the value of size
String[] names = new String[10];
// print the size of the names Array
System.out.println(numbers.length); // 10
```

The two above are Arrays are of different types and size. All of these Array contain their default values in them. The `numbers` array store five `0` and `names` store ten `null`.

```java
int size = 5; // size of an Array
int[] numbers = new int[size];
System.out.println(Arrays.toString(numbers));
//
[0, 0, 0, 0, 0]

String[] names = new String[10];
System.out.println("length: " +names.length);
System.out.println(Arrays.toString(names));
//
length: 10;
[null, null, null, null, null, null, null, null, null, null]
```

#### Store element in to the array

Hence we have created an empty Array of size five meaning we can store 5 elements of type int into the `numbers` Array, remember **index** start from **`0`**, and therefore, Array uses **index** to position its elements. The first **element** that will be store will always be at **index `0`** and of course the last element will the at *length* minus one. If the length of an Array is `5` then the last element will be place at **index `4`**.

 To do that we need to refer to the name of the variable which is `numbers` with the Array bracket `[]`, in side of the you pass the position or **index** and rest is a normal procedure of assigning value to a variable. Using a wrong index will thrown you an exception of `IndexBoundException` .

```java
int[] numbers = new int[size];
// store number into the Array using index
numbers[0] = 10;
numbers[1] = 1;
numbers[2] = 20;
numbers[3] = 4;
numbers[4] = 5;
```

### Accessing elements from an Array

As the way we stored elements into the Array, we will also use the same technique to access elements. As usual, the `numbers[]`, the variable name of an Array with an Array bracket. The most important thing here is the **index**  which is the position of each element. Always print the length of an Array to be at the saver size! 

```java
// accessing elements from an Array using their index
System.out.println("First element: " +numbers[0]);
System.out.println("Second element: " +numbers[1]);
System.out.println("Third element: " +numbers[2]);
System.out.println("Fourth element: " +numbers[3]);
System.out.println("Fifth element: " +numbers[4]);

//
First element: 10
Second element: 1
Third element: 20
Fourth element: 4
Fifth element: 5
```

#### Resigning values from an Array

Reassignment is also possible with Arrays. To replace an existing with a new value we use the position of the old value and assign it with a new value.

```java
numbers[4] = 12;
System.out.println("Fifth element: " +numbers[4]);
//
12
```

#### Remove values from an Array

Its also possible to remove a value from an Array. But, remember Array are fixed size memories; once the size is allocated it cannot be adding either reduce it. So, therefore a value cannot remove but it can remove a value and by setting it to its default stage.

```java
// remove 
numbers[1] = 0;
numbers[4] = 0;
System.out.println("Second element: " +numbers[1]);
System.out.println("Forth element: " +numbers[4]);

//
Second element: 0
Fourth element: 0    
```

## Initialing an Array

The other way and more straight forwarded way of creating an Array is to set your values initially. The technique is almost the same; 

* The data-type for example `int[]` with the Array bracket
* The name of the variable for example `numbers`
* Assignment operator `=`
* Curly brace `{}`, wrapping the elements with a comma separation

If you are watchful here we do not provide the size of an Array and we said Array is fixed memory location. Well, this way of creating an Array is more dynamic, not fixe size, the element can adding or reduce to any length, but with caution.

```java
// initial grades
int[] grades = {99, 75, 89, 93, 66};
System.out.println("Length: " +grades.length); // Length: 5

// added more grades
int[] grades = {99, 75, 89, 93, 66, 90, 59, 88, 45, 39};
System.out.println("Length: " +grades.length); // Length: 10
```

The above code snippets illustrate the dynamic nature of *initializing* an Array. It can accommodated to any size.

Using the length property, accessing the elements, updating (replace and removing) elements can be also apply.

## Array with Loop

Hence elements on an Array are positioned in an index, starting from `0` all the way up to the last index. It is ideal to use a *loop* to read values from an Array.

We can use a `for` loop to achieve this:

```java
int[] grades = {99, 75, 89, 93, 66, 90, 59, 88, 45, 39};
int lengthOfGrades = grades.length; // length of the grades Array
// reading elements
for (int i = 0; i < lengthOfGrades; i++) {
    System.out.println(i); // print i
}

//
0
1
2
3
4
5
6
7
8
9
```

The `for` uses the  `lengthOfGrades`  as its condition, so therefore the numbers between `0` starting of the loop all the way up to less than `10` which is the actual *length* of the grades Array. `0...9` are ten number in total and using range will print you all the elements from the `grades` Array. 

With this trick we can use `i` to access the values from our `grades` Array. How do we access element from an Array? By using the Array bracket with the index which is `grades[0]` for the first element. Hence `i` is also starting from `0` we can simply replace `0` with it; `grades[i]`

```
int[] grades = {99, 75, 89, 93, 66, 90, 59, 88, 45, 39};
System.out.println("Length: " +grades.length);
int lengthOfGrades = grades.length;
// reading elements
for (int i = 0; i < lengthOfGrades; i++) {
    System.out.println(grades[i]);
}

//
99
75
89
93
66
90
59
88
45
39
```

 The syntax is fair the same with that of the `for` loop; the loop will execute up to one position before the