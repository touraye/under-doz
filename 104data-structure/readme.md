# Data Structure

### . **Java Collection Interface**:

- **Definition**: The `Collection` interface is a root interface in the Java Collections API, representing a group of objects. It defines the core methods that all collection classes should implement, such as `add()`, `remove()`, `size()`, and `iterator()`. It is a part of the larger collection framework.
- **Purpose**: The `Collection` interface provides a uniform way to interact with various types of collections (e.g., lists, sets, queues) by defining common operations.
- **Subinterfaces**: Some of its important subinterfaces include:
  - `List` (e.g., `ArrayList`, `LinkedList`)
  - `Set` (e.g., `HashSet`, `TreeSet`)
  - `Queue` (e.g., `PriorityQueue`, `LinkedList`)

**Example of the `Collection` Interface**:

```java
import java.util.Collection;
import java.util.ArrayList;

public class CollectionExample {
    public static void main(String[] args) {
        Collection<String> collection = new ArrayList<>();
        collection.add("Apple");
        collection.add("Banana");
        System.out.println(collection);
    }
}

```

In this example, the `Collection` interface is used to create an `ArrayList`, and we can add and manipulate elements using the methods defined in the `Collection` interface.

### **Java Collection Framework**:

- **Definition**: The **Java Collection Framework** refers to the entire architecture that provides a comprehensive set of classes and interfaces to store and manipulate groups of objects. The framework includes the `Collection` interface along with many other interfaces (`Map`, `List`, `Set`, `Queue`), classes (`ArrayList`, `HashSet`, `HashMap`), and algorithms (like sorting and searching). It is a unified framework for managing collections in Java.
- **Purpose**: The framework is designed to standardize the way collections of objects are handled, allowing for flexibility, reusability, and performance optimization. It encompasses both the interfaces that define the operations on collections and the concrete implementations of those interfaces (such as `ArrayList`, `HashMap`, etc.).
- **Components of the Collection Framework**:
  - **Interfaces**: Such as `Collection`, `List`, `Set`, `Queue`, `Map`.
  - **Concrete Classes**: Such as `ArrayList`, `HashSet`, `LinkedList`, `TreeSet`, `HashMap`.
  - **Utility Classes**: Like `Collections` and `Arrays`, which provide algorithms for sorting, searching, and other collection-related tasks.

**Example of the Collection Framework**:

```
import java.util.ArrayList;
import java.util.HashSet;
import java.util.HashMap;

public class CollectionFrameworkExample {
    public static void main(String[] args) {
        // List example (ArrayList)
        ArrayList<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");

        // Set example (HashSet)
        HashSet<String> set = new HashSet<>();
        set.add("Apple");
        set.add("Banana");

        // Map example (HashMap)
        HashMap<Integer, String> map = new HashMap<>();
        map.put(1, "Apple");
        map.put(2, "Banana");

        System.out.println("List: " + list);
        System.out.println("Set: " + set);
        System.out.println("Map: " + map);
    }
}

```



### Key Features of the Java Collection Framework:

1. **Unified Architecture**: All collection classes and interfaces are part of a standard, consistent framework.
2. **Dynamic Resizing**: Many collection classes automatically adjust their size as data is added or removed.
3. **Generics Support**: Collections can store objects of specific types, offering type safety and reducing the need for casting.
4. **High Performance**: Many of the collection classes, such as `ArrayList` or `HashMap`, are optimized for performance in different scenarios.

### Core Interfaces of Java Collection Framework:

1. Collection Interface

   : The root of the collection hierarchy. It represents a group of objects (also called elements). It has several subinterfaces:

   - **List**: An ordered collection (e.g., `ArrayList`, `LinkedList`).
   - **Set**: A collection that does not allow duplicate elements (e.g., `HashSet`, `TreeSet`).
   - **Queue**: A collection used to hold multiple elements prior to processing (e.g., `PriorityQueue`, `LinkedList`).

2. **Map Interface**: Represents a collection of key-value pairs (e.g., `HashMap`, `TreeMap`). It is not a part of the `Collection` interface, but it is included in the framework.

### Core Classes of the Collection Framework:

1. **ArrayList**: A resizable array implementation of the `List` interface.
2. **LinkedList**: A doubly linked list implementation of the `List` and `Queue` interfaces.
3. **HashSet**: An implementation of the `Set` interface that uses a hash table.
4. **TreeSet**: A `Set` implementation that uses a tree structure to order elements.
5. **HashMap**: A `Map` implementation based on a hash table. It stores data in key-value pairs.
6. **TreeMap**: A `Map` implementation based on a tree structure that orders its keys.

Hierarchy of the Collection Framework:

```java
java.util.Collection
    |-- List
        |-- ArrayList
        |-- LinkedList
        |-- Vector
    |-- Set
        |-- HashSet
        |-- LinkedHashSet
        |-- TreeSet
    |-- Queue
        |-- PriorityQueue
        |-- LinkedList

```

Map:

```java
java.util.Map
    |-- HashMap
    |-- TreeMap
    |-- LinkedHashMap
    |-- Hashtable
```

### Common Methods of Collection Interface:

- `add(E e)`: Adds an element to the collection.
- `remove(Object o)`: Removes an element from the collection.
- `clear()`: Removes all elements from the collection.
- `size()`: Returns the number of elements in the collection.
- `isEmpty()`: Checks if the collection is empty.
- `contains(Object o)`: Checks if a collection contains a specific element.
- `iterator()`: Returns an iterator to traverse the collection.

### Benefits of the Java Collection Framework:

1. **Reusability**: The framework provides common data structures, which can be reused in different programs without writing custom implementations.
2. **Type Safety**: With generics, the framework provides compile-time type checking, reducing runtime errors.
3. **Efficiency**: The classes in the framework are optimized for performance, with different classes suited to different types of tasks.
4. **Interoperability**: Since the collection classes implement common interfaces, they can easily interact with one another.