This topic explores the fundamental shift in software development from following a linear sequence of steps to modeling software after real-world entities.

# 1. The Procedural Programming Paradigm

Procedural programming views a problem as a **sequence of instructions** or a list of things for the computer to do.

- **Core Logic:** Statements tell the computer to perform specific actions, such as getting input, performing calculations, and displaying output.
- **Organization:** Large programs are divided into **functions and modules** (also referred to as subroutines or procedures). Each function has a clearly defined purpose and interface.
- **Approach:** It follows a **top-down approach** to software design.
- **Examples:** C, Pascal, FORTRAN, COBOL, and BASIC.

## Limitations of Procedural Programming

As programs grow in size and complexity, procedural methods face several critical issues:

- **Unrestricted Global Data Access:** Functions have unrestricted access to global data, making it easy for one function to accidentally corrupt data needed by another.
- **Difficulty in Modification:** Because data and functions are often unrelated, a single change to a global data item may require rewriting every function that accesses it.
- **Poor Real-World Modeling:** It is difficult to represent complex real-world problems because the focus is on the "procedure" rather than the "entities" involved.
- **Maintenance Hurdles:** As complexity increases, costs skyrocket, schedules slip, and the program's structure becomes difficult to conceptualize.

# 2. The Object-Oriented Programming (OOP) Paradigm

OOP organizes software design around **objects**—real-world entities that combine data and behavior—rather than just functions and logic.

- **What is an Object?** An object represents a real-world entity (such as a student, car, or sensor).
- **Components of an Object:**
    - **Attributes (Data/Fields):** Variables inside a class that hold the state of the entity (e.g., a student's name and marks).
    - **Methods (Behaviors):** Functions inside a class that define what the object can do (e.g., calculating an average).
- **Approach:** OOP follows a **bottom-up approach**, focusing on data security and modularity.
- **Core Benefits:** Using a modular, object-oriented design makes development groups significantly more productive than earlier techniques. Key advantages include modularity, reusability, maintainability, and extensibility.

# 3. Procedural vs. Object-Oriented: Key Differences

| Feature               | Procedural Programming (PP)                 | Object-Oriented Programming (OOP)        |
| --------------------- | ------------------------------------------- | ---------------------------------------- |
| **Organization**      | Divided into functions.                     | Divided into objects.                    |
| **Focus**             | Function is more important than data.       | Data is more important than functions.   |
| **Approach**          | Top-down.                                   | Bottom-up.                               |
| **Data Security**     | Less secure; no proper way for data hiding. | Highly secure; provides data hiding.     |
| **Access Specifiers** | None.                                       | Includes public, private, and protected. |
| **Real-World Model**  | Based on "unreal" world logic.              | Based on the real world.                 |
| **Overloading**       | Not possible.                               | Possible.                                |

# 4. The Four Pillars of OOP

These core principles allow developers to handle software complexity effectively:

- **Encapsulation (Data Hiding):** The wrapping of data and functions into a single unit (a class). This protects data from accidental outside interference and ensures that implementation details are hidden within the objects themselves.
- **Abstraction:** Providing only essential information to the outside world while hiding the background implementation details. For example, a driver knows how to use a car's accelerator to increase speed without needing to know the mechanical implementation.
- **Inheritance:** The capability of a class (subclass) to derive properties and characteristics from another class (superclass). Often called an **"is-a" hierarchy**, it is the key to code reuse and reducing redundancy.
- **Polymorphism:** Meaning "many forms," it is the ability of a message or function to be displayed or behave in more than one form. This allows objects of different classes to be used interchangeably.

# 5. History and Characteristics of C++

C++ was developed as an enhancement to the C language to include the object-oriented paradigm.

- **Origins:** Developed by **Bjarne Stroustrup** in 1979 at Bell Labs.
- **Evolution:** Originally called **"C with Classes,"** it was renamed **C++** in 1984. The "++" symbolizes the C increment operator, signifying it is an advanced version of C.
- **Key Features:**
    - **Middle-Level Language:** It combines features of both high-level and low-level languages.
    - **Life-cycle Control:** It allows the explicit creation and destruction of objects while programming.
    - **Portability:** It is machine-independent but platform-dependent.
- **Major Updates:** The language has been updated significantly over time, notably with the releases of C++11, C++14, and C++17.