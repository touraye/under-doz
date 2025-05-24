# Arrays

Throughout the course we have been dealing variables that store a single value at any given time.  Unlike *single value*, **data structures** can store multiples values at any given time. And, as far as Java is concerned multiple values of the same type. Arrays are the fundamentals of data structures as far as Java is concern,  despite array is said to be a simple data structure. 

Topic to cover:

1. What is an Array
2. Types of Arrays
3. Declaring an Array
4. Initialing an Array
5. Accessing Element from an Array
6. Array with loop

## What is an Array

An Array is a  fixed-size, continuous block of memory that stores elements of the same data type. In an Array each value is know as **an element** which is store at a specific position refer to as an **index**. The **index** of every Array start from `0...` till the last element. An Array also possess a property called the **length**  that is use to know the *size* of an Array or the number of elements it contain. 

Point of correct, In Java there is no concept of continuous  memory for [heap objects](). Object in the [heap memory]() are not continuous according to the [JVM]()

## Types of Array

Hence Arrays store multiples values in the type, they can also appear in different spaces and forms. This spaces and forms are influenced by the kind of problem at hand. Well, Java offer two main types of Arrays; **one-dimensional** and **multi-dimensional**. A **one-dimensional** Array consist of only one row which is used to store similar values, while **multi-dimensional** Arrays can store values in rows and column format. 

A **multi-dimensional** Array also range forms:

1. **Two-dimensional** - matrix style.
2. **Three-dimensional** - 3D Array.
3. **Jagged** - Arrays of Array with different lengths. 

Arrays can be created in two ways; declaration and initialization

### Declaring an Array

Declaration of an Array happens at *compile time* 

To declare an Array we first specify the data type with an Array angle bracket `[]` and create a [reference variable]() i.e a variable name. Hence, Arrays are classify under non-primitive aka referential types the variable here is going to be use as a reference to an *object*. The actual variable is created in the **[stack memory]()**, which will point to an *object* in the **[heap memory]()** when initialized. But, at the state it does not point to any *object*. When an Array is declared it does not have a *size* to begin with, therefore, elements cannot be added nor read from it.

1. We start off the *data-type* like any other variable
2. Array bracket `[]`, telling the compile this type is going to be an Array of integer for instance.
3. Lastly, we specify the name of the reference variable which is define in the stack memory.

```java
int[] numbers; // numbers is defined in the stack memory
```

The Arrays above do not point to any object, so therefore, no memory was allocated for them. The snippet below we will instantiate a `new` Array there creating a new instance of an Array, memory will be allocated in the **[heap memory]()**, and the size as well. 

```java
numbers = new int[5]; // a new array is created in the heap memory of size five
String[] names;
names = new String[5];
```

The two above are Arrays are of different types but the same size. All of these Array contain their *default values* in them. The `numbers` Array has five `0` and `names` has five `null` as their default values.

**Some Operations on Arrays:**

* Array has a very handed *property* called the **length** which is use to know the *size* of an Array.
* The Array class `Arrays.tostring()`  `static` *method* prints the value (s) of any given Array with an Array bracket with a comma separation.
* The Array class `Arrays.sort()` `static` *method* sort the any given Array into ascending or descending order.
* The `equals` method compare two Arrays and return `true` or `false`
  * This method can also compare portion of Array; starting index to end index in the two array
* The `fill` method replace all the values of an Array with a given value
* The `copyOf()` copies from one Array to another

```java
System.out.println("Length: "+ numbers.length);
// Length: 5
System.out.println(Arrays.toString(numbers));
// [0, 0, 0, 0, 0]

System.out.println("length: " +names.length);
// length: 5;
System.out.println(Arrays.toString(names));
// [null, null, null, null, null]
```

#### Store element in to the array

Hence we have created an empty Array of size five meaning we can store 5 elements of type int into the `numbers` Array, remember **index** start from **`0`**, and therefore, Array uses **index** to place its elements. The first **element** that will be store will always be at **index `0`** and of course the last element will the at *length* minus one. If the length of an Array is `5` then the last element will be place at **index `4`**. The *length* property start counting from `1` which is why it's always going to be greater than the last **index**; if an Array has 5 element, therefore the *length* is going to be `5`. However, the last element will be at **index** `4`.

 To do that we need to refer to the name of the [reference variable]() which is `numbers` with the Array bracket `[]`, within it pass the position or **index** and rest is a normal procedure of assigning a value to a variable. Using a wrong index will thrown you an exception of `IndexBoundException` .

```java
// store number into the Array using index
numbers[0] = 10; // place 10 at index 0
numbers[1] = 1; // place 1 at index 1
numbers[2] = 20; // place 20 at index 2
numbers[3] = 4; // place 4 at index 3
numbers[4] = 5; // place 5 at index 4

// using to Arrays.toString() method
System.out.println(Arrays.toString(numbers));
//[10, 1, 20, 4, 5]

// applying some operations
System.out.println("Original: "+Arrays.toString(numbers));
// Original: [10, 1, 20, 4, 5]
Arrays.sort(numbers) // sort the Array in ascending order
System.out.println("Sorted: "+Arrays.toString(numbers));
// Sorted: [1, 4, 5, 10, 20]

// check for two Arrays are equal
int[] arr1 = {10, 1, 5, 9};
int[] arr2 = {10, 1, 5};
System.out.println("Are the elements in 'arr1' = 'arr2': "+Arrays.equals(arr1, arr2));
Are the elements in 'arr1' = 'arr2': false        
```

### Accessing elements from an Array

As the way we stored elements into the Array, we can also use the same technique to access elements from an Array. As usual, the `numbers[]`, the variable name of an Array with an Array bracket. The most important thing here is the **index**  which is the position of each element. Always print the length of an Array to be at the saver side! 

```java
// accessing elements from an Array using their index
System.out.println("First element: " +numbers[0]);
System.out.println("Second element: " +numbers[1]);
System.out.println("Third element: " +numbers[2]);
System.out.println("Fourth element: " +numbers[3]);
System.out.println("Fifth element: " +numbers[4]);

// First element: 10
// Second element: 1
// Third element: 20
// Fourth element: 4
// Fifth element: 5
```

#### Resigning values from an Array

Reassignment is also possible with Arrays. To replace an existing value with a new value we use the **index**  of the old value and assign it with a new value.

```java
numbers[4] = 12; // update the value at index 4 with 12
System.out.println("Fifth element: " +numbers[4]);
// Fifth element: 12
```

#### Remove values from an Array

Its also possible to remove a value from an Array. But, remember Array are fixed size memories; once the size is allocated it cannot be adding nor reduce. So, therefore a value cannot be removed totally but it can replace with a default value value of that Array.

```java
// remove 
numbers[1] = 0;
numbers[4] = 0;
System.out.println("Second element: " +numbers[1]);
System.out.println("Forth element: " +numbers[4]);

// Second element: 0
// Fourth element: 0    

// print the number array
System.out.println(Arrays.tostring(numbers));
[10, 0, 20, 4, 0]
```

## Initialing an Array

As we have mentioned about creating a reference variable when declaring an Array and later creating an object pointing the reference variable. Here we learn a more straight forwarded way; creating reference variable along with the Array object or passing the actual values.

The other ways and more straight forwarded way of creating an Array is to create the actual object either by specifying the *size* or set the initial values. 

1. Creating an Array object
   1. The data-type for example `int[]` with the Array bracket
   2. Reference variable
   3. Assignment operator `=`
   4. A new Array object; `new int[5]` with a size
2. Passing the values directly, with this no `new` keyword and  size is require:
   1. The data-type for example `int[]` with the Array bracket.
   2. Reference variable.
   3. Assignment operator `=`.
   4. Curly brace `{}`, wrapping the elements with a comma separation.

If you are watchful for the second step we do not write the `new` keyword but internally Java does it, and the *size* is not provided. Well, this way of creating an Array by passing value is more dynamic, no fixe size is required, elements can be replaced. However,  the element can cannot be added or reduce to any length once they are passed in.

```java
// initializing an Array:
String[] students = new String[5];
// fill the array with 5 names

// Passing value, dynamic Array
int[] grades = {99, 75, 89, 93, 66};
System.out.println("Length: " +grades.length); // Length: 5
grades[5] = 40;// index out of bound exception
```

The above code snippets illustrate the dynamic nature of *initializing* an Array. It can be accommodated to any size.

Using the length property, accessing the elements, updating (replace and removing) elements can be also applied.

## Array with Loop

Hence elements on an Array are positioned in an index, starting from `0` all the way up to the last index (`length - 1`). It is ideal to use a *loop* to read values from an Array.

We can use a `for` loop to achieve this in a simplest matter:

```java
int[] grades = {99, 75, 89, 93, 66, 90, 59, 88, 45, 39};
int lengthOfGrades = grades.length; // length of the grades Array
// looping through length of grades Array
for (int i = 0; i < lengthOfGrades; i++) {
    System.out.print(i+ ", "); // print i
}

// 0, 1, 2, 3, 4, 5, 6, 7, 8, 9,
```

The `for` uses the  `lengthOfGrades`  as its condition to iterates, so therefore the numbers between `0` starting of the loop all the way up to less than `10` which is the actual *length* of the grades Array. `0...9` are ten number in total and using range will print you all the elements from the `grades` Array. 

With this trick we can use `i` to access the values from our `grades` Array. How do we access element from an Array? By using the Array bracket with the index which is `grades[0]` for the first element. Hence `i` is also starting from `0` we can simply replace `0` with it; `grades[i]`

```java
int[] grades = {99, 75, 89, 93, 66, 90, 59, 88, 45, 39};
System.out.println("Length: " +grades.length);
int lengthOfGrades = grades.length;
// reading elements
for (int i = 0; i < lengthOfGrades; i++) {
    System.out.println(grades[i]+ ", ");
}

// 99, 75, 89, 93, 66, 90, 59, 88, 45, 39
```

Each time the `for` loop iterates the value of `i` is going to be use to access the elements from the `grades` Array; when `i` is `0` the element at **index `0`** will be access, so thus to the rest of the elements up `i < lengthOfGrades`. 

It's also possible to use a `while` and `do while` loop to read elements from an Array, but anyway not the best approach.

```java
int[] arr = {20,10, 40, 15, 6};
int count = 0;
while (count < arr.length) {
    System.out.print(arr[count]+ " ");
    count++;
}

// 20,10, 40, 15, 6

// do while loop
do {
    System.out.print(arr[count]+ " ");
    count++;
}  while (count < arr.length);

// 20,10, 40, 15, 6
```

## Parallel Array

Imagine we want to process students with their grade, maybe we want write a program that will be use to test the who are promoted or not. An Array in itself will not suffice hence it can only store values of the same type, but even if we were to store grades as `string` w will still run into problem. 

Suppose the class size is five creating two Array with same *size*, but of different type. One will store student name and the other will store their corresponding grades. Two or more Arrays of the same *size* are said to be **parallel** regardless of their type.

```java
String[] names = {"Ahmed", "Alieu", "Mariama", "Fatou", "Amienata"};
int[] grades = {90, 89, 95, 88, 94};

// printing each student with grades
System.out.println(names[0]+ ": " +grades[0]);
System.out.println(names[1]+ ": " +grades[1]);
System.out.println(names[2]+ ": " +grades[2]);
System.out.println(names[3]+ ": " +grades[3]);
System.out.println(names[4]+ ": " +grades[4]);

// Ahmed: 90
// Alieu: 89
// Mariama: 95
// Fatou: 88
// Amienata: 94
```

This two Arrays are in sync, it also possible to use a `for` loop to iterate through these two Arrays:

```java
for (int i = 0; i < names.length; i++) {
    System.out.println(names[i]+ ": " +grades[i]);
}
```

When working with parallel Arrays and the Array should be of the *size* not necessarily of the same type.

### Multi-dimensional Array

An Array is very simple data-structure that store stores the same types in a single variable i.e **one-dimensional** Array where all the elements are in row format. However, an Array can also live within an Array for example, index at position one can be an Array with some elements so forth and so on. 

The syntax of a **multi-dimensional**  differ from that of **one-dimensional** Array. A **multi-dimensional array** always have two *array brackets* like so; `[][]` before the specify data-types.

**Creating a Multi-dimensional Array**

As we have learn above; Array declaration and initialization is also possible with **multi-dimensional** Array. Lets have some fewer examples:

```java
int[][] arr;
arr = new int[5][2];
```

The `arr` Array is said to store `5` elements within it outer box and `2` elements within its inner box. Let's read the default elements from `arr` using `deepToString()` method.

```java
System.out.println(Arrays.deepToString(arr));
// [[0, 0], [0, 0], [0, 0], [0, 0], [0, 0]]
```

Without using the *length* property you already have a picture of the structure; the **outer array** consist of five inner elements which are Arrays themselves and with those Array i.e **inner array** also has two elements.

**Accessing Elements from a Multi-dimensional Array**

Well, that pretty easy hence, we know the structure and about **index**.  At first let try accessing the first element from the **outer array**.

```java
System.out.println("First ele: " + Arrays.toString(arr[0]));
// First ele: [0, 0]
```

The first element is an Array meaning we can also use the *array bracket* to access its element. By doing so we can add another *array bracket:*  `arr[0][0]`. What will this print an Array or just a value? 

```java
// reading the first element from the first inner array
System.out.println(arr[0][0]);
// 0

// reading the second element from the first inner array
System.out.println(arr[0][1]);
// 0
```

**Populating Element into a Multi-dimensional Array**

If we can get to the first elements from the first **inner arrays** then we can assign value to it as well. Since, `arr[0][0]` gave us `0` and  `arr[0][1]` gave us `0` respectively.

```java
// populate
arr[0][0] = 20;
arr[0][1] = 10;
// read the entire arr Array
System.out.println(Arrays.deepToString(arr));
// [[20, 10], [0, 0], [0, 0], [0, 0], [0, 0]] 
```

You can now see the structure of `arr` has change, the first Array have `20` and `10` as its element. Challenge yourself to assign values to the rest of the **inner arrays** values.

**Multi-dimensional** Array is categorize into three:

1. **Two Dimensional Array Matrix (2D Array)**: An Array that represent in a rows and column format, like the example above.
   1. The **row** is actually the **outer** Array
   2. The **columns** are the **inner** Arrays
   3. Syntax: `int[][] arr2D = {{3, 5}, {9, 2}}`
2. **Three Dimensional Array (3D)**: Instead of `[][]` 3-D Array has 3 *array bracket*, meaning it can have an **outer** Array with an **inner** Array acting as an **inner** Array.
   1. Syntax: `int[][] arr3D = {{{2, 4}, {9, 5}}, {{4, 3}, {6, 1}}}`
3. **Jagged Array (Array of Arrays with Different Lengths)**: Unlike a 2D Array this one do not have fix length for the **inner arrays**, each row can have a different number of columns.
   1. Syntax: `int[][] jagged = { {1, 2}, {3, 4, 5}, {6} };`

### Multi-dimensional Array with loop

Going back to our `studentGrades`, the parallel Arrays one consist of the names of the student and the other their grades. Anyway, we can solve this issue or simplify the problem using a **two-dimensional** Array. But, wait the two Array are of different type. Well, that easy we can sacrifice one type over the other.

String cannot be converted to integers, so therefore the string will remains as it is. But an integer type can be represented a string and its possible to convert it back an integer hence, it a valid integer value.

Refactoring:

```java
// parallel array
String[] names = {"Ahmed", "Alieu", "Mariama", "Fatou", "Amienata"};
int[] grades = {90, 89, 95, 88, 94};

// new 2D represent
String[][] studentGrades = {
                {"Ahmed", "90"},
                {"Alieu", "89"},
                {"Mariama", "95"},
                {"Fatou", "88"},
                {"Amienata", "94"}
        };
```

The refactored version looks much more cleaner and easy to read. We could use the Array declaration or initialization and later assigned value manually using *array bracket*. But, a simple approach it always the best.

To iterate over a 2D Array require a nested `for` loop, **outer loop** for the **outer array**, and **inner loop** for the **inner array**. Let's start of with the **outer loop** to read the **outer array**

```java
for (int i = 0; i < studentGrades.length; i++) {
    System.out.println(Arrays.toString(studentGrades[i]));
}

//
[Ahmed, 90]
[Alieu, 89]
[Mariama, 95]
[Fatou, 88]
[Amienata, 94]
```

We have successfully read all the elements of the **outer array** and realized each i also an array consisting of two elements. One thing to note is that the `studentGrades` has a five elements (inner array), but the **inner array** themselves have only two elements within them. So, it will be wise of you how many times to iterate using a **nested loop**. 

Hence, the **inner array** just to two length then we can simply iterate two times:

```java
for (int i = 0; i < studentGrades.length; i++) {
    for (int j = 0; j < 2; j++) {
        System.out.print(studentGrades[i][j]+ " ");
    }
    System.out.println();
}

// 
Ahmed 90 
Alieu 89 
Mariama 95 
Fatou 88 
Amienata 94 
```

From the above code snippet:

1. The **outer loop** is use iterate over the `studentGrades` array using the `i`; `studentGrades[i]` will give out the first **inner array**. 
2. The **inner loop** iterate two time, the first iteration when `j = 0`
   1. The first iteration we have access to the first element which is the name of the student
   2. The second iteration `j = 1` and we have access to element at index 1 which is the grade of the corresponding student.
3. After the first iteration of the **inner loop** a line break is happen when an empty print statement.
4. The cycle will repeat for five times therefore, all the elements of the 2D array are printed.
