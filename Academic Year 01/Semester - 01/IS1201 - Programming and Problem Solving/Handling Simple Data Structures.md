> [!Info]
> **Topic 06: Handling Simple Data Structures** is a critical four-week module designed to teach you how to manage and organize data efficiently in C. This topic covers pointers, arrays and strings, structures, unions, and enumerations.

---

# 1. Pointers and Memory Management

A pointer is a variable that stores the memory address of another variable.

- **Core Concepts:**
    - **Operators:** The **address-of operator (****&****)** retrieves a variable's memory address, while the **indirection operator (*********)** is used to access the value stored at that address.
    - **NULL Pointers:** A pointer assigned **NULL** or `0` does not point to any memory location. This is distinct from an uninitialized pointer, which can contain any random value.
    - **Pointer to Void:** A `void *` is a general-purpose pointer that can hold references to any data type. It can be cast back to its original pointer type without losing data.
    - **Size:** The size of a pointer (e.g., 8 bytes on many systems) depends on the machine architecture rather than the data type it points to.
- **Dynamic Memory Allocation:** C allows you to request memory from the "heap" during runtime using the `<stdlib.h>` library.
    - **malloc(size)**: Allocates a block of memory of a specified size.
    - **calloc(n, size)**: Allocates memory for multiple elements and initializes them to zero.
    - **free(ptr)**: Returns allocated memory back to the heap to avoid **memory leaks**.
    - **Dangling Pointers:** These occur when a pointer still references a memory location after the memory has been freed, which can cause undefined behavior.
- **Function Pointers:** You can declare pointers that point to functions, allowing you to pass functions as arguments to other functions.

# 2. Arrays and Strings

- **Arrays:** Used to store a set of elements of the **same data type** in contiguous memory locations.
- **Strings:** Handled as arrays of characters. This topic also introduces **Tokenizing** using functions like **strtok()**, which splits a string into smaller parts (tokens) based on delimiters like spaces.

# 3. Structures (`struct`)

A structure is a user-defined data type that allows you to group related variables of **different types** under a single name.

- **Declaration:** Members of a structure are defined within curly braces. You can define a structure with a **tag** (e.g., `struct student`) to make it reusable.
- **Accessing Members:** You use the **dot (****.****) operator** to access or assign values to specific members (e.g., `st1.age = 21;`).
- **Advanced Structures:**
    - **Self-referential structures:** A structure that contains a pointer to its own type, often used in complex data structures like linked lists.
    - **Arrays of Structures:** You can define an array where every element is a structure, which is useful for managing databases of records, such as student IDs and GPAs.
- **Limitations:** You **cannot** use basic mathematical operators (`+`, `-`, `*`, `/`) or comparison operators (`==`, `<`) directly on structure variables; you must compare their individual members instead.

# 4. Unions

A union is similar to a structure, but all its members **share the same storage space**.

- **Memory Efficiency:** The size of a union is determined by its **largest member**. Because members share memory, only one member can be used at a time.
- **Practical Application:** Unions are ideal when you have an item that could be one of several different things but never more than one at once (e.g., a shop item that is either a "Book" or a "Cake"), thus preventing memory waste.

# 5. Enumerations (`enum`)

While specific details on `enum` syntax are limited in the excerpts, the syllabus lists them as a key component of Topic 06 for defining sets of named integer constants.

---
# Lecture Notes
![[IS1201 - IS1201 - Programming and Problem Solving _ Arrays and Strings.pdf]]
![[IS1201 - IS1201 - Programming and Problem Solving _ Understanding and Using Pointers in C.pdf]]
![[IS1201 - Structures.pdf]]
![[IS1201 - Unions.pdf]]