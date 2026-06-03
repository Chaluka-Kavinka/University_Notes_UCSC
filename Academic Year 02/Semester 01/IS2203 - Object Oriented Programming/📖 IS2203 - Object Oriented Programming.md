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
1. [[Introduction to Programming Paradigms]]

The module begins by contrasting **Procedural Programming** with **Object-Oriented Programming (OOP)**.

- **Procedural Programming:** Focuses on a sequence of instructions, dividing programs into functions and modules. It often suffers from "unrestricted access to global data" and is difficult to modify as complexity increases.
- **Object-Oriented Programming:** Organizes design around **objects** (real-world entities) that combine **attributes (data)** and **behaviors (methods)**. It emphasizes **modularity, reusability, and security**.

2. [[Core Principles of OOP]]

You will need to master the four pillars of OOP discussed in your lectures:

- **Inheritance:** Creating new classes that derive properties and characteristics from existing ones, reducing code redundancy.
- **Abstraction:** Providing only essential information to the outside world while hiding implementation details.
- **Encapsulation (Data Hiding):** Wrapping data and functions into a single unit (class) to prevent accidental external interference.
- **Polymorphism:** The ability of a message or function to be displayed or behave in more than one form.

3. [[C++ Language Basics and Data Types]]

The module utilizes **C++** as its primary language, covering its history as an extension of C developed by Bjarne Stroustrup. Key technical topics include:

- **Data Types:** Categorized into **Primary** (int, char, float), **Derived** (Arrays, Pointers, References), and **User-Defined** (Structures, Classes).
- **Pointers and References:** Understanding symbolic representations of memory addresses and alternative names for variables.
- **Structures (struct):** A precursor to classes used to group different data types, though in C++ they can also contain member functions.

4. [[Working with Classes and Objects]]

A significant portion of the module focuses on the transition from structures to **classes**.

- **Class Anatomy:** Defining **Data Members** (variables) and **Member Functions** (behavior) within a class.
- **Access Specifiers:** Using **public**, **private**, and **protected** keywords to control data visibility. By default, class members are private.
- **Member Access:** Using the **dot operator (.)** for objects and the **arrow operator (->)** for pointers to objects.
- **Scope Resolution Operator (::):** Used to define functions outside of a class, access global variables, or refer to namespaces.

5. [[Object Lifecycle: Constructors and Destructors]]

You will study how objects are created and destroyed:

- **Constructors:** Special functions automatically called upon object instantiation to initialize data members. These include **Default**, **Parameterized**, and **Copy Constructors**.
- **Constructor Overloading:** Defining multiple constructors with different parameter lists.
- **Initializer Lists:** An efficient way to specify initial values for data members.
- **Destructors:** Functions preceded by a tilde (~), automatically called when an object ceases to exist to release resources.

6. [[Memory Management and Advanced Scoping]]

- **Variable Scope:** Differentiating between **local variables** (inside a block) and **global variables** (accessible throughout the program).
- **Namespaces:** Defining spaces to prevent identifier name conflicts.
- **Dynamic Memory Allocation:** Using the **new** keyword to allocate memory at runtime and the **delete** keyword to free it, ensuring efficient memory use.