This topic focuses on how C++ manages the visibility of identifiers and how memory is allocated during a program's execution.

# 1. Understanding Variable Scope

**Scope** refers to the specific extent of the program code within which a variable can be accessed, declared, or worked with. C++ distinguishes between two primary types of scope:

- **Local Variables:**
    - Defined within a specific function or block and declared inside that block.
    - They **do not exist outside the block** and cannot be accessed or used once the program exits that block.
- **Global Variables:**
    - Declared at the top of a program, outside of all functions or blocks.
    - They are accessible from **any part of the program** and remain available throughout its entire lifetime.
- **Scope Precedence:** Usually, two variables with the same name are not allowed in the same scope. However, if defined in different scopes, the compiler allows it. If a local variable and a global variable share a name, the compiler gives **precedence to the local variable**.

# 2. The Scope Resolution Operator (::)

The **Scope Resolution Operator** is used to tell the compiler which version of an identifier to use. Its primary applications include:

- **Accessing Global Data:** Used to access a global variable when a local variable with the same name is currently in scope.
- **Defining Functions Outside Classes:** Allows you to declare a function signature inside a class but provide the implementation elsewhere to keep class definitions clean.
- **Namespace Navigation:** Used to call specific identifiers (variables, functions, classes) located within a namespace.
- **Nested Class Access:** Used to refer to a class that has been defined entirely inside another class.
- **Static Member Access:** Used to access a class’s **static variables** or member functions.
- **Inheritance Ambiguity:** Used to specify which ancestor class's variable to access in complex multiple inheritance scenarios.

**3. Namespaces**

A **namespace** is a designated space used to define or declare identifiers like variables, methods, and classes.

- **Purpose:** They allow programmers to use functions and classes with the same name across different libraries without causing conflicts.
- **Syntax:** Identifiers are called using the syntax `namespace_name::code;`.
- **Directive:** Using `using namespace std;` allows you to access standard library identifiers (like `cout`) without the `std::` prefix.

# 4. Memory Allocation: Static vs. Dynamic

C++ handles memory in two distinct ways depending on when the allocation occurs:

- **Static Memory Allocation:**
    - Used for global and local variables.
    - Memory space is **allocated by the compiler before the program executes**.
- **Dynamic Memory Allocation:**
    - Allows for memory to be explicitly allocated and deallocated at **run-time**.
    - **Advantages:** You do not need to know the required memory amount beforehand; you can allocate exactly what is needed, leading to more efficient memory space usage.

**Keywords for Dynamic Memory**

- **new** **Keyword:** Allocates storage for an object or an array and returns a **pointer** to that address.
- **delete** **Keyword:** Deallocates (frees) the storage once it is no longer required. For arrays, the syntax `delete []` must be used.

**Best Practices and Safety**

- **Memory Leaks:** Always free dynamic memory when it is no longer required to prevent performance issues.
- **Success Verification:** `new` returns a **null pointer (0)** if allocation fails. It is best practice to use the `assert` macro to check that allocation was successful before proceeding with the code.