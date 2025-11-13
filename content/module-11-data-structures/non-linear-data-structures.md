## **Non-Linear Data Structures**

Non-linear data structures organize data in hierarchical, interconnected, or relational ways where elements don't follow a sequential arrangement. Unlike linear structures where each element has exactly one predecessor and successor, non-linear structures allow each element to connect to multiple others, enabling more complex relationships and efficient operations for specific use cases. These structures are essential for representing real-world scenarios like organizational charts, social networks, database indexing, and file systems.

**Key Characteristics**:

- Elements have multiple relationships (not just sequential)
- Hierarchical or graph-based organization
- Often provide faster search/retrieval for specific operations
- More complex to implement but offer powerful capabilities

**Topics to cover:**

* Tree
* Graph
* HashMap

### **1. Tree (TreeSet & TreeMap)**

**Explanation**: Hierarchical structure where each node has a parent and children. TreeSet and TreeMap use Red-Black trees for self-balancing.

```java
import java.util.TreeSet;
import java.util.TreeMap;
import java.util.NavigableSet;
import java.util.Map;

public class TreeExample {
    public static void main(String[] args) {
        // TreeSet - stores unique elements in sorted order
        TreeSet<Integer> treeSet = new TreeSet<>();
        
        treeSet.add(50);
        treeSet.add(20);
        treeSet.add(80);
        treeSet.add(10);
        treeSet.add(30);
        treeSet.add(70);
        treeSet.add(90);
        
        System.out.println("TreeSet (sorted): " + treeSet);
        
        // NavigableSet operations
        System.out.println("\nNavigableSet Operations:");
        System.out.println("First element: " + treeSet.first());          // 10
        System.out.println("Last element: " + treeSet.last());            // 90
        System.out.println("Lower than 25: " + treeSet.lower(25));        // 20
        System.out.println("Higher than 25: " + treeSet.higher(25));      // 30
        System.out.println("Floor of 25: " + treeSet.floor(25));          // 20
        System.out.println("Ceiling of 25: " + treeSet.ceiling(25));      // 30
        
        // Subset operations
        System.out.println("HeadSet (less than 50): " + treeSet.headSet(50));
        System.out.println("TailSet (greater than or equal to 50): " + treeSet.tailSet(50));
        System.out.println("SubSet (30 to 70): " + treeSet.subSet(30, 70));
        
        // TreeMap - key-value pairs sorted by keys
        TreeMap<String, Integer> studentGrades = new TreeMap<>();
        
        studentGrades.put("Alice", 85);
        studentGrades.put("Bob", 92);
        studentGrades.put("Charlie", 78);
        studentGrades.put("Diana", 95);
        studentGrades.put("Eve", 88);
        
        System.out.println("\nTreeMap (sorted by name): " + studentGrades);
        
        // NavigableMap operations
        System.out.println("\nFirst entry: " + studentGrades.firstEntry());
        System.out.println("Last entry: " + studentGrades.lastEntry());
        System.out.println("Lower key than 'D': " + studentGrades.lowerKey("D"));
        System.out.println("Floor key for 'Charlie': " + studentGrades.floorKey("Charlie"));
        
        // Iterating through TreeMap
        System.out.println("\nStudent grades (sorted):");
        for (Map.Entry<String, Integer> entry : studentGrades.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
        
        // Performance
        System.out.println("\nTree Performance (Red-Black Tree):");
        System.out.println("Insertion: O(log n)");
        System.out.println("Deletion: O(log n)");
        System.out.println("Search: O(log n)");
        System.out.println("Traversal in order: O(n)");
    }
}
```

**When to Use Tree Structures**:

- When you need elements sorted automatically
- For range queries and navigation operations
- When you need predictable O(log n) performance
- For hierarchical data representation
- When you need ordered iteration

---

### **2. Graph**

**Explanation**: Collection of nodes (vertices) connected by edges. No built-in implementation in Java - must be custom implemented.

```java
import java.util.*;

public class GraphExample {
    
    // Graph representation using adjacency list
    static class Graph {
        private Map<Integer, List<Integer>> adjList;
        
        public Graph() {
            adjList = new HashMap<>();
        }
        
        // Add vertex
        public void addVertex(int vertex) {
            adjList.putIfAbsent(vertex, new ArrayList<>());
        }
        
        // Add edge (undirected)
        public void addEdge(int src, int dest) {
            adjList.get(src).add(dest);
            adjList.get(dest).add(src); // For directed graph, remove this line
        }
        
        // Get neighbors
        public List<Integer> getNeighbors(int vertex) {
            return adjList.getOrDefault(vertex, new ArrayList<>());
        }
        
        // BFS traversal
        public void bfs(int startVertex) {
            Set<Integer> visited = new HashSet<>();
            Queue<Integer> queue = new LinkedList<>();
            
            queue.offer(startVertex);
            visited.add(startVertex);
            
            System.out.print("BFS: ");
            while (!queue.isEmpty()) {
                int current = queue.poll();
                System.out.print(current + " ");
                
                for (int neighbor : getNeighbors(current)) {
                    if (!visited.contains(neighbor)) {
                        visited.add(neighbor);
                        queue.offer(neighbor);
                    }
                }
            }
            System.out.println();
        }
        
        // DFS traversal
        public void dfs(int startVertex) {
            Set<Integer> visited = new HashSet<>();
            System.out.print("DFS: ");
            dfsRecursive(startVertex, visited);
            System.out.println();
        }
        
        private void dfsRecursive(int current, Set<Integer> visited) {
            visited.add(current);
            System.out.print(current + " ");
            
            for (int neighbor : getNeighbors(current)) {
                if (!visited.contains(neighbor)) {
                    dfsRecursive(neighbor, visited);
                }
            }
        }
        
        // Display graph
        public void display() {
            for (Map.Entry<Integer, List<Integer>> entry : adjList.entrySet()) {
                System.out.println(entry.getKey() + " -> " + entry.getValue());
            }
        }
    }
    
    public static void main(String[] args) {
        Graph graph = new Graph();
        
        // Add vertices
        for (int i = 0; i < 6; i++) {
            graph.addVertex(i);
        }
        
        // Add edges
        graph.addEdge(0, 1);
        graph.addEdge(0, 2);
        graph.addEdge(1, 3);
        graph.addEdge(2, 4);
        graph.addEdge(3, 5);
        graph.addEdge(4, 5);
        
        System.out.println("Graph Structure:");
        graph.display();
        
        System.out.println("\nGraph Traversals:");
        graph.bfs(0);
        graph.dfs(0);
        
        // Practical example: Social network
        Graph socialNetwork = createSocialNetwork();
        System.out.println("\n=== Social Network ===");
        socialNetwork.display();
        System.out.println("Friends of User 2: " + socialNetwork.getNeighbors(2));
    }
    
    public static Graph createSocialNetwork() {
        Graph socialNetwork = new Graph();
        
        // Users
        for (int i = 1; i <= 5; i++) {
            socialNetwork.addVertex(i);
        }
        
        // Friendships
        socialNetwork.addEdge(1, 2); // User1 is friends with User2
        socialNetwork.addEdge(1, 3);
        socialNetwork.addEdge(2, 4);
        socialNetwork.addEdge(3, 4);
        socialNetwork.addEdge(4, 5);
        
        return socialNetwork;
    }
}
```

**When to Use Graphs**:

- Social networks and relationships
- Network routing and connectivity
- Recommendation systems
- Web page linking
- Any complex relationship modeling

---

### **3. HashMap (Hash Table)**

**Explanation**: Key-value storage using hash function for O(1) average-case operations. Uses array of buckets with linked lists or trees for collision resolution.

```java
import java.util.HashMap;
import java.util.Map;
import java.util.Set;

public class HashMapExample {
    public static void main(String[] args) {
        // Creating HashMap
        HashMap<String, Integer> studentScores = new HashMap<>();
        
        // Adding key-value pairs - O(1) average case
        studentScores.put("Alice", 95);
        studentScores.put("Bob", 87);
        studentScores.put("Charlie", 92);
        studentScores.put("Diana", 78);
        studentScores.put("Eve", 100);
        
        System.out.println("HashMap: " + studentScores);
        
        // Accessing values - O(1) average case
        System.out.println("\nAccess Operations:");
        System.out.println("Alice's score: " + studentScores.get("Alice"));
        System.out.println("Contains key 'Bob'? " + studentScores.containsKey("Bob"));
        System.out.println("Contains value 100? " + studentScores.containsValue(100));
        
        // Updating values
        studentScores.put("Charlie", 89); // Update existing key
        studentScores.replace("Diana", 85); // Update only if key exists
        
        // Remove operations
        studentScores.remove("Eve");
        studentScores.remove("Bob", 87); // Remove only if key-value pair matches
        
        System.out.println("After updates: " + studentScores);
        
        // Iterating through HashMap
        System.out.println("\nIteration Methods:");
        
        System.out.println("1. Using keySet():");
        for (String name : studentScores.keySet()) {
            System.out.println("Key: " + name + ", Value: " + studentScores.get(name));
        }
        
        System.out.println("\n2. Using entrySet():");
        for (Map.Entry<String, Integer> entry : studentScores.entrySet()) {
            System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());
        }
        
        System.out.println("\n3. Using forEach (Java 8+):");
        studentScores.forEach((key, value) -> 
            System.out.println("Key: " + key + ", Value: " + value));
        
        // Useful methods
        System.out.println("\nUtility Methods:");
        System.out.println("Size: " + studentScores.size());
        System.out.println("Is empty? " + studentScores.isEmpty());
        
        // getOrDefault - avoids NullPointerException
        System.out.println("Frank's score: " + studentScores.getOrDefault("Frank", -1));
        
        // putIfAbsent - add only if key doesn't exist
        studentScores.putIfAbsent("Frank", 75);
        System.out.println("After putIfAbsent: " + studentScores);
        
        // Practical example: Word frequency counter
        String text = "hello world hello java world programming java hello";
        Map<String, Integer> wordFrequency = countWordFrequency(text);
        
        System.out.println("\n=== Word Frequency ===");
        System.out.println("Text: " + text);
        System.out.println("Word frequencies: " + wordFrequency);
        
        // Performance characteristics
        System.out.println("\nHashMap Performance:");
        System.out.println("Average case - O(1) for put, get, remove");
        System.out.println("Worst case (all collisions) - O(n)");
        System.out.println("Load factor: 0.75 (default)");
        System.out.println("Resizing: automatic when threshold reached");
    }
    
    public static Map<String, Integer> countWordFrequency(String text) {
        Map<String, Integer> frequencyMap = new HashMap<>();
        String[] words = text.split(" ");
        
        for (String word : words) {
            frequencyMap.put(word, frequencyMap.getOrDefault(word, 0) + 1);
        }
        
        return frequencyMap;
    }
}
```

**When to Use HashMap**:

- When you need fast key-based lookups
- For caching mechanisms
- Counting frequencies and occurrences
- Database indexing simulation
- When insertion order doesn't matter

---

## **Summary: When to Choose Which**

### **Linear vs Non-Linear**

- **Use Linear** when data has natural sequence or order of processing
- **Use Non-Linear** for complex relationships, hierarchies, or fast key-based access

### **Specific Use Cases**

| Data Structure | Best For                                        | Avoid When                                    |
| -------------- | ----------------------------------------------- | --------------------------------------------- |
| **Array**      | Fixed size, maximum performance, primitives     | Size is unknown or needs to change frequently |
| **ArrayList**  | Frequent random access, iteration               | Frequent insertions/deletions at beginning    |
| **LinkedList** | Frequent insertions/deletions, queue operations | Frequent random access by index               |
| **Stack**      | LIFO processing, backtracking, DFS              | FIFO processing needed                        |
| **Queue**      | FIFO processing, BFS, task scheduling           | LIFO processing needed                        |
| **Tree**       | Sorted data, range queries, navigation          | Insertion order or unsorted data needed       |
| **Graph**      | Complex relationships, networks, paths          | Simple linear or hierarchical data            |
| **HashMap**    | Fast lookups, caching, frequency counting       | Ordered iteration or sorted data needed       |

### **Performance Comparison**

| Operation           | Array/ArrayList | LinkedList | HashMap | TreeMap  |
| ------------------- | --------------- | ---------- | ------- | -------- |
| **Access**          | O(1)            | O(n)       | O(1)    | O(log n) |
| **Insert (end)**    | O(1) amortized  | O(1)       | O(1)    | O(log n) |
| **Insert (middle)** | O(n)            | O(1)       | O(1)    | O(log n) |
| **Search**          | O(n)            | O(n)       | O(1)    | O(log n) |
| **Delete**          | O(n)            | O(1)       | O(1)    | O(log n) |

Choose based on your specific use case, performance requirements, and data characteristics!