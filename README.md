# Heap-Java-
# Heap Implementation in Java (1-Based Indexing)

Index:      1     2     3     4     5     6     7

Value:     50    30    40    10    20    35    25

This project contains Java implementations of both **Max Heap** and **Min Heap** using **1-based indexing** with array representation. The heap is a complete binary tree that allows efficient insertion, deletion, and access to the maximum or minimum element.

---

## 📘 Why 1-Based Indexing?

We use 1-based indexing (i.e., the array starts from index `1` instead of `0`) to simplify parent-child relationships in a binary heap:

- **Parent of node at index `i`** = `i / 2`
- **Left child of node at index `i`** = `2 * i`
- **Right child of node at index `i`** = `2 * i + 1`

This eliminates the need for additional offset calculations required when using 0-based indexing, making the logic more intuitive and readable.

---

## 📂 Project Structure

/HeapProject
├── Max_Heap.java // Implements Max Heap (largest element at root)
├── Min_Heap.java // Implements Min Heap (smallest element at root)
└── Main.java // Example usage and test cases

pgsql
Copy
Edit

---

## 🔧 Core Heap Operations

### ✅ Max Heap
- **Insert**: Adds a new element and moves it up using `Swim`.
- **Delete / Extract Max**: Removes the root (maximum) and restores heap using `Sink`.
- **Build Heap**: Converts an unordered array to a valid heap.
- **Increase Key**: Increases a key’s value and swims it up.
- **Heap Sort**: Sorts in ascending order by turning the heap into a sorted array.

### ✅ Min Heap
- Similar logic but adjusted to maintain the **minimum element at the root**.

---

## 🚀 Execution Flow

### Max Heap Example

```java
int[] heap = new int[100]; // 1-based indexing
int n = 0;
Max_Heap maxHeap = new Max_Heap();

n = maxHeap.insert(heap, n, 20);
n = maxHeap.insert(heap, n, 15);
n = maxHeap.insert(heap, n, 30);

System.out.println("Max: " + maxHeap.peek(heap));  // Output: 30

n = maxHeap.delete(heap, n);

System.out.println("New Max: " + maxHeap.peek(heap)); // Output: 20
✅ Advantages of This Heap Implementation
Efficient Operations:

Insert, Delete, and Peek all run in O(log n) time.

Simple Indexing: 1-based indexing reduces bugs and improves clarity in parent/child calculation.

Flexible Structure: Can be used for both Max Heap and Min Heap with minor logic adjustments.

Fixed Array Size: Easy to manage and avoids dynamic memory issues.

💡 Applications of Heap
Priority Queues

Job Scheduling

Dijkstra’s Algorithm

Median Maintenance

Heap Sort

📌 Notes
Make sure the array size is large enough to avoid overflow (new int[100] for demo).

This is a classical academic implementation to understand heap mechanics.

For production, consider using Java's built-in PriorityQueue or Heap implementations with dynamic resizing.

👨‍💻 Author
This project was implemented as part of a university assignment in CSE220 - Data Structures, using Java with basic array structures and recursion. It is designed for educational purposes and a deeper understanding of heap internals.
