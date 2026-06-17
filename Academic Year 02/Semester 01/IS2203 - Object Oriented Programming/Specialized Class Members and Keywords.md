>Next Topic : [[Polymorphism (Overloading Functions & Operators)]]

# 1. Static Members

In C++, the **static** keyword allows you to define members that belong to the **class itself** rather than any specific object.

- **Static Data Members:**
    - **Shared Identity:** These variables are shared by all objects of the class; there is only one copy regardless of how many objects are created.
    - **Lifetime:** They are allocated memory for the entire lifetime of the program.
    - **Initialization:** They cannot be initialized inside a constructor because they don't depend on a specific object. Instead, they must be initialized **explicitly outside the class** using the scope resolution operator: `Type ClassName::variable_name = value;`.
- **Static Member Functions:**
    - **Class-Level Access:** These functions work for the class as a whole and do not depend on a particular object.
    - **Invocation:** They can be called using an object or, more commonly, using the class name: `ClassName::staticMemberName()`.
    - **Restrictions:** They can **only access static data members** or other static member functions. They **do not have a** **this** **pointer** and cannot be declared as `const`.
# 2. The [const] Keyword

The **const** keyword is used to create "read-only" entities, ensuring their values remain unchanged during their lifetime.

- **Constant Variables:** Must be initialized at the time of declaration. Any attempt to modify them later (e.g., `i++`) results in a compilation error.
- **Constant Pointers:**
    - **Pointer to a Constant (****const int* ptr****):** The value being pointed to cannot change, but the pointer can be moved to point to a different address.
    - **Constant Pointer (****int* const ptr****):** The pointer's address cannot change, but the value at that address can be modified.
    - **Constant Pointer to a Constant (****const int* const ptr****):** Neither the pointer nor the value it points to can be changed.
- **Constant Member Functions:**
    - **Data Protection:** These functions are guaranteed **never to modify data members** of an object.
    - **Syntax:** The `const` keyword must be added to both the function signature and its implementation: `void getVal() const;`.
- **Constant Objects:** Declared as `const ClassName object;`. These objects can **only call constant member functions** to ensure their state remains immutable.

# 3. The [this] Pointer

Every non-static member function in C++ has access to a "hidden" implicit pointer called **this**.

- **Purpose:** It points to the **specific object that is currently invoking the method**.
- **Mechanics:** It is passed as a hidden argument to all non-static member function calls and is available as a local variable within the function body.
- **Usage:** It is often used to distinguish between local parameters and class data members if they share the same name (e.g., `this->width = width;`).
- **Static Limitation:** Because static member functions are not associated with a particular object, they **do not have a** **this** **pointer**.