>Next Topic : [[Specialized Class Members and Keywords]]

# 1. Understanding Variable Scope

**Scope** refers to the specific extent of program code within which a variable can be accessed, declared, or worked with. C++ handles two primary types of scope:

- **Local Variables:** These are defined within a specific function or block. They only exist while that block is executing and cannot be accessed or used outside of it.
- **Global Variables:** These are declared at the top of a program, outside of all functions or blocks. They are accessible from any part of the program and remain available throughout the program's entire lifetime.
- **Precedence:** If a local variable and a global variable share the same name, the compiler gives **precedence to the local variable**.
# 2. The Scope Resolution Operator (::)

The **Scope Resolution Operator** is a powerful tool used to tell the compiler exactly which "version" of a name you want to use. Its main uses include:

- **Accessing Global Data:** Used to access a global variable when a local variable with the same name is currently in scope.
- **Defining Functions Outside Classes:** Allows you to keep your class definitions clean by declaring the function signature inside the class and providing the implementation elsewhere.
- **Accessing Static Members:** Used to access a class's static variables or functions without needing a specific object.
- **Namespace Navigation:** Used to refer to a class or function inside a specific namespace.
- **Nested Class Access:** Used to refer to a class that has been defined inside another class.
# 3. Namespaces

A **namespace** is a designated space where you can define or declare identifiers like variables, methods, and classes. This prevents naming conflicts when using multiple libraries that might use the same names for different things.

- **Syntax:** You call a specific member of a namespace using `namespace_name::member_name`.
- **Convenience:** The `using namespace std;` directive allows you to use standard library features (like `cout`) without needing to prefix them with `std::` every time.
# 4. Dynamic Memory Allocation

Unlike **Static Memory Allocation**, where the compiler decides memory space before the program runs, **Dynamic Memory Allocation** happens at **run-time**.

- **Advantages:** You do not need to know how much memory is required beforehand; you can allocate exactly what is needed for better efficiency.
- **The** **new** **Keyword:** Used to allocate storage for an object or an array at runtime, returning a pointer to that address.
- **The** **delete** **Keyword:** Used to release (deallocate) storage once it is no longer required. Failing to use `delete` can lead to **memory leaks**.
- **Safety:** `new` returns a **null pointer (0)** if memory allocation fails. It is best practice to use `assert` to check if allocation was successful before proceeding.
# 5. Nested and Member Objects

Complex software often requires classes to be built from other classes:

- **Nested Classes:** You can declare a class entirely within the body of another class.
- **Member Objects (Composition):** A class can have a data member that is itself an object of another class.
- **Initialization Order:** When an object contains a member object, the member object's constructor is called first to ensure the internal components are ready before the main object's constructor finishes. For example, a `Cylinder` object would first trigger the constructor for its `Circle` "base" before completing its own initialization.