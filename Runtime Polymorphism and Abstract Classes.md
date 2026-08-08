This final topic explores **Late Binding**, a powerful feature of C++ that allows programs to decide which function to execute at runtime rather than at compile time.

# 1. Understanding Runtime Polymorphism

Polymorphism, meaning "many forms," allows a single message to be displayed in more than one form. While **Compile-Time Polymorphism** is achieved through function and operator overloading, **Runtime Polymorphism** is achieved through **Function Overriding** and **Virtual Functions**.

- **Definition:** It is the ability of C++ to ensure the correct function is called for an object, regardless of the type of the reference (pointer or alias) used to call it.
- **Late Binding:** Unlike overloading, where the compiler picks the function during compilation, runtime polymorphism involves "dynamic binding," where the decision is made while the program is running.


# 2. Function Overriding

Function overriding occurs when a derived class provides a new definition for a member function that already exists in its base class.

- **Requirement:** The overriding function must have the **exact same signature** (name and parameter list) as the function in the base class.
- **The** **override** **Keyword (C++11):** To prevent accidental mistakes (such as typos or signature mismatches), programmers can use the `override` keyword. This forces the compiler to check if a matching virtual function actually exists in the base class; if not, it triggers a compilation error.


# 3. Virtual Functions: The Key to Flexibility

A **virtual function** is a member function declared in a base class using the **virtual** keyword, which you intend to redefine in derived classes.

- **Mechanism (vtable and vptr):**
    - For every class containing virtual functions, the compiler creates a **vtable (virtual table)**.
    - This table stores the addresses of the virtual functions for that specific class.
    - Each object of such a class contains a hidden **vptr (virtual pointer)** that points to its class's vtable.
    - When a virtual function is called via a pointer, the program looks up the address in the vtable to ensure the "actual" object's version is executed.
- **Costs:** Using virtual functions requires a small amount of extra memory for the vtable and incurs a minor performance penalty during the lookup process.


# 4. Pure Virtual Functions and Abstract Classes

Sometimes, a base class is so general that it cannot provide a meaningful implementation for a function (e.g., a `Shape` class cannot calculate an area because it doesn't know its geometry).

- **Pure Virtual Functions:** These are functions declared in the base class without any implementation. They are defined by assigning **0** to the declaration (e.g., `virtual void draw() = 0;`).
- **Abstract Classes:**
    - A class is considered **Abstract** if it contains at least one pure virtual function.
    - **Instantiation Rule:** Abstract classes **cannot be instantiated** (you cannot create objects of that class).
    - **Mandatory Implementation:** If a derived class does not override the pure virtual function, it also becomes an abstract class and cannot be instantiated.


# 5. Method Hiding: A Cautionary Note

In C++, if a derived class redefines a base class member method, **all** methods in the base class with that same name become **hidden** in the derived class.

- **The Trap:** Even if the derived class version has a different signature, the base class's overloaded versions are still hidden and cannot be accessed through the derived object without explicit scope resolution.