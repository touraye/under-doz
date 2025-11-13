# **Linear Data Structures**

Linear data structures store elements in a sequential order, where each element connects to the next and previous. They’re simple, easy to traverse, and represent real-world sequences like queues, trains, or book pages.

**Key Characteristics**:

- Elements are arranged in sequential order
- Each element (except first and last) has exactly one predecessor and one successor
- Simple to implement and understand
- Efficient for sequential access patterns
- Memory can be contiguous (arrays) or non-contiguous (linked lists)

**Topic to cover:**

* Array
* ArrayList
* LinkedList
* Stack
* Queue

### **1. Array**
**Explanation**: An array is a fixed-size, contiguous memory block storing homogeneous elements, enabling instant index-based access but prohibiting dynamic resizing.

```java
import java.util.Arrays;

public class ArrayExample {
    public static void main(String[] args) {
        // Declaration and initialization
        int[] numbers = {10, 20, 30, 40, 50};
        
        // Accessing elements - O(1) time complexity
        System.out.println("First element: " + numbers[0]); // 10
        System.out.println("Third element: " + numbers[2]); // 30
        
        // Modifying elements
        numbers[1] = 25;
        
        // Length of array
        System.out.println("Array length: " + numbers.length); // 5
        
        // Iterating through array
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Index " + i + ": " + numbers[i]);
        }
        
        // Using Arrays utility class
        System.out.println("Array as string: " + Arrays.toString(numbers));
        
        // Sorting
        int[] unsorted = {5, 2, 8, 1, 9};
        Arrays.sort(unsorted);
        System.out.println("Sorted: " + Arrays.toString(unsorted));
    }
}
```

**When to Use**:
- When you know the exact size at compile time
- When you need maximum performance for random access
- For primitive types to avoid boxing overhead
- When memory efficiency is critical

---

### **2. ArrayList**
**Explanation**: Resizable array implementation of the List interface. Provides dynamic sizing while maintaining fast random access.

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Iterator;

public class ArrayListExample {
    public static void main(String[] args) {
        // Creating an ArrayList
        ArrayList<String> fruits = new ArrayList<>();
        
        // Adding elements - O(1) amortized
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add(1, "Mango"); // Insert at specific position
        
        System.out.println("ArrayList: " + fruits);
        
        // Accessing elements - O(1)
        System.out.println("First fruit: " + fruits.get(0));
        System.out.println("Contains Banana? " + fruits.contains("Banana"));
        
        // Removing elements
        fruits.remove("Orange"); // Remove by object
        fruits.remove(0);        // Remove by index
        
        // Size and empty check
        System.out.println("Size: " + fruits.size());
        System.out.println("Is empty? " + fruits.isEmpty());
        
        // Iterating through ArrayList
        System.out.println("\nIterating with for-each:");
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
        
        System.out.println("\nIterating with iterator:");
        Iterator<String> iterator = fruits.iterator();
        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
        
        // Sorting
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(5);
        numbers.add(1);
        numbers.add(8);
        numbers.add(2);
        
        Collections.sort(numbers);
        System.out.println("Sorted numbers: " + numbers);
        
        // Performance characteristics
        System.out.println("\nPerformance:");
        System.out.println("Random access: O(1)");
        System.out.println("Insert at end: O(1) amortized");
        System.out.println("Insert at beginning: O(n)");
        System.out.println("Search: O(n)");
    }
}
```

**When to Use ArrayList**:
- When you need frequent random access by index
- When most operations are at the end of the list
- When you need a resizable array-like structure
- When iteration performance is important

---

### **3. LinkedList**
**Explanation**: Doubly-linked list implementation where each element points to its predecessor and successor. Efficient for insertions/deletions but slower for random access.

```java
import java.util.LinkedList;
import java.util.ListIterator;

public class LinkedListExample {
    public static void main(String[] args) {
        // Creating a LinkedList
        LinkedList<String> students = new LinkedList<>();
        
        // Adding elements
        students.add("Alice");
        students.add("Bob");
        students.addFirst("Charlie");  // Add at beginning
        students.addLast("Diana");     // Add at end
        students.add(2, "Eve");        // Add at specific position
        
        System.out.println("LinkedList: " + students);
        
        // Accessing elements - O(n) for random access
        System.out.println("First: " + students.getFirst());
        System.out.println("Last: " + students.getLast());
        System.out.println("Element at index 2: " + students.get(2));
        
        // Removing elements
        students.removeFirst();
        students.removeLast();
        students.remove("Bob");
        
        System.out.println("After removals: " + students);
        
        // LinkedList as Deque (Double Ended Queue)
        students.offer("Frank");    // Add to end
        students.poll();            // Remove from front
        students.push("Grace");     // Push to front (stack operation)
        students.pop();             // Pop from front (stack operation)
        
        // Bidirectional traversal with ListIterator
        System.out.println("\nForward traversal:");
        ListIterator<String> forwardIterator = students.listIterator();
        while (forwardIterator.hasNext()) {
            System.out.println(forwardIterator.next());
        }
        
        System.out.println("\nBackward traversal:");
        ListIterator<String> backwardIterator = students.listIterator(students.size());
        while (backwardIterator.hasPrevious()) {
            System.out.println(backwardIterator.previous());
        }
        
        // Performance comparison
        System.out.println("\nPerformance:");
        System.out.println("Insert at beginning: O(1)");
        System.out.println("Insert at end: O(1)");
        System.out.println("Random access: O(n)");
        System.out.println("Insert at middle: O(n) for traversal + O(1) for insertion");
    }
}
```

**When to Use LinkedList**:
- When you have frequent insertions/deletions at beginning or middle
- When implementing stacks or queues
- When you need bidirectional traversal
- When memory allocation needs to be more flexible

---

### **4. Stack**
**Explanation**: LIFO (Last-In, First-Out) data structure. Elements are added and removed from the same end.

```java
import java.util.Stack;
import java.util.ArrayDeque;
import java.util.Deque;

public class StackExample {
    public static void main(String[] args) {
        // Using legacy Stack class (synchronized)
        Stack<Integer> legacyStack = new Stack<>();
        
        legacyStack.push(10);
        legacyStack.push(20);
        legacyStack.push(30);
        
        System.out.println("Legacy Stack: " + legacyStack);
        System.out.println("Top element: " + legacyStack.peek()); // 30
        System.out.println("Popped: " + legacyStack.pop());      // 30
        System.out.println("After pop: " + legacyStack);
        
        // Using ArrayDeque as Stack (recommended)
        Deque<Integer> stack = new ArrayDeque<>();
        
        // Stack operations
        stack.push(100);
        stack.push(200);
        stack.push(300);
        
        System.out.println("\nArrayDeque as Stack: " + stack);
        System.out.println("Top element: " + stack.peek()); // 300
        System.out.println("Popped: " + stack.pop());       // 300
        System.out.println("After pop: " + stack);
        
        // Practical example: Balanced parentheses checker
        String expression1 = "((2+3)*5)";
        String expression2 = "((2+3)*5";
        
        System.out.println("\nExpression 1 is balanced: " + isBalanced(expression1));
        System.out.println("Expression 2 is balanced: " + isBalanced(expression2));
    }
    
    public static boolean isBalanced(String expression) {
        Deque<Character> stack = new ArrayDeque<>();
        
        for (char ch : expression.toCharArray()) {
            if (ch == '(') {
                stack.push(ch);
            } else if (ch == ')') {
                if (stack.isEmpty()) {
                    return false; // Closing parenthesis without opening
                }
                stack.pop();
            }
        }
        
        return stack.isEmpty(); // True if all parentheses are matched
    }
}
```

**When to Use Stack**:
- For undo/redo functionality
- Expression evaluation and syntax parsing
- Backtracking algorithms
- Depth-First Search (DFS)
- Function call management (call stack)

---

### **5. Queue**
**Explanation**: FIFO (First-In, First-Out) data structure. Elements are added at the rear and removed from the front.

```java
import java.util.LinkedList;
import java.util.Queue;
import java.util.PriorityQueue;
import java.util.ArrayDeque;

public class QueueExample {
    public static void main(String[] args) {
        // LinkedList as Queue (FIFO)
        Queue<String> queue = new LinkedList<>();
        
        // Enqueue operations
        queue.offer("First");
        queue.offer("Second");
        queue.offer("Third");
        queue.offer("Fourth");
        
        System.out.println("Queue: " + queue);
        System.out.println("Front element: " + queue.peek()); // First
        
        // Dequeue operations
        System.out.println("\nProcessing queue:");
        while (!queue.isEmpty()) {
            System.out.println("Processing: " + queue.poll());
        }
        
        // PriorityQueue - elements ordered by natural ordering or comparator
        Queue<Integer> priorityQueue = new PriorityQueue<>();
        
        priorityQueue.offer(30);
        priorityQueue.offer(10);
        priorityQueue.offer(50);
        priorityQueue.offer(20);
        
        System.out.println("\nPriorityQueue (not stored in order): " + priorityQueue);
        System.out.println("Processing by priority:");
        while (!priorityQueue.isEmpty()) {
            System.out.println(priorityQueue.poll()); // Will output in sorted order
        }
        
        // ArrayDeque as Queue (more efficient than LinkedList for queue operations)
        Queue<String> arrayDequeQueue = new ArrayDeque<>();
        arrayDequeQueue.offer("Task1");
        arrayDequeQueue.offer("Task2");
        arrayDequeQueue.offer("Task3");
        
        System.out.println("\nArrayDeque as Queue:");
        while (!arrayDequeQueue.isEmpty()) {
            System.out.println("Processing: " + arrayDequeQueue.poll());
        }
        
        // Practical example: Task scheduler
        simulateTaskScheduler();
    }
    
    public static void simulateTaskScheduler() {
        Queue<String> taskQueue = new LinkedList<>();
        
        // Adding tasks
        taskQueue.offer("Task A - Process data");
        taskQueue.offer("Task B - Send email");
        taskQueue.offer("Task C - Generate report");
        taskQueue.offer("Task D - Backup database");
        
        System.out.println("\n=== Task Scheduler Simulation ===");
        int taskNumber = 1;
        while (!taskQueue.isEmpty()) {
            String currentTask = taskQueue.poll();
            System.out.println("Executing task " + taskNumber + ": " + currentTask);
            taskNumber++;
            
            // Simulate task execution time
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
        System.out.println("All tasks completed!");
    }
}
```

**When to Use Queue**:
- Task scheduling and job processing
- Breadth-First Search (BFS) algorithms
- Message passing systems
- Print job management
- Any FIFO processing scenario

---

