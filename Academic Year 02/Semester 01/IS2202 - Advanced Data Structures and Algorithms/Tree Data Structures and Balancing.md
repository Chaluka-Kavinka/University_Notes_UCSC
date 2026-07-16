>Next Topic : [[Hashing and Searching Complexity]]
---
# 1. Fundamental Concepts

- **Definition:** A tree is a **non-linear**, abstract data type with a hierarchy-based structure used to represent data in a **parent-child relationship**.
- **Structure:** It consists of **nodes** (storing data) connected by **links**.
```C
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

typedef struct Node {
    int data;
    struct Node *left;
    struct Node *right;
    struct Node *parent;
} Node;

typedef struct {
    Node *root;
} Tree;
```
- **Examples:** Folder structures in an OS and HTML tag hierarchies.

# 2. Key Terminology

- **Root:** The single node at the very top of the tree.
- **Path:** A sequence of nodes along the edges of a tree.
- **Parent/Child:** A parent is the immediate predecessor of a node, while a child is the immediate successor.
- **Leaf:** A node that has no children.
- **Sub-tree:** A tree structure consisting of a node and all its descendants.
- **Levels:** The count of edges from the root to a specific node (Root = Level 0, Children = Level 1, etc.).
- **Height:** The number of edges on the **longest path** from a node to a leaf node. The height of the tree is the height of its root.

# 3. Types of Trees

- **General Trees:** Unordered structures where a node can have any number of sub-trees.
- **Binary Trees:** Each node has a **maximum of two children** (Left and Right).
- **Binary Search Tree (BST):** A binary tree where the **left sub-tree** contains values **less than** the root, and the **right sub-tree** contains values **greater than** the root.
- **Multi-way Search Trees:** Trees where nodes can store multiple keys and have more than two children (e.g., B-Trees).

# 4. Binary Tree Variations

- **Full Binary Tree:** Every node has either **0 or 2 children**.
- **Complete Binary Tree:** All levels are completely filled except possibly the last, and all nodes in the last level are as **far left as possible**.
- **Perfect Binary Tree:** All leaf nodes are on the same level, and every internal node has exactly 2 children.
    - _Formula:_ Total nodes $n=2^{h+1}−1$, where h is height.

# 5. Tree Balancing

Balancing ensures the height difference between sub-trees remains minimal to optimize search, insertion, and deletion operations.

## Local vs. Global Balancing

- **Local Balancing:** Focuses on small sub-trees or individual nodes, typically using **rotations** immediately after every insertion or deletion (e.g., **AVL Trees** or **Red-Black Trees**).
- **Global Balancing:** Restructures the **entire tree** structure periodically to achieve an optimal balance (e.g., **DSW Algorithm**).

# 6. Tree Rotations

Rotations are local operations that change the tree's structure without violating the BST property.

- **Right Rotation:** Moves left nodes to the right. It "promotes" a left child to the root position and "demotes" the original root to become the right child.
```C
void rightRotate(Tree *tree, Node *parent) {
    Node *child = parent->left;
    if (child == NULL) return;

    Node *oldParent = parent->parent;

    // Move child's right subtree to parent's left
    parent->left = child->right;
    if (child->right != NULL) {
        child->right->parent = parent;
    }

    // Perform rotation
    child->right = parent;
    parent->parent = child;

    // Reattach rotated subtree to the rest of the tree
    child->parent = oldParent;
    if (oldParent == NULL) {
        tree->root = child;
    } else if (oldParent->left == parent) {
        oldParent->left = child;
    } else {
        oldParent->right = child;
    }
}
```
- **Left Rotation:** Moves right nodes to the left. It promotes a right child and demotes the original root to become the left child.
```C
void leftRotate(Tree *tree, Node *parent) {
    Node *child = parent->right;
    if (child == NULL) return;

    Node *oldParent = parent->parent;

    // Move child's left subtree to parent's right
    parent->right = child->left;
    if (child->left != NULL) {
        child->left->parent = parent;
    }

    // Perform rotation
    child->left = parent;
    parent->parent = child;

    // Reattach rotated subtree
    child->parent = oldParent;
    if (oldParent == NULL) {
        tree->root = child;
    } else if (oldParent->left == parent) {
        oldParent->left = child;
    } else {
        oldParent->right = child;
    }
}
```
# 7. The Day–Stout–Warren (DSW) Algorithm

The DSW algorithm balances any BST in **linear time** $(O(n))$ using $O(1)$ **extra space**. It consists of two main phases:
## Phase 1: Create a Vine (Backbone)

The goal is to flatten the tree into a right-skewed linked list.

1. Start at the root.
2. If the current node has a **left child**, perform a **right rotation** and stay at the same position to check again.
3. If there is **no left child**, move to the **right child**.
4. Repeat until all nodes are in a single right-handed chain.
### C Implementation

```C
void createVine(Tree *tree) {
    Node *grand = NULL;
    Node *current = tree->root;

    while (current != NULL) {
        if (current->left != NULL) {
            rightRotate(tree, current);
            // After rotation, update 'current' to the new root of this subtree
            if (grand == NULL) {
                current = tree->root;
            } else {
                current = grand->right;
            }
        } else {
            // No left child, move down the right side
            grand = current;
            current = current->right;
        }
    }
}
```

## Phase 2: Balance the Vine (Compression)

The vine is converted back into a balanced tree using stages of left rotations.

1. **Count nodes** $(n)$ in the vine.
2. Calculate m (number of nodes in the closest perfectly balanced tree): $$m=2^{⌊\log_2{​(n+1)}⌋}−1$$
3. Perform $n−m$ initial left rotations on the vine to handle "excess" nodes.
4. Repeatedly **halve** $m (m=\frac{m}{2})$ and perform m left rotations until $m=0$.

### C Implementation
```C
void compress(Tree *tree, int count) {
    Node *current = tree->root;
    for (int i = 0; i < count; i++) {
        if (current == NULL) break;
        Node *child = current->right;
        leftRotate(tree, current);
        // Move to the next pair in the vine
        if (child != NULL) {
            current = child->right;
        }
    }
}

void dswBalance(Tree *tree, int n) {
    createVine(tree);

    // Calculate m: number of nodes in the closest perfectly balanced tree [6, 10]
    int m = (int)pow(2, floor(log2(n + 1))) - 1;

    // Initial compression for excess nodes (n - m) [6, 11]
    compress(tree, n - m);

    // Repeatedly halve m and perform m left rotations [6, 12]
    while (m > 1) {
        m = m / 2;
        compress(tree, m);
    }
}
```

# 5. Advanced Multi-way Trees

- **B-Tree:** A search tree where nodes store multiple keys to handle large-scale data storage efficiently.
- **B+ Tree:** An optimization of B-Trees where **actual records** are only stored in the **leaf nodes**, which are linked together for faster sequential access (commonly used in databases).