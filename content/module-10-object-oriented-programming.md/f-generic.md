# Generic Programming

Generic promote **type safety**, with generic the compiler act as a body-guard to your code thereby, prevent runtime error, and throwing compile time error. Before we get into generic I will talk you through a problem that will lead to compile-time a runtime error and use generic to solve the issue.

```java
List student = new ArrayList();
student.add("Ahmed");
student.add("Alieu");
student.add(60); // <-- the problem is here
```

**What happened?**

- The system accepted an integer into a list meant for strings.
- Java treats the list as containing `Object` only.
- The compiler cannot warn you.
- The error will appear *later* — when you try to use the value.

Let's say we want to assign to a variable like so: `String name = student.get(2);` The compile will force us to cast it.

```java
String name = student.get(2); // compile error : suggestion to cast in a String

String name = (String) student.get(2); // the compile assume this is safe, while it is not
```

Run your code and your program will crash: `ClassCastException`

This is the **type-safety problem**:

- No protection at compile time
- Wrong data type added accidentally
- Program crashes at runtime
- Difficult to debug

This is why generics were introduced.

## What is Generics

Generics in Java allow you to specify the **exact data type** for a class, interface, or method should work with, ensuring type-safety at compile time and preventing runtime errors caused by incompatible types.

Getting back with our problem we can specify the **exact type** for our `List` and that will ensure only `object` are add to `List`.

```java
List<String> student = new ArrayList<>(); // this is type safety

student.add("Ahmed");
student.add("Alieu");
student.add(60); // compile hint the error at compile-time
```

The `List<String>`  enforce only Strings to be add to the student list. How can I create `List` that will store primitive types? Primitive types cannot be directly use as types for a generic class, rather their **Wrapper class**. Each primitive data-type have their own wrapper class:

```java
List<Integer> nums = new ArrayList<>(); // Integer instead int
nums.add(30);
nums.add(10);
```

### Generic class

A **class** with a **type-parameter** is a **generic class**, the **type** is specify at the class level with a diamond (`<>`),  the type become generic meaning the class accept any type whenever it is be **instantiated**.

```java
class Student<E> {
    private E name;
    private E department;
    private E age;

    public Student(E name, E department, E age) {
        this.name = name;
        this.department = department;
        this.age = age;
    }
}

Student<String> stu1 = new Student<>("Lamin", "50", "19");
Student<String> stu2 = new Student<>("Lamin", "50", 19); // Compile error
```

`stu2` type-parameter is `String` and, therefore, providing other types will lead to compile error.

### Generic method

Assume we have `List` without a specifying its type:

```java
class MyStack {
     List items = new ArrayList();

    public void push(Object item) {
        items.add(item);
    }

    public Object pop() {
        return items.remove(items.size() - 1);
    }
}

MyStack stack = new MyStack();
stack.push("Mariama");
stack.push(new Date());
stack.push(10);

String firstItem = (String) stack.pop(); // will crash!
String secItem = (String) stack.pop(); // will crash!
String thirdItem = (String) stack.pop(); // will crash!

```

After running your code Java will throw a `ClassCastException` which the compile has ignored, assuming it is safe while it is not. This can be fixe with generic. The class `MyStack` will define a **type parameter** that will be use to as the type for our data structure and `push` and `pop` method.

```java
class GenericStack<T> {
    List<T> items = new ArrayList<>();

    public void push(T item) {
        items.add(item);
    }

    public T pop(){
        return items.remove(items.size() - 1);
    }
}

GenericStack<String> genericStack = new GenericStack<>();
genericStack.push("Mariama");
genericStack.push(new Date()); // compile error
genericStack.push(10); // compile error

```

The compile will catch the error due to adding wrong type another than `String` on to the stack. This safe guard your program, catch errors earlier when omitted by mistake, and fixed them with grace.