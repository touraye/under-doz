# The Block

A block (`{}`) may be new to you, I assume. So, why should you learn about it? Well, when it comes to control structures, blocks play a significant role in programming. In fact, the **[building blocks of a Java program]()** showcase how blocks are used in defining a `class` and a `main` method.

A block (`{}`) is enclosed by two curly braces, and between these braces can be a single instruction or multiple instructions. As we dive deeper into control structures, we'll see the significance of blocks and how they help group related instructions together.

**Example syntax:**

```java
{
	// instruction goes here
}
```

Inside a block, it is legal to declare or initialize a variable, or even write an expression. Remember, any variable defined within a block is only visible within that block. For more details, refer to **[local variables]()**.

```java
{
	int temp; // temporarly is only visible with this block
    temp = a;
    System.out.println(a);
	System.out.println(temp);
}
```

A block becomes more programmatic when combined with control structures or even function creation. In fact, a block forms the body of `class`, `method` or `function`, and control structures. In the upcoming modules, you will learn how to leverage blocks to write robust programs.