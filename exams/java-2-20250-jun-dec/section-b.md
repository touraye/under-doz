1. Study the algorithm below and answer the following questions:

   ```java
   static void print(int n) {
       if (n > 5) {
           return; 
       }
       System.out.println(n);
       print(n + 1); 
   }
   ```

   1.  Describe the above function. (2 marks)
   2. Print the output for the above function. (1 mark)
   3. Discuss what `if (n > 5) return` is doing. (2 marks)

2. Discuss Big O Notation. (1 mark)

   1. Distinguish between time and space complexity. (2 marks) 

   2. Using the algorithm:

      ```java
      int[] arr = {10, 20, 30, 40};
              for (int num : arr) {
                  System.out.println(num);
              }
      ```

      determine its time complexity. (2 marks).

3. List the differences between a class and an object. (1 marks)

   1. List all the principles of Object Oriented Programming. (2 marks)
   2. List any three types of classes in Java. (1 mark)
   3. Discuss between method-overloading and method-overriding. (1 mark)

4. What are the two types of memory allocation/management in Java? (1 mark)

   1. List a difference between a compile and a run time. (1 mark)
   2. List the two main types of data structures in Java. (1 mark)
   3. List two differences between a stack and a queue. (2 mark)

5. What is a Collection? (1 mark)

   1. List the three core components of the Java Collection Framework.(2 marks)
   2. List one Interface of the Java Collection Framework. (1 marks)
   3. List at least two implementations of the above-mentioned Interface. (1 mark)