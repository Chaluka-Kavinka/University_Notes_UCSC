>Next Topic : [[Building Classes and Objects]]

# 1. Understanding Data Types

In C++, a **data type** defines the type of data a variable can store, which determines how much memory the compiler allocates for it. Every data type has specific memory requirements:

- **Integer (****int****):** Typically requires **4 bytes** and stores whole numbers.
- **Character (****char****):** Requires **1 byte** and stores single characters or small integers.
- **Classification:** C++ categorizes data types into three main groups: **Primary**, **Derived**, and **User-Defined**.
# 2. Primary (Built-in) Data Types

These are predefined types that you can use directly to declare variables.

- **Examples:** `int`, `char`, `float` (for decimals), `bool` (for true/false), and `void` (representing the absence of data).

# 3. Derived Data Types

These types are built from primary data types to provide more complex functionality.

- **Arrays:** A collection of items of the same type stored at **contiguous memory locations**.
- **Pointers:** A symbolic representation of memory addresses. A pointer "points" to the address where data is held. **Syntax:** `datatype *var_name;`.
- **References:** An **alternative name** for an existing variable. It is declared using the **&** symbol.

# 4. User-Defined Data Types

These are types defined by the programmer to model specific entities.

- **Structures (****struct****):** Used to group different data types into a single unit. In C++, structures can also contain **member functions**.
- **Classes:** A natural evolution of the structure and the blueprint for objects.
    - **Key Difference:** By default, members of a **structure are public**, while members of a **class are private**.

# 5. Pointers and Memory Addresses

Understanding pointers is crucial for efficient memory management in C++.

- **Address-of Operator (****&****):** Used to get the memory address of a variable.
- **Dereferencing Operator (*********):** Used to access the value stored at the address a pointer is holding.
- **Member Access via Pointers:** While the **dot operator (****.****)** is used for objects, the **arrow operator (****->****)** is used to access members through a pointer to an object.

# 6. Variable Scope and Namespaces

- **Local Variables:** Defined within a function/block and cannot be accessed outside of it.
- **Global Variables:** Declared outside all functions and accessible from any part of the program.
- **Scope Resolution Operator (****::****):**
    - Used to access a **global variable** when a local variable has the same name.
    - Used to define **member functions** outside their class definition.
- **Namespaces:** A space used to define identifiers (variables, classes) to prevent name conflicts across different libraries.

# 7. Dynamic Memory Allocation

Unlike static allocation (where memory is fixed at compile-time), dynamic allocation happens at **run-time**.

- **new** **keyword:** Allocates memory storage and returns a pointer to it.
- **delete** **keyword:** Deallocates (frees) the memory when it is no longer required to prevent memory leaks.