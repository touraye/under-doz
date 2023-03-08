# Java At First Look

Welcome to Java programming, I hope you are ready to learn one of the most awesome, and most used programming languages for building real-time applications. 

I hope your read all the materials in the `101-programming`. if yes then you are in good shape. 

*Prerequisite: You must have solid programming knowledge. considered you covered materials in `101-programming`*

[TOC]



## What Are We Going To Do

* We will talk a little more about Java(brief history),
*  The use cases of Java
* Why should you learn Java?
* How to download Java from the internet and more about JKD
* How to setup your development environment,
*  Command line versus IDE.

### What is Java

Java is an **Object-Oriented Programming Language** developed by **sonny Microsoft** in 1992. 

### Uses Of Java

* Java is used to build rich-enterprise applications 
* Java is used in Android app development
* Android operating system is built on Linux with Java
* Web development(build web server and web APIs)
* Internet of things and embedded devices
* Banking applications and ATM systems

### Why Should You Learn Java

Java is a well-respected language with many benefits. The mentioned above uses of Java are enough for someone considering taking a career in Java and also considered a great choice to start your programming journey with due to its strictness. We will see why Java is said to be a *strict language*. 

### How To Download Java

Well, there are many resources out there on the internet, but I would recommend using **Oracle** as they are the maintainer of Java. Java has evolved hence than with some many new features added to the language.

Java 19 is the newest version right now(at the time of my writing), but I would recommend downloading Java 17. Java 17 is the current standard version of Java which has the longest-term support(TLS). 

What do I mean by long-term support(LTS):
Well, software development involved the process of updating, adding a new feature, and depreciating other features as well. Every software undergoes these phases. 
So does Java, Java 17 has the newest updated features which are tested(free from bugs) and can be used in real-time software development, while the newest version(Java 19) does not have long-term support(LTS). 

A version that does not have the longest-term support is out to the general public for testing, people will use it, report back issues and the maintainers will fix those issues. These kinds of versions are not used by companies or individuals to build software.

To download Java on your Computer please follow this link [download java 17](https://www.oracle.com/in/java/technologies/downloads/#jdk17-windows), select your OS type , and proceed with your download.

### Why Do You Need To Download And Install Java 

Well, to be able to execute Java code on your computer you need to install Java which comes along with Java Development Kit aka JDK. Without this JDK you will not be able to execute Java codes on your machine.

JDK comprises other great software which is Java Virtual Machine and Java Runtime Environment.

Java Virtual Machine: This helps us to be able to execute our byte or object codes. As we discussed earlier computer only understands Machine codes(lower-level language) and therefore Java happens to be a higher-level language. The JVM will further process our bytes code into machine code for the CPU to be able to execute it.

Java Runtime Environment: This contains classes and libraries with predefined logic. We will use these predefined classes and libraries in our Java program later on.

### Set Up Your Path 

Now we successfully downloaded and installed Java it's time to set up our development environment aka dev environment. We need to tell our computer where to find the java we installed. *This is for only people running Windows computer* Mac OS and Linux takes off everything.

In steps: 

* Open your window file explorer
* Navigate to your C drive
* Open your `program files` folder(this folder contain your installed programs)
* Find a folder named `Java`, open it
* You should see one folder named `jdk-17.0.4`, and open it suppose you've downloaded Java-17
* You will see a list of sub-folder and files, among you, should see a folder with the name of the `bin`, open the `bin` folder
* Inside the `bin` folder, there are lots of sub-folders and files. See the preview:
* <img src="../assets/bin-folder.png"/>
* Point your cursor(mouse) to the highlighted red color shown in the image above it will highlight everything in that address bar(think of it like how you copy a URL in your browser). `Ctrl+c` copy to highlighted text.
* Now we have to go to our Environment variables, press the `Windows key,` and type `env` you see 'Edit the system environment variables, press on Enter key to open it
* Advance tap will be selected by default, at the bottom you should see a button `Environment Variables` click on it another window will open.
* There you will see the `User variable for pc-name`(this will set the path to the only logged use), and System Variables(will set the path for the entire e-system, and the user can access it). I prefer the `System Variable`.
* On the `System, Variables` select the `path` and click the `edit` button. Another small window will pop up, but two ways are done depending on your system.
  * The way my system shows it: 
  * <img src="../assets/evn.png"/>
  * You might not see all of the paths like the above, but it's ok. Click the `New` button a text area will be below the path, paste using `Ctrl+v` then `Ok`.
  * The other way; all the paths will appear in one line separated. The last path might not have an at the end, but if you have terminated it before you can add any other path after it.
  * Add a to the last path, paste `Ctrl+v,` and then Ok. That's it.

### Verify Java 

These are for all Operating Systems. Let's see whether Java is successfully installed on our computer. 

* Open your terminal or command prompt(on windows: `windows key + r` then type cmd and Ok)
* Type `java -version` and press on `enter key` this should show you the version of Java you have installed. Our case will be `java version "17.0.4" 2022-07-19 LTS`.
* Type `java` and press on `enter key` a man-page will appear with some other useful commands. Believe it or not, we are done!



### Java On The Command Line

Before we finally install an Integrated Development Environment aka IDE to write and compile our Java code we will learn how to use the command line with a notepad to write our first Java program.

Tip: If you're using Windows I highly recommend you download and install [git](hppt://git-scm.com) which comes with a `bash terminal the wWindowsPowerShell or the command prompt in some Window computer can run some bash commands. The `bash` is the default for Mc OS and Linux, for Mc and Linux life is good! 

Let's get into it:

* Let's begin by creating a directory/folder on our Desktop preferably name it java

* Open your terminal or git bash.

* You want to make sure these two windows and next to each meaning:

* Type `cd` in your terminal or git bash then press on the spacebar to create a space

* <img src="../assets/window-side-by-side.png"/>

* Drag and drop your java folder in the terminal or git bash window. You should see something like this 'cd C:\Users\ebrima\Desktop\java' then click on enter key this should take you to the java directory.

* Let's confirm we are sitting in the right directory, type `pwd` and these should show up `/c/Users/ebrima/Desktop/java`. Off course a different username, mine is ebrima.

* Type `touch Main.java` and press enter this will create a file name Main or Main.java depending on your OS.

* Run the `ls` command to see the file

* You can double click on the file to open it with notepad or use the terminal by typing the name of your text editor and the file name with the file extension. `notepad Main.java` and enter.

* Copy the following code snippets  and paste them into your file opened in notepad then `Ctrl+s` to save

  ```java
  public class Main {
  	public static void main(String[] args){
  	System.out.ptintln("Hellow World!");
  }
  }
  ```

* Run `cat Main.java` this will preview the content of the file in your terminal/git bash. Now we are in good shape, let's try to compile this code by invoking the java-compiler

* Run `javac Main.java` in your terminal/git bash. Hope you do not see anything coming out? that's perfect because your code has been compiled successfully

* Run `ls` you see two files all named Main but with different files extension(.java, and .class)

* Now is the time to execute our code to see the print message. Run `java Main.java ` or just `java Main` not `Main.class`

* Congratulations if you see Hello World! printed in your terminal/git bash

* Let's modify our program a bit, move to notepad, copy the code below, and paste the code below the first print statement

* ```java
  System.out.println(2+2)
  ```

* Save it and go to your terminal and run `javac Main.java` to compile it again. Am sure this time an error is going to throw at you because we don't terminate the print statement we just added. May some of have spotted it!

* Correct the error, save it, compile it, and execute it you should see Hello World! and 4

## Install An IDE

Well, learning Java really requires having an IDE(integrated development environment). This will help us with many things like syntax highlighting, code formatting, suggestions, and many more.

I will be using IntelliJ IDE, but you can use any IDE of your choice. To download IntelliJ [navigate to the official site](https://www.jetbrains.com/idea/download/#section=windows), and make sure your download the Community Edition(free for everyone to download and use, the ultimate is paid).

Upon installing IntelliJ IDE you check 'set path, and check java for language'. That should be good