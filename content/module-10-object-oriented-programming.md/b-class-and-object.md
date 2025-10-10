# What is Class

Imagine you are tasked to create **data type** for your program that stores five roll numbers. Well it is easy enough to create an array of integer with a size of five. What if you then asked to create data structure that stores five names. Hence, names are strings; an array of type  string will suffice. As for the final tasked, create just a **data structure** that will store data (roll number, name and mark) of 5 students. Confusing, right? Because you can use an array hence the data for the five students are of a different type. `roll number` is a integer, `name` is a string, and `mark` is decimal. 

Similarly, you can create separate arrays for type with size of five. Is this program scalable? No. Simply because you will to use more array as the data  to store increase and all of them are not bind to a single **type** i.e your own custom **type**.

This is where **object oriented programming** shines. Instead of creating different array we can leverage a **class**. A class is name **group** of **properties** and **functions**. So let's use a **class** to create properties of our student which are `rollNumber, name, mark`.

Combining these three **properties**  into a single **entity** we will have to create a **class** and by convention a **class** starts with a capital letter.

```java
class Student {
	int rollNumber;
	String name;
	double mark;
}
```

Above we have created our own **data type** by the name **Student** that will store roll number, name, and mark.

### More About a Class

A **Class** is just a **template** or a **logical constructure** with a distinct name, **properties** and **functions**. Whoever using this program and want to create a *student* can use the **Student Class**, they don't have to do anything rather to use the **template** to do so.

You are tasked to use the **Student class** aka **template** to create students. By using the same **properties** from the **Student Class** each new *student* can assign their own values without affecting each other. A **class** is  a template where **objects** are created from.

```java
public class Main {
    class Student {
        int rollNumber;
        String name;
        double mark;
    }
    
    public static void main(String[] args) {
    	Student student1; // first studnet
        student1.rollNumber = 1213;
        student1.name = "Ahmed Dicko";
        student1.mark = "95";
        
        Student student2; // second studnet
        student2.rollNumber = 1112;
        student2.name = "Yabou";
        student2.mark = "100";
    }
}
```

If **Student** is a **class**. The question is what present a **Class**? From the above we can say `student1` and `student2` present a **Student** because they are of type **Student**. Following the rules of **variables creation** a **data types** comes before the variable itself. So, therefore, we can conclude by saying `strudent1` and `studnet2` are of type **Student**. And, **Student** is our own type that we created by leveraging a class. 

## Object

**Non-primitives data types**  are unlike **primitives data type** because they can be reference which is why  they are called **referential** data type.  An **object** is  instance of  a **class**. After designing a **class** you can create countless number of **objects** and must importantly they have their properties and behavior a **class** defined.

What is an **instance of a class**? This still refers to an **object**. Object are tangible while **class** are just a rules that defines the properties and behavior of a class. 

#### Object Creation

An object creation happen when a **class** is *instantiated* by using the **new** keyword or operator. In the above we haven't really create **objects**, rather we have created references variable: `student, studnet2` of type **Student**. 

Let's begin creating **objects**

```java
public static void main(String[] args) {
	Student stu1 = new Student();
     stu1.rollNumber = 1390;
     stu1.name = "Hali Mass";
     stu1.mark = "85";
}
```

The `new Student();` is the actual *instantiation* of a **class**, the **object** is `stu1`. The **new** keyword dynamically allocate memory at **runtime** and return a **references** to it. Remember about the **stack and heap memory**, objects are stored in the **heap memory** but there references are stored in the **stack memory**. 

Memory allocation happens during object creation; **compile time:** `Student stu1` and **runtime:** `new Student();`.

#### Property and Behavior

A **class** defines property and behavior for **objects** at the **class ** level and a object have to provide those values. You can think of creating  empty variable that will some value later in your program. 

Property defines what a **object  has** while a behavior define what a **object can do**. Let's take an example of a *car*, a *car* has physical feature such as **make, model, engine type, number of wheels** and a *car* perform certain action such as **start, move, break**. 

After defining the a **property and behavior** of a *car* we can begun constructing a **Car class**. The properties are going to store in an **instance variable** while behaviors are going to be define in a **function (method)**.

A **`car` has and `car` can do ** make up a **Car class** so those any other **class** you will ever construct or create. 

Construct a class with the following **properties and behaviors**:

1. Create a **Car class**
2. Define properties of a **Car**: `make, model, engine type, number of wheel`
3. Define behavior of a **Car**: `start, move, break`
  * Print the action being perform in the console.
4. Create a Car object with any of your choice as the name.
5. Assign values to the properties of your car
6. Call the behaviors of your car.

