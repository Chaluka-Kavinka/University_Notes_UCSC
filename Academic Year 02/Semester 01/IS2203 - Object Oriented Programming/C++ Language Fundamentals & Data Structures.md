This topic covers how C++ manages data in memory, the classification of data types, and the evolution of structures into classes.

# 1. Understanding Data Types

A **data type** defines the type of data a variable can store. When a variable is declared, the compiler allocates a specific amount of memory based on its type.

- **Memory Requirements:** Different types require different amounts of space. For example, an **Integer (****int****)** typically requires **4 bytes**, while a **Character (****char****)** requires **1 byte**.
- **Classification:** C++ categorizes data types into three main groups: **Primary**, **Derived**, and **User-Defined**.

# 2. Primary (Built-in) Data Types

These are predefined by the language and can be used directly to declare variables.

- **Examples:** `int` (Integer), `char` (Character), `float` (Floating point), `double` (Double floating point), `bool` (Boolean), and `void` (representing the absence of data).

# 3. Derived Data Types

These types are formed by deriving them from primary or built-in data types.

- **Functions:** A block of code designed to perform a specific task.
- **Arrays:** A collection of items of the same type stored at **contiguous memory locations**.
- **Pointers:** A symbolic representation of memory addresses. A pointer "points" to the specific address that holds data.
    - _Syntax:_ `datatype *var_name;`.
- **References:** An **alternative name** (alias) for an existing variable, declared using the **&** symbol.

# 4. Pointers and Memory Mechanics

Pointers are a fundamental tool for managing memory directly.

- **Address-of Operator (****&****):** Used to retrieve the memory location of a variable (e.g., `ptr = &var;`).
- **Dereferencing Operator (*********):** Used to access the actual value stored at the address a pointer is holding.
- **Pointer to Pointer:** C++ allows multiple levels of indirection, such as double pointers (`int **pt`) or triple pointers (`int ***ptr`).

# 5. User-Defined Data Types: Structures (*struct*)

Structures allow you to organize simple variables into complex entities, such as grouping a student's name, age, height, and weight.

- **Aggregate Type:** Aggregates elements of different types into a single unit.
- **Syntax:** Defined using the `struct` keyword and must always end with a **semicolon (****;****)**.
- **Declaration:** In C++, the keyword `struct` is optional when defining a variable of that type (e.g., `date today;` instead of `struct date today;`).
- **Member Access:** Use the **dot operator (****.****)** to access specific data members (e.g., `today.day`).

# 6. Evolution: Structures to Classes

Classes in C++ are a natural evolution of the C notion of structures. While they are very similar, there are two critical differences:

- **Member Functions:** In standard C, structures only hold data. In C++, both **Data Members** and **Member Functions** (behaviors) can be included inside a structure.
- **Default Access (The Key Distinction):**
    - In a **Structure**, members are **PUBLIC** by default.
    - In a **Class**, members are **PRIVATE** by default.