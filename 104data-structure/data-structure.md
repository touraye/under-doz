# Data Structure

A **data structure** is a specialized way of organizing, managing, and storing data so that it can be accessed and modified efficiently. It defines how data is arranged in memory and the operations that can be performed on that data. The choice of a data structure directly impacts the efficiency of algorithms in terms of time and space complexity.

### Key Characteristics of Data Structures:

1. **Organization**: Data structures help organize data logically and provide a framework to store and access data effectively.
2. **Efficiency**: Different data structures are optimized for different operations, such as searching, insertion, deletion, or traversal.
3. **Storage Management**: They help manage data in memory by providing efficient ways to store, retrieve, and manipulate data.
4. **Data Manipulation**: They support various operations like adding, removing, or updating data, depending on the specific type of structure.

### Types of Data Structures:

#### 1. **Linear Data Structures**:

In linear data structures, elements are arranged in a sequential manner, and each element is connected to its previous and next element.

- **Array**: A fixed-size, contiguous block of memory that stores elements of the same data type. Example: `int[] arr = {1, 2, 3, 4};`
- **Linked List**: A list where each element (node) contains a data part and a reference (or pointer) to the next node. Example: Singly linked list, doubly linked list.
- **Stack**: A collection that follows the **Last In First Out (LIFO)** principle. You can only insert and remove elements from the top. Example: Plate stacking.
- **Queue**: A collection that follows the **First In First Out (FIFO)** principle. Elements are inserted from the rear and removed from the front. Example: Line at a bank.

#### 2. **Non-linear Data Structures**:

Non-linear data structures allow elements to be arranged in hierarchical or interconnected ways, where not all elements are necessarily arranged in a sequence.

- **Tree**: A hierarchical structure where each element (node) has a value and references to child nodes. A tree starts with a root node and grows downward. Example: Binary trees, AVL trees.
- **Graph**: A collection of nodes (vertices) and edges that connect them. Graphs are used to represent networks. Example: Social networks, road maps.

#### 3. **Hash-based Data Structures**:

- **Hash Table**: A data structure that uses a hash function to map keys to values. It allows for quick access, insertion, and deletion of key-value pairs. Example: `HashMap` in Java.

### Common Operations on Data Structures:

- **Insertion**: Adding an element to the data structure.
- **Deletion**: Removing an element from the data structure.
- **Search**: Finding an element in the data structure.
- **Traversal**: Accessing all elements in a data structure.
- **Sorting**: Arranging elements in a specific order (e.g., ascending or descending).
- **Access**: Retrieving an element from the data structure.

### Example of Data Structures in Practice:

1. **Array Example**:

   ```java
   int[] arr = {1, 2, 3, 4, 5};  // Array of integers
   System.out.println(arr[2]);    // Accessing the third element
   
   ```

2. **Linked List Example**:

   ```java
   class Node {
       int data;
       Node next;
   
       Node(int data) {
           this.data = data;
           this.next = null;
       }
   }
   
   public class LinkedListExample {
       public static void main(String[] args) {
           Node head = new Node(1);   // First node
           head.next = new Node(2);   // Second node
           head.next.next = new Node(3);  // Third node
   
           // Traversing the linked list
           Node temp = head;
           while (temp != null) {
               System.out.println(temp.data);  // Printing node data
               temp = temp.next;
           }
       }
   }
   
   ```

3. **Stack Example**:

   ```java
   import java.util.Stack;
   
   public class StackExample {
       public static void main(String[] args) {
           Stack<Integer> stack = new Stack<>();
           stack.push(10);  // Add element
           stack.push(20);  // Add element
           System.out.println(stack.pop());  // Remove top element (20)
           System.out.println(stack.peek());  // Peek at the top element (10)
       }
   }
   
   ```

4. **Hash Map Example**:

   ```java
   import java.util.HashMap;
   
   public class HashMapExample {
       public static void main(String[] args) {
           HashMap<String, Integer> map = new HashMap<>();
           map.put("Apple", 1);
           map.put("Banana", 2);
           System.out.println(map.get("Apple"));  // Access value for the key "Apple"
       }
   }
   
   ```

### Importance of Choosing the Right Data Structure:

The efficiency of your program often depends on selecting the most appropriate data structure for the task. For instance:

- **Array**: Ideal when you need random access and a fixed-size structure.
- **Linked List**: Useful when you expect frequent insertions and deletions.
- **Hash Table**: Best for quick lookups of key-value pairs.
- **Tree**: Suitable for hierarchical data representation and sorted data retrieval.
- **Graph**: Used in scenarios like social networks, roadmaps, and network topologies.