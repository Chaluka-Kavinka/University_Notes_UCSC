- **Course Code** : IS 1214
- **Course Name** : Data Structures and Algorithms
- **Lecture** : Prof. Noel Fernando

#Lesson-Plan 

>[!Goals]
>The goal of this course is to provide a comprehensive understanding of **Data Structures and Algorithms (DSA)**, specifically focusing on the efficient organization, storage, and manipulation of data within a computer. It bridges the gap between theoretical algorithm design and practical implementation in C, ensuring that data is handled in ways that optimize memory utilization and processing speed.

---
# Learning Objectives

- **Defining and Categorizing Data Structures:** Distinguish between **linear** (arrays, stacks, queues, linked lists) and **non-linear** (trees, graphs) structures.

- **Developing Efficient Algorithms:** Write well-defined, finite, and effective **pseudo-code and algorithms** to solve computational problems.

- **Mastering Memory Management:** Utilize **dynamic memory allocation** functions in C, such as `malloc()`, `calloc()`, and `free()`, to manage data at runtime.

- **Implementing Abstract Data Types (ADTs):** Understand and code the fundamental operations for **Stacks (LIFO)** and **Queues (FIFO)**, including handling overflow and underflow conditions.

- **Manipulating Linked Lists:** Create and manage various list types—including **singly, doubly, circular, and header linked lists**—through insertion, deletion, and traversal.

- **Solving Complex Problems:** Apply structures to real-world applications such as **polynomial representation**, **mathematical expression evaluation**, and recursive puzzles like the **Towers of Hanoi**.

# Topic Covered

1. [[Introduction & Arrays]]
	- Definitions of data structures and their importance in Computer Science.
	- Qualities of a good algorithm and the use of flowcharts/pseudo-code.
	- **Array properties**: Finite, ordered, and homogeneous collections.
	- Basic array operations: Traversing, inserting, deleting, searching, sorting, and merging.

2. [[Stacks]]
	- The **LIFO (Last-In, First-Out)** principle and the Stack ADT.
	- Core operations: `Push`, `Pop`, `Peek`, `isEmpty`, and `isFull`.
	- **Stack applications**: Reversing lists, checking for balanced parentheses, and converting arithmetic expressions (Infix, Post-fix, Prefix).
	- Recursive solutions using stacks, specifically for the **Towers of Hanoi**.

3. [[Queues]]
	- The **FIFO (First-In, First-Out)** principle and Queue ADT.
	- Linear queue implementation and the logic for `Enqueue` and `Dequeue`.
	- **Circular Queues**: Overcoming the limitations of linear queues regarding memory gaps.
	- **Priority Queues and Heaps**: Using binary trees (heaps) to manage elements by priority and performing **Heap Sort**.

4. [[Link Lists & Double Link Lists]]
	- Comparison between arrays and linked lists (fixed vs. dynamic size).
	- **Dynamic memory management** in C using pointers and heap memory.
	- **Singly Linked List** structure: Data fields and "next" pointers.
	- Basic list operations: Creating nodes, building a list of 'n' nodes, traversing, and searching.
	- Advanced operations: Deleting nodes from the beginning, end, or after a specific node.
	- **Doubly Linked Lists**: Two-way navigation using "next" and "prev" pointers.
	- **Circular and Header Linked Lists**: Lists where the last node points back to the start or lists containing a special header node.
	- Practical application: Representing **polynomials** using linked lists for mathematical operations.

5. [[Trees]]
	- **Defining and applying tree terminology**, such as root, leaf node, ancestor, descendant, level number, degree, height, and depth.
	- **Distinguishing between tree types**, including general trees, binary trees, full binary trees, and complete binary trees.
	- **Implementing memory representations**, specifically comparing sequential (array-based) and linked representations for binary trees.
	- **Mastering traversal algorithms**, including depth-first schemes (Pre-order, In-order, Post-order) and breadth-first schemes (Level-order).
	- **Constructing and manipulating Binary Search Trees (BSTs)**, including performing search, insertion, and complex deletion operations.
	- **Understanding self-balancing structures**, specifically the AVL tree balance property and the use of single and double rotations to correct imbalances.
	- **Utilizing trees for practical applications**, such as calculating the size/height of a tree, building expression trees for mathematical evaluation, and creating dictionary structures.

6. [[Sorting Methods]]
	- **1. Basic Sorting Techniques (Part A)**
		- **Selection Sort:** Finds the smallest element and exchanges it with the first position, repeating for the rest of the array.
		- **Insertion Sort:** Builds the sorted list one item at a time by comparing and inserting elements into their proper place.
		- **Bubble Sort (Sorting by Exchange):** Repeatedly compares adjacent elements and swaps them if they are in the wrong order.
	- **2. Advanced Comparison-Based Sorting (Parts B, C, and D)**
		- **Merge Sort:** A "divide and conquer" algorithm that recursively divides the array into halves, sorts them, and merges them back together.
		- **Shell Sort:** An improvement over insertion sort that allows for the exchange of elements that are far apart using a "gap" or increment.
		- **Quick Sort:** Another "divide and conquer" method that partitions the array around a selected "pivot" element.
		- **Heap Sort:** Utilizes a **Heap** data structure (a special binary tree where parents are ≥ children) to sort elements efficiently.
	- **3. Non-Comparison-Based Sorting (Part E)**
		- **Counting Sort:** Efficient when the range of input values is small; it counts the frequency of each distinct element.
		- **Radix Sort:** A linear sorting algorithm for integers that processes data digit-by-digit, starting from the least significant digit.
		- **Bucket Sort:** Distributes elements into various "buckets," sorts each bucket individually, and then concatenates the results.
	- **Factors Considered in Sorting**
	  The lecture also emphasizes important performance metrics for these algorithms:
		- **Speed:** Simple algorithms are typically $O(N^2)$, while advanced ones are $O(N\log{N})$.
		- **Storage:** Some algorithms sort "in place" $(O(N) memory)$, while others require extra space.
		- **Stability:** Whether the algorithm preserves the relative order of records with equal keys.

7. [[Complexity and Analysis of Algorithms]]
   This section moves from implementing data structures to mathematically evaluating how well they perform.
	- **1. Algorithm Characteristics:** Defining the essential trials fro an algorithm, such as **finieness, definiteness, and effectiveness**.
	- **2. Asymptotic Notations:**
		- **Big O Notation:** Used to describe the upper bound (worst-case) of an algorithm's growth.
		- **Theta Notation ($\theta$):** Used for analyzing average-case complexity.
	- **3. Complexity Classes:** Categorizing algorithms from best to worst: $O(1) (Constant)$, $O(\log n) (Logarithmic)$, $O(n) (Linear)$, $O(n \log n) (Linearithmic)$, $O(n^2) (Quadratic)$, and $O(2^n) (Exponential)$.
	- **4. Factors Influencing Speed:** Exploring how algorithmic efficiency, hardware (CPU/RAM), and environmental factors (OS overhead) affect performance.
	- **5. Practical Analysis:** Calculating the complexity of loops, nested loops, and recursive functions like Factorials and **Fibonacci numbers**.

8. [[Graphs]]
	- **Graph Anatomy:** Defining **Vertices (nodes)** as entities and **Edges (arcs)** as the relationships between them $(G=(V,E))$.
	- **Graph Types:**
	    - **Directed vs. Undirected:** Whether connections have a specific one-way direction.
	    - **Weighted Graphs:** Graphs where edges have associated costs (e.g., distance between towns).
    - **Key Terminology:** Understanding concepts like **Adjacency** (connected nodes), **Path** (sequence of vertices), **Cycles**, and **Degree** (number of edges on a vertex).
    - **Representation Methods:**
	    - **Adjacency Matrix:** A 2D array (Boolean product) representing connections; useful for finding paths of specific lengths.
	    - **Adjacency List:** An array of linked lists, which is more memory-efficient for sparse graphs.
	- **Graph Traversal Algorithms:**
	    - **Depth-First Search (DFS):** Uses a **Stack** or recursion to explore as deep as possible along a branch before backtracking.
	    - **Breadth-First Search (BFS):** Uses a **Queue** to visit all neighboring nodes at the current level before moving deeper.
	- **Spanning Trees:** A sub-graph that connects all vertices without any cycles.
	- **Minimum Spanning Tree (MST):** In a weighted graph, the spanning tree that has the **lowest total edge cost**.
	- **Applications:** Using MSTs for civil network planning (power lines, water pipes), cluster analysis, and network routing.
	- **Prim’s Algorithm:** A specific method used to find the MST of a graph.
---
# Analogy for Understanding:

Think of these data structures as different ways to organize a **library**. An **array** is like a shelf of books where every slot is numbered; it's easy to find book #10, but if you want to squeeze a new book in the middle, you have to move every other book down. A **linked list** is more like a **scavenger hunt**: each clue (node) tells you where the next clue is. You can easily add a new clue anywhere by just updating the directions, but you have to start at the beginning to find anything at the end.