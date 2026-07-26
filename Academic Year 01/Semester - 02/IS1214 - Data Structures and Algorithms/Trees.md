>[!info] Introduction
>A **Tree** is a non-linear data structure used to represent hierarchical relationships and organize data objects based on keys. Unlike linear structures, trees allow for the implementation of **faster algorithms**, specifically for searching and sorting.

# 1. Fundamental Terminology

- **Root:**
  The topmost node in a tree; if the root is NULL, the tree is empty.
- **Leaf Node:**
  A node that has **no children** (also called a terminal node).
- **Path:**
  A sequence of consecutive edges connecting distinct vertices.
- **Level Number:**
  The root is at level 0, and its children are at level 1; every child is at its **parent's level + 1**.
- **Height:**
  The length of the longest path from a node to a leaf node.
- **Depth:**
  The length of the path from the root to a specific node.

# 2. Binary Trees (BT)

A **Binary Tree** is a specific type of tree where each node has **at most two children**, usually called the left and right child.

- **Properties:** At any level $L$, a binary tree can have at most $2^L$ nodes. A **Full Binary Tree** of depth d has exactly $2^{d+1}−1$ total nodes.

- **Memory Representation:**
	- **Linked Representation:**
	  Each node has three parts: the data, a pointer to the left node, and a pointer to the right node.
	- **Sequential (Array) Representation:** 
	  The root is stored at index 1; for any parent at index $K$, its left child is at index $2K$ and its right child is at $2K+1$.

# 3. Tree Traversals

Traversal is the process of visiting every node in the tree exactly once.

- **Depth-First Search (DFS):**
	- **Pre-order:** Visit Root → Left → Right.
	- **In-order:** Visit Left → Root → Right.
	- **Post-order:** Visit Left → Right → Root.

- **Breadth-First Search (BFS):** Also called **Level-order traversal**, it visits nodes level by level from left to right using a **Queue** to track the children.

# 4. Binary Search Trees (BST)

A **BST** (or ordered binary tree) is a binary tree where nodes are arranged in a specific order to support **fast searching**

- **Key Property:** For every node, the **left sub-tree** values are **less than** the root, and the **right sub-tree** values are **greater than or equal to** the root.

- **Operations:**
	- **Search:**
	  Average time complexity is $O(\log n)$.
	- **Deletion:**
	  Categorized into three cases: deleting a leaf (no sons), deleting a node with one child (re-link parent to child), or deleting a node with two children (replace it with the rightmost node of the left sub-tree).
	- **Sorting:**
	  An **In-order traversal** of a BST will always visit the nodes in **increasing sorted order**.

# 5. AVL Trees (Self-Balancing)

An **AVL Tree** is a BST that automatically keeps itself balanced to ensure search operations stay efficient.

- **Balance Property:**
  For every node, the height of the left and right sub-trees can differ by **at most 1** (Balance Factor must be -1, 0, or 1).
- **Rotations:**
  If an insertion causes a node to become "out of balance," the tree performs **Single Rotations** (if nodes are in a straight line) or **Double Rotations** (if they form a "dog-leg" pattern) to fix it.

# 6. Special Applications: Expression Trees and Heaps

- **Expression Trees:**
  Used by compilers to evaluate math problems. **Internal nodes** store operators (+, -, *, /) and **leaf nodes** store operands (numbers/variables).
- **Heaps:**
  A special binary tree where every node is greater than or equal to its children. Heaps are the primary way to implement **Priority Queues**, where the highest priority item is always at the root.

---
# Short Note for Memory:

- **BST Rule:** Left < Root < Right.
- **AVL Rule:** Keeps the tree "short" using rotations so it doesn't become a long line.
- **Heap Rule:** Parent ≥ Children.
- **DFS vs. BFS:** DFS uses **Recursion**; BFS uses a **Queue**.
- **Array Mapping:** Parent K has children at 2K and 2K+1.

---
# Lecture Notes
![[DSA - Lecture 06.pdf]]
![[DSA - Lecture 07.pdf]]