A **Linked List** is a dynamic linear data structure consisting of a sequence of elements called **nodes**. Unlike arrays, which store data in contiguous memory, linked list nodes can be scattered throughout memory, connected by **pointers** that store the address of the next item in the chain.

# 1. The Anatomy of a Node

Each node in a linked list is essentially a container with two main parts:

- **Data Field:** Stores the actual information (like an integer or string).

- **Link/Address Field:** A pointer that holds the memory address of the **succeeding node**.

- **START Pointer:** A special variable that stores the address of the very first node so the computer knows where the list begins.

- **NULL Pointer:** The last node in the list points to `NULL` (often denoted as 'X'), signaling the end of the sequence.
>Double Link List is more complex tow-way structure where each node contains **Three Parts**
>- The data field
>- A Pointer to the Next node
>- Pointer to the **Previous**

# 2. Arrays vs. Linked Lists

| Feature        | Array                                     | Linked List                              |
| -------------- | ----------------------------------------- | ---------------------------------------- |
| **Size**       | **Fixed** (must be declared at the start) | **Dynamic** (grows/shrinks at runtime)   |
| **Memory**     | Contiguous locations                      | Random locations (Heap memory)           |
| **Efficiency** | Shifting required for insertion/deletion  | **No shifting**; just update pointers    |
| **Access**     | Random access (via index)                 | Sequential access (must start from head) |

# 3. Memory Management in C

Linked lists rely on **Dynamic Memory Allocation**, using functions from the `<stdlib.h>` library to manage memory on the **Heap**:

- **malloc()**: Reserves a specific block of memory and returns a pointer to it.

- **free()**: Crucial for releasing memory back to the system after a node is deleted to avoid **memory leaks**.

# 4. Types of Linked Lists

- **Singly Linked List:** The simplest form where nodes point only to the next node.

- **Doubly Linked List:** Each node has **two pointers** (Next and Prev), allowing you to traverse the list both forward and backward.

- **Circular Linked List:** The last node points back to the first node instead of NULL, creating a continuous loop often used in operating systems for task maintenance.

- **Header Linked List:** Contains a special **header node** at the beginning that may store metadata about the list.

# 5. Essential Operations

- **Traversing:** Moving through the list from START to NULL to process each node.

- **Searching:** Checking the data field of each node until a specific value is found.

- **Insertion:** Adding a new node at the beginning, end, or middle by simply **relinking pointers**.

- **Deletion:** Removing a node and adjusting the surrounding pointers. You must check for **Underflow** (trying to delete from an empty list) before this operation.

---

# Short Note for Memory:

- **Node = Data + Next Pointer**.

- **START** = The "Head" of the train.

- **Dynamic Allocation** = `malloc` to create, `free` to destroy.

- **Overflow** = No more memory available to add nodes.

- **Underflow** = No nodes left to delete.

---

# Analogy for Understanding:

Think of a **Linked List** like a **Scavenger Hunt**. You don't know where all the prizes are at once (like an array). Instead, you start at the first location (**START**), where you find a prize and a **clue** (pointer) telling you where the next prize is hidden. You keep following clues until you find a box that is empty (**NULL**), which tells you the hunt is over!

---
# Lecture Notes

![[DSA - Lecture 04.pdf]]

![[DSA - Lecture 05.pdf]]