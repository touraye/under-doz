# Data Structures

A **data structure** is a specialized way of organizing, managing, and storing data so that it can be accessed and modified efficiently. It defines how data is **arranged in memory** and the **operations that can be performed** on that data. The choice of a data structure directly impacts the efficiency of algorithms in terms of time and space complexity.

**Foundational Types:** Your data structures journey will begin with learning the foundational type provided by Java. This are of course primitives types that store only a single value at a given time. Other reference type like **Array and Java Collections Framework**.

## Types of Data Structures:

In Java data structures are categorized into two **Linear**  and **Non-Linear**

### **Linear Data Structures**
Elements are arranged in a sequential order, one after another. Each element has a unique predecessor and successor (except the first and last).

| Data Structure                 | Java Implementation(s)                                       | Key Characteristics                                          |
| :----------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| **Array**                      | `int[]`, `String[]`, etc. <br> `java.util.Arrays` (Utility Class) | Fixed-size, contiguous memory, fast index-based access.      |
| **Linked List**                | `LinkedList<E>` <br> (Doubly-linked)                         | Dynamic size, non-contiguous memory, efficient insertions/deletions. |
| **Stack**                      | `Stack<E>` (Legacy) <br> **`ArrayDeque<E>`** (Recommended)   | LIFO (Last-In, First-Out) principle.                         |
| **Queue**                      | `LinkedList<E>` <br> `PriorityQueue<E>` <br> `ArrayDeque<E>` | FIFO (First-In, First-Out) principle. `PriorityQueue` orders by priority. |
| **Deque** (Double-Ended Queue) | **`ArrayDeque<E>`** (Recommended) <br> `LinkedList<E>`       | Elements can be added/removed from both ends.                |

---

### **Non-Linear Data Structures**
Elements are not arranged sequentially. They form a hierarchical or graph-like structure where an element can be connected to multiple others.

| Data Structure | Java Implementation(s)                                       | Key Characteristics                                          |
| :------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| **Tree**       | `TreeSet<E>` <br> `TreeMap<K, V>`                            | Hierarchical structure. `TreeSet` and `TreeMap` use a **Red-Black Tree** internally. |
| **Graph**      | No built-in implementation. <br> Must be built using: <br> - `Collections` (e.g., `Map<Integer, List<Integer>>` for adjacency list) | A collection of nodes (vertices) and connections (edges).    |
| **Hash Table** | `HashSet<E>` <br> `HashMap<K, V>` <br> `LinkedHashSet<E>` <br> `LinkedHashMap<K, V>` | Uses a hash function to map keys to values for fast lookups. Not sequential, but not hierarchical either. It's often in its own category but is fundamentally non-linear. |

---

### Visual Summary

```
Data Structures in Java
│
├── Linear (Sequential)
│   ├── Array ([] & Arrays utility)
│   ├── List (ArrayList, LinkedList, Vector)
│   ├── Stack (Stack, ArrayDeque)
│   ├── Queue (LinkedList, PriorityQueue, ArrayDeque)
│   └── Deque (ArrayDeque, LinkedList)
│
└── Non-Linear (Hierarchical/Graph)
    ├── Tree (TreeSet, TreeMap)
    ├── Graph (Custom implementation)
    └── Hash Table (HashSet, HashMap, LinkedHashSet, LinkedHashMap)
```

### Key Takeaways:
*   **Use Linear structures** when your data has a natural sequence or order of processing (e.g., a list of tasks, a waiting line, a undo/redo history).
*   **Use Non-Linear structures** for more complex relationships:
    *   **Trees** are excellent for representing hierarchical data like file systems or for maintaining sorted order for fast searches.
    *   **Graphs** model networks like social connections or maps.
    *   **Hash Tables** provide the fastest average-time for lookups, insertions, and deletions based on a key.

