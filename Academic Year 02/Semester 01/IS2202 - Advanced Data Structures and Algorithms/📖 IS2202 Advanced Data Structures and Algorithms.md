- Course Code : IS 2202
- Course Name : Advanced Data Structures and Algorithms
- Lecture : Dr. Kasun Karunanayaka | Dr. Yohani Ranasinghe

#Lesson-Plan 


> [!Tip] Goal
> the overall goal of this lesson is to master complex data organizations and the algorithms required to manipulate them efficiently.

---
# The specific objectives broken down by the three core modules covered.

- **1. Graph Data Structures and Algorithms**
  The objective is to understand how to model real-world networks (like computer or road networks) where items are connected by relationships. Key goals include: Master different ways to represent graphs in memory using **Adjacency Matrices** and **Adjacency Lists**. Learn fundamental strategies for exploring graphs—**Breadth-First Search (BFS)** and **Depth-First Search (DFS)**—to find paths and check for connectivity. Solve complex graph problems such as finding **Strongly Connected Components** and performing **Topological Sorts**.

- **2. Tree Data Structures and Balancing**
  The objective is to move beyond simple linear structures to hierarchical ones that optimize data access. Key goals include: Understand the properties and terminology of various trees, including **Binary Trees** and **Binary Search Trees (BST)**. Learn how to maintain the efficiency of a tree by keeping it balanced. A major focus is the **Day–Stout–Warren (DSW) algorithm**, which transforms an unbalanced BST into a balanced one in linear time (O(n)) to minimize search height. Explore more complex multiway trees like **B-Trees** and **B+ Trees** often used in databases.

- **3. Hashing and Complexity of Algorithms**
  The objective is to achieve the fastest possible data retrieval—ideally O(1) time—by using key-based mapping. Key goals include: Compare different searching approaches such as **Jump Search**, **Interpolation Search**, and **Binary Search**. Design effective **Hash Functions** (using methods like Division, Multiplication, or Mid-Square) to spread data evenly across a table. Master **Collision Resolution** techniques, such as **Chaining** (using linked lists) and **Open Addressing** (Linear Probing, Quadratic Probing, and Double Hashing), to handle cases where two keys map to the same spot.
---
# Topics covered 

1. [[Graph Data Structures and Algorithms]]

	- **Fundamental Concepts:** Definition of graphs (vertices and edges) and real-world applications like road or computer networks.
	- **Graph Types:** Undirected, directed (digraphs), multi-graphs, weighted graphs, and special categories like **Bipartite Graphs** and **Hypergraphs**.
	- **Terminology:** Concepts such as paths, cycles (including **Hamiltonian Cycles**), connectivity, subgraphs, and spanning trees.
	- **Representations:** How to store graphs using **Adjacency Matrices** and **Adjacency Lists**, including comparisons of their memory and time complexity.
	- **Graph Traversal/Searching:**
		- **Breadth-First Search (BFS):** Using queues to find shortest paths.
		- **Depth-First Search (DFS):** Using stacks and backtracking, including **edge classification** (tree, forward, back, and cross edges).
	- **Advanced Algorithms:** Finding **Strongly Connected Components (SCC)** using graph transposes and performing **Topological Sorts**.
	
2. [[Tree Data Structures and Balancing]]

	- **Introduction to Trees:** Hierarchy-based structures, terminology (root, parent, child, leaf, levels, height), and common types like Binary and **Binary Search Trees (BST)**.
	- **Binary Tree Variations:** Differences between **Full, Complete, and Perfect Binary Trees**.
	- **Traversals:** In-order, Pre-order, and Post-order traversal methods.
	- **Tree Balancing:**
	    - **Local vs. Global Balancing:** Using rotations (left/right) to maintain efficiency.
	    - **The DSW (Day–Stout–Warren) Algorithm:** A linear time (O(n)) method to transform an unbalanced BST into a balanced one by first creating a "**vine**" (backbone) and then performing **compression**.
	- **Advanced Multiway Trees:** An introduction to **B-Trees** and **B+ Trees**, which are optimized for database storage.

3. [[Hashing and Searching Complexity]]

	- **Searching Strategies:** Comparison of different algorithms, including **Sequential/Linear Search**, **Binary Search**, **Jump Search**, and **Interpolation Search**.
	- **Direct-Address Tables:** Using keys as direct indices in an array.
	- **Hash Tables and Functions:**
	    - Designing effective **Hash Functions** using methods like Division, Multiplication, Mid-Square, Radix Transformation, and Folding.
	    - **Universal Hashing** and the **MAD Method** to prevent performance degradation from "malicious" key selections.
	- **Collision Resolution:**
	    - **Chaining:** Using linked lists (including overflow areas) to handle multiple keys at one index.
	    - **Open Addressing:** Techniques like **Linear Probing** (and its clustering issues), **Quadratic Probing**, and **Double Hashing**.
	- **Advanced Hashing:** **Perfect Hashing** for static data sets, which guarantees O(1) search time in the worst case.