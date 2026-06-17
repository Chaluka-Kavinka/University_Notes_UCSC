- **Course Code** : IS 2203
- **Course Name** : Object Oriented Programming
- **Lecture** : Dr. Lasanthi De Silva

#Lesson-Plan 


> [!NOTE] Goal
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
	This introductory section explores why software development shifted from procedural steps to object-oriented design.
	- **Procedural vs. OOP:** Understanding the move from a "sequence of instructions" to "real-world entities" (objects) that combine attributes and behaviors.
	- **The Four Pillars:** Mastery of **Inheritance, Abstraction, Encapsulation, and Polymorphism**.
	- **C++ Origins:** The history of C++ as an extension of C by Bjarne Stroustrup, incorporating advanced features like classes and the increment operator (++) in its naming.

2. [[C++ Language Fundamentals & Data Types]]
	Before diving into complex objects, the module covers how data is structured in memory.
	- **Data Type Categories:** Distinguishing between **Primary** (int, char, bool), **Derived** (Functions, Arrays, Pointers, References), and **User-Defined** (Classes, Structures) types.
	- **Pointers and References:** Understanding memory addresses through pointer syntax (`*`) and alternative naming via references (`&`).
	- **Evolution of Structures:** How C++ "structs" evolved into classes, including the ability to hold both data and member functions.

3. [[Building Classes and Objects]]
	This topic focuses on the syntax and mechanics of creating the "blueprints" for your software.
	- **Class Anatomy:** Defining **Data Members** (attributes) and **Member Functions** (behaviors).
	- **Access Specifiers:** Implementing security through **public** (accessible outside), **private** (internal only), and **protected** keywords.
	- **Member Access:** Using the **dot operator (.)** for direct access and the **arrow operator (->)** when referring to a class via a pointer.

4. [[The Object Life-cycle (Constructors & Destructors)]]
	One of the most critical topics, focusing on how objects are "born," managed, and "destroyed" to prevent memory leaks.
	- **Constructors:** Special functions (Default, Parameterized, and Copy) that ensure an object starts in a "valid, predictable state".
	- **Advanced Initialization:** Using **Initializer Lists** for efficiency and **Constructor Overloading** to provide multiple ways to create an object.
	- **The Copy Constructor:** Learning the difference between a compiler-generated **bit-wise copy** and a user-defined copy needed for objects with pointers.
	- **Destructors:** The tilde (`~`) syntax used to release resources when an object ceases to exist.
5. [[Memory Management and Advanced Scoping]]
	Mastering how the computer allocates resources during a program's execution.
	- **Scope & Namespaces:** Using the **Scope Resolution Operator (::)** to define functions outside classes and manage global vs. local variable conflicts.
	- **Dynamic Memory:** Utilizing **new** and **delete** keywords to allocate storage at run-time rather than compile-time.
	- **Nested & Member Objects:** Creating complex classes that contain other classes as members (e.g., a "Cylinder" class containing a "Circle" object).

6. [[Specialized Class Members and Keywords]]
	Refining class behavior using advanced C++ keywords.
	- **Static Members:** Variables and functions that are shared by the entire class rather than owned by a specific object.
	- **The** **const** **Keyword:** Protecting data by creating constant variables, constant pointers, and **constant member functions** that cannot modify an object’s data.
	- **The** **this** **Pointer:** Understanding the implicit "hidden" pointer that points to the object currently invoking a method.

7. [[Polymorphism (Overloading Functions & Operators)]]
	The final section covers how to give multiple meanings to functions and symbols.
	- **Function Overloading:** Defining multiple functions with the same name but different parameter lists, allowing the compiler to choose the "best match".
	- **Operator Overloading:** Using the **operator** keyword to redefine how standard symbols (like `+`, `-`, or `++`) interact with your custom class objects.
	- **Unary vs. Binary Overloading:** Learning to overload operators that act on a single operand (like prefix/postfix `++`) versus those acting on two (like `+`).