- **Course Code** : IS 2203
- **Course Name** : Object Oriented Programming
- **Lecture** : Dr. Lasanthi De Silva

#Lesson-Plan 

> [!important] Goal
> The primary goal of this module is to transition your programming approach from a procedural mindset to an **Object-Oriented Programming (OOP) paradigm**, which organizes software design around real-world objects rather than just functions and logic.

---
# The specific objectives of the module include:

- **Understanding Software Complexity:** Learning how to handle larger, more complex programs where traditional procedural methods often lead to skyrocketing costs and difficult maintenance.
- **Mastering the Four Pillars of OOP:** Developing a deep understanding of core principles used to model real-world problems:
	- **Inheritance:** Reusing code by deriving new classes from existing ones.
    - **Abstraction:** Providing only essential information while hiding background implementation.
    - **Encapsulation (Data Hiding):** Wrapping data and functions into a single unit to ensure security and prevent outside interference.
    - **Polymorphism:** Allowing a single message or function to be displayed in multiple forms.
- **Improving Software Development Processes:** Learning how modular, object-oriented design can make development groups significantly more **productive** while making code more **reusable, maintainable, and extensible**.
- **Practical Implementation in C++:** Utilizing C++ to implement these concepts through the use of **classes and objects**. This includes mastering C++ specific features like access specifiers (public, private, protected), namespaces, and the scope resolution operator.
- **Managing the Object Lifecycle:** Learning how to ensure objects are in a "valid, predictable state" from instantiation to destruction through the proper use of **constructors and destructors**.
- **Efficient Memory Management:** Understanding how to use **dynamic memory allocation** (the `new` and `delete` keywords) to manage resources efficiently at runtime.

Overall, the module aims to provide you with a robust framework for designing software that is more secure, organized into logical units, and capable of representing complex real-world entities like students, cars, or accounts.

---
# Topic Covered

1. [[Foundations of the OOP Paradigm]]
	- **Procedural vs. Object-Oriented:** Understanding the shift from a "sequence of instructions" to organizing design around real-world objects.
	- **Limitations of Procedural Programming:** Unrestricted access to global data and poor modeling of complex real-world problems.
	- **The Four Pillars of OOP:** Definitions and benefits of **Inheritance, Abstraction, Encapsulation (Data Hiding), and Polymorphism**.
	- **C++ History:** Origins as "C with Classes" and the significance of the "++" operator.

2. [[C++ Language Fundamentals & Data Structures]]
	- **Data Type Categories:** Distinguishing between **Primary** (int, char), **Derived** (Arrays, Pointers, References), and **User-Defined** (Classes, Structures).
	- **Pointers and Memory:** Managing addresses using the address-of (`&`) and dereferencing (`*`) operators.
	- **Structures (struct):** Evolution of structures in C++ to include member functions and the distinction between `struct` (default public) and `class` (default private).

3. [[Anatomy of Classes and Objects]]
	*   **Class Mechanics:** Defining **Data Members** (attributes) and **Member Functions** (behaviors).
	*   **Access Specifiers:** Implementing security via **public, private, and protected** keywords.
	*   **Member Access:** Using the **dot operator (.)** for objects and the **arrow operator (->)** for object pointers.
	*   **Defining Functions:** Comparing **inline** functions (inside the class) versus functions defined **outside** using the Scope Resolution Operator.
	
4. [[Scope, Namespaces, and Dynamic Memory]]
	*   **Variable Scope:** Differentiating between **local** and **global** variables and managing precedence.
	*   **Namespaces:** Using identifiers to prevent naming conflicts in libraries.
	*   **The Scope Resolution Operator (::):** Its many uses, from accessing global variables to defining functions outside classes.
	*   **Dynamic Memory Allocation:** Explicitly allocating/deallocating memory at runtime using **`new`** and **`delete`**.

5. [[The Object Life-cycle (Constructors & Destructors)]]
	*   **Constructors:** Special functions for initialization, including **Default, Parameterized, and Copy Constructors**.
	*   **Initialization Lists:** An efficient syntax for specifying initial values for data members.
	*   **Destructors:** The tilde (`~`) syntax and their role in deallocating resources.
	*   **Order of Execution:** The sequence of calls for global, local, and nested objects.

6. [[Specialized Class Members and Keywords]]
	*   **Static Members:** Data and functions shared by the entire class rather than a specific object.
	*   **The `const` Keyword:** Protecting data via constant variables, constant pointers, and **constant member functions**.
	*   **The `this` Pointer:** An implicit pointer pointing to the object currently invoking a method.

7. [[Function and Operator Overloading]]
	*   **Function Overloading:** Multiple functions with the same name but different signatures (parameters).
	*   **Operator Overloading:** Redefining how symbols like `+`, `-`, or `++` interact with classes.
	*   **Unary vs. Binary Overloading:** Handling operators that act on one operand (like prefix/postfix `--`) versus two.
	*   **Non-Overloadable Operators:** Understanding why `.`, `::`, `?:`, and `sizeof` cannot be redefined.

8. [[Friend Functions and Data Conversion]]
	*   **Friend Functions:** External functions granted access to a class's private and protected members.
	*   **Type Conversion:** Handling assignments between basic types and classes, as well as between different class types.

9. [[Inheritance Fundamentals and Types]]
	*   **Terminology:** Concepts of **Super/Base** classes versus **Sub/Derived** classes.
	*   **Inheritance Modes:** How **public, protected, and private inheritance** affect member visibility in derived classes.
	*   **The Five Types of Inheritance:** Single, Multiple, Multilevel, Hierarchical, and Hybrid.

10. [[The Diamond Problem and Virtual Inheritance]]
	*   **The Ambiguity Issue:** When a class inherits two copies of a grandparent class.
	*   **The Solution:** Implementing **Virtual Base Classes** and using the `virtual` keyword to ensure only one copy exists.

11. [[Runtime Polymorphism and Abstract Classes]]
	*   **Function Overriding:** Redefining base class functions in derived classes.
	*   **The `override` Keyword:** A C++11 feature to prevent mistakes during overriding.
	*   **Virtual Functions:** Achieving **late binding** (runtime decision-making).
	*   **Pure Virtual Functions and Abstract Classes:** Creating "blueprint" classes that cannot be instantiated.
	*   **Method Hiding:** Understanding how derived methods can accidentally hide base class functions.