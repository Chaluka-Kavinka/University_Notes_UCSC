- **Course Code** : IS 2202
- **Course Name** : Advanced Data Structures and Algorithms
- **Lecture** : Dr. Kasun Karunanayaka | Dr. Yohani Ranasinghe

#Lesson-Plan 

> [!important] Goal
> The primary goal of this course is to develop advanced theoretical foundations and practical skills for designing, analyzing, and implementing complex data structures and efficient algorithms. The curriculum transitions from elementary sequential programming to rigorous asymptotic complexity analysis, multi-way search trees, global tree balancing, graph traversal paradigms, hashing techniques, greedy optimization, and data compression.

---
# The specific objectives of the module include:

- **Mastering Algorithmic Complexity:** Evaluating time vs. space complexity trade-offs, calculating instruction counts using the sequential computational model, and establishing asymptotic bounds ($O, \Omega, \Theta$).
- **Balancing Tree Structures:** Implementing tree rotations and applying global balancing algorithms like the Day-Stout-Warren (DSW) algorithm.
- **Disk-Optimized Indexing with B-Trees:** Understanding multi-way search trees, structural order $m$ constraints, bottom-up insertions with median promotion, and deletion with sibling borrowing and merging.
- **High-Performance Key-Value Retrieval:** Designing hash tables, analyzing division/multiplication hash functions, and resolving collisions using separate chaining and open addressing (linear probing, quadratic probing, double hashing).
- **Modeling & Traversing Relational Data:** Applying graph representations, executing Breadth-First Search (BFS) and Depth-First Search (DFS), classifying tree/back/forward/cross edges, performing Topological Sort, and computing Strongly Connected Components (SCC).
- **Solving Optimization Problems Greedily:** Applying the greedy-choice property and optimal substructure principles to problems like Fractional Knapsack and Activity Selection.
- **Data Compression & Information Theory:** Constructing optimal prefix codes using Huffman Coding and implementing Run-Length Encoding (RLE) to minimize digital data footprint.

---
# Topic Covered

1. [[Foundations of Algorithms & Graph Theory Fundamentals]]
	- **Algorithm Definition & Criteria:** Correctness, evaluating multiple algorithmic approaches, and computational resource complexity.
	- **Graph Theory Foundations:** Vertices, edges, directed vs. undirected, weighted graphs, self-loops, and multigraphs.
	- **Vertex Degrees & Handshaking Lemma:** In-degree, out-degree, isolated/pendant vertices, and proving the sum of degrees theorem.
	- **Specialized Graph Families:** Null, complete ($K_n$), regular, cycle ($C_n$), bipartite ($K_{m,n}$), and planar graphs with Euler's formula.
	- **Walks, Paths, and Cycles:** Classifying walks, trails, paths, circuits, cycles, connectivity, and tree properties.

2. [[Algorithm Analysis and Asymptotic Notations]]
	- **Time vs. Space Complexity:** Evaluating engineering trade-offs using the grocery shopping analogy.
	- **Sequential Computational Model:** Hardware-independent unit cost assumptions for assignments, comparisons, and arithmetic.
	- **Exact Instruction Counting:** Mathematical derivations for sequential code, single loops ($2n+2$), and nested loops ($3n^2+4n+2$).
	- **Linear Search Analysis:** Formal best-case $O(1)$, worst-case $3n+3$, and average-case $\frac{3}{4}n$ derivations.
	- **Asymptotic Notations ($O, \Omega, \Theta$):** Mathematical definitions, growth dominance, logarithm simplification rules, and standard complexity curves.

3. [[Tree Data Structures and DSW Tree Balancing]]
	- **Binary Search Tree (BST) Review:** BST ordering invariant, search/insert/delete operations, and in-order traversal sorting.
	- **Degenerate Trees & Need for Balancing:** Preventing $O(n)$ worst-case degradation through local vs. global balancing.
	- **Tree Rotations:** Mechanics and invariant preservation of Right Rotations and Left Rotations.
	- **The Day-Stout-Warren (DSW) Algorithm:** Phase 1 backbone/vine flattening ($O(n)$) and Phase 2 compression into a balanced BST ($O(n)$ time, $O(1)$ auxiliary space).

4. [[B-Trees and Multi-Way Search Trees]]
	- **Secondary Storage Optimization:** Overcoming disk I/O bottlenecks and block transfer constraints.
	- **Structural Properties of Order $m$:** Max/min bounds on keys ($m-1$) and children ($m$), half-full internal node constraints, and root exceptions.
	- **Search & Insertion Mechanics:** Multiway search, leaf-level insertions, overflow detection, and upward median promotion.
	- **Deletion & Underflow Resolution:** In-order predecessor/successor replacement, sibling borrowing (rotations), and sibling merging.
	- **Interactive Animation:** Embedded interactive visual widget for step-by-step B-Tree insertion.

5. [[Hashing and Collision Resolution Techniques]]
	- **Evolution of Searching:** Limitations of direct-address tables and the motivation for space-efficient hash tables.
	- **Hash Functions:** Division method, multiplication method (Knuth's ratio), universal hashing, and perfect hashing.
	- **Separate Chaining:** Linked list collision resolution, load factor $\alpha = n/m$, and $O(1)$ average-time proof.
	- **Open Addressing:** Linear probing (primary clustering), quadratic probing (secondary clustering), double hashing, and tombstone lazy deletion.

6. [[Advanced Graph Algorithms and Traversals]]
	- **Graph Memory Representations:** Space and time trade-offs between Adjacency Matrix ($\Theta(V^2)$) and Adjacency List ($\Theta(V+E)$).
	- **Breadth-First Search (BFS):** 3-coloring scheme, queue mechanics, shortest path property, and $O(V+E)$ time.
	- **Depth-First Search (DFS):** Discovery/finish timestamps ($d[u], f[u]$), Parenthesis Theorem, and recursion/stack traversal.
	- **Edge Classifications & DAGs:** Tree, back (cycle detection), forward, and cross edges.
	- **Topological Sort & SCC:** Linear DAG ordering via finish times, and Kosaraju-Sharir algorithm for strongly connected components.

7. [[Greedy Algorithms and Optimization Problems]]
	- **Greedy Algorithmic Paradigm:** Locally optimal choices yielding global optimums, and comparisons with Dynamic Programming.
	- **Core Elements:** The Greedy-Choice Property and Optimal Substructure.
	- **Fractional Knapsack Problem:** Value-to-weight ratio heuristic ($v_i / w_i$), greedy filling proof, and $O(n \log n)$ complexity.
	- **0-1 Knapsack Limitations:** Demonstrating why greedy fails for non-divisible items.

8. [[Data Compression Algorithms (Huffman & RLE)]]
	- **Data Compression Fundamentals:** Lossless vs. lossy compression and fixed-length vs. variable-length encoding savings.
	- **The Prefix-Free Rule:** Designing instantaneous codes mapped to leaf nodes of binary trees.
	- **Huffman Coding Algorithm:** Greedy min-heap construction, codeword derivation, and weighted tree cost calculation.
	- **Run-Length Encoding (RLE):** Algorithm mechanics, best-case compression, worst-case data expansion, and practical applications.
