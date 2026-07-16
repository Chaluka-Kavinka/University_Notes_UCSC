> Next Topic : [[Tree Data Structures and Balancing]]
---
# 1. Fundamental Concepts

- **Definition:** A graph $G=(V,E)$ consists of a set of vertices $V$ (also called nodes) and a set of edges $E$, which represent binary relations between those vertices.
- **Analogy:** A graph is like a road map where cities are the vertices and the roads connecting them are the edges.
- **Real-World Applications:** Graphs are used to model:
    - Computer and road networks.
    - Electrical circuits (e.g., resistors and inductors as vertices).
    - Hierarchical relationships.
# 2. Types of Graphs

- **Undirected Graph:** A graph where edges have no direction; the edge $\{vi​,vj​\}$ is identical to $\{ vj​,vi\}$.
- **Directed Graph (Digraph):** A graph where each edge has a specific direction, often called an **Arc**. For an edge $(u,v)$, $u$ is the "tail" and $v$ is the "head".
- **Multi-Graph:** A graph where two vertices can be connected by multiple edges.
- **Weighted Graph:** A graph where each edge has an associated numerical value (weight), often representing distance or cost.
# 3. Key Terminology

- **Adjacency and Incidence:** Nodes $i$ and $j$ are **adjacent** if there is an edge $(i,j)$ between them. The edge is said to be **incident** to those vertices.
- **Degree:**
    - **Undirected:** The number of edges incident to a vertex.
    - **Directed:** Split into **In-degree** (edges entering the vertex) and **Out-degree** (edges leaving the vertex).
- **Connectivity:**
    - **Connected Graph:** An undirected graph where a path exists between every pair of vertices.
    - **Sub-graph:** A graph $H=(U,F)$ is a sub-graph of $G=(V,E)$ if $U⊆V$ and $F⊆E$.
- **Paths and Cycles:**
    - **Path:** A sequence of edges. A **Simple Path** is one where all vertices are distinct.
    - **Length:** The sum of the lengths/weights of the edges in a path.
    - **Cycle:** A circuit where all vertices are distinct except for the first and last.
    - **Hamiltonian Cycle:** A cycle that visits every vertex in the graph exactly once.
- **Trees and Forests:**
    - **Tree:** A connected graph with no cycles. It always has $V−1$ edges.
    - **Forest:** A disjoint union of trees.
    - **Spanning Tree:** A sub-graph that is a tree and contains all vertices of the original graph. A complete graph with n nodes can have $n^n−2$ possible spanning trees.
# 4. Graph Representations

Graphs are typically stored in memory using one of two primary data structures:
## A. Adjacency Matrix

An $∣V∣\times∣V∣$ matrix A where $A[i,j]=1$ if an edge exists, and 0 otherwise.

- **Pros:** Determining if an edge $(u,v)$ exists is very fast $(O(1))$.
- **Cons:**
    - Requires $O(V2)$ memory, which is wasteful for **sparse graphs**.
    - Requires advance knowledge of the number of nodes.
    - Finding all neighbors of a node takes $O(V)$ time.
## B. Adjacency List

An array of lists where each index i stores a list of vertices adjacent to vertex $i$.

- **Pros:**
    - Memory efficient for **sparse graphs** $(O(V+E))$.
    - Fast to list all vertices adjacent to a node $(O(\text{degree}(u)))$.
- **Cons:** Determining if a specific edge $(u,v)$ exists takes $O(\text{degree}(u))$ time.
# 5. Searching and Traversal Algorithms

Searching is used to find paths or check for connectivity.

## Breadth-First Search (BFS)

- **Strategy:** Starts at an arbitrary node and visits all neighbors at distance 1, then distance 2, etc. (layer-by-layer exploration).
- **Data Structure:** Uses a **Queue**.
- **Properties:**
    - Calculates the **shortest path distance** (minimum edges) from the source.
    - Time Complexity: $O(V+E)$.
    - Space Complexity: High, as all nodes must be kept in memory.

## Depth-First Search (DFS)

- **Strategy:** Explores as deep as possible along a branch before **backtracking** to the most recent node with unexplored edges.
- **Data Structure:** Uses a **Stack** (often implemented via recursion).
- **Edge Classification in DFS:**
    - **Tree Edge:** Part of the DFS tree.
    - **Forward Edge:** Connects a node to a non-child descendant in the tree.
    - **Back Edge:** Connects a node to an ancestor; its presence indicates a **cycle** in a directed graph.
    - **Cross Edge:** Connects nodes that have no ancestor/descendant relationship.
- **Properties:**
    - Useful for determining connectivity and detecting cycles.
    - Time Complexity: $O(V+E)$.
# 6. Advanced Algorithms

- **Strongly Connected Components (SCC):** Largest disjoint sub-graphs where every pair of vertices u,v has a path to each other.
    - **Algorithm:**
        1. Call DFS on $G$ to get finishing times.
        2. Compute the **Transpose Graph** $G^T$ (reverse all edges).
        3. Call DFS on $G^T$, visiting nodes in decreasing order of their finishing times from the first DFS.
- **Topological Sort:** A linear ordering of vertices for a Directed Acyclic Graph (DAG) such that for every edge $(u,v)$, $u$ comes before $v$.
    - **Algorithm:** Perform DFS and insert each vertex into the front of a linked list as it finishes.
# 7. Special Graph Categories

- **Bipartite Graph:** A graph where vertices can be partitioned into two sets $V_1$​ and $V_2$​ such that every edge connects a vertex in $V_1$​ to one in $V_2$​. This is possible if the graph can be colored with only two colors.
- **Hypergraph:** A generalization where an edge can connect any number of vertices simultaneously.