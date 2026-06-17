>Next Topic : [[C++ Language Fundamentals & Data Types]]

# 1. The Procedural Programming Paradigm

Before OOP, programming was primarily **procedural**. This approach views a problem as a **sequence of instructions** or a list of things for the computer to do.

- **Core Concept:** Statements tell the computer to get input, perform calculations (like addition or division), and display output.
- **Organization:** Large programs are divided into **functions and modules** (also called subroutines or procedures), each with a specific purpose.
- **Examples:** C, Pascal, FORTRAN, COBOL, and BASIC.
## Limitations of Procedural Programming

As programs become larger and more complex, procedural methods face significant challenges:

- **Unrestricted Global Data Access:** Functions have unrestricted access to global data, making it easy for one function to accidentally change data needed by another.
- **Difficulty in Modification:** A change in a global data item may require rewriting every function that accesses it.
- **Poor Real-World Modeling:** It is difficult to represent complex real-world problems because the focus is on the "procedure" rather than the "entities" involved.
# 2. The Object-Oriented Programming (OOP) Paradigm

OOP was developed to handle increasing software complexity by organizing design around **objects** rather than functions and logic.

- **What is an Object?** An object represents a **real-world entity** (e.g., a student, car, or bank account).
- **Components of an Object:**
    - **Attributes (Data):** The characteristics or state of the entity (e.g., a student's name and marks).
    - **Methods (Behaviors):** The functions that define what the object can do (e.g., calculating an average mark).
- **Approach:** OOP follows a **bottom-up approach**, focusing on data security and how objects communicate with each other.
# 3. The Four Pillars of OOP

These core principles allow developers to model the real world effectively:

- **Encapsulation (Data Hiding):** Wrapping data and functions into a single unit (a class). This conceals implementation details and protects data from outside interference.
- **Abstraction:** Providing only essential information to the outside world while hiding the background implementation (e.g., knowing how to use a car's brakes without knowing the mechanical details).
- **Inheritance:** The process by which one class (derived class) acquires the properties and characteristics of another (base class), promoting **code re-usability**.
- **Polymorphism:** The ability of a message or function to be displayed or behave in more than one form.
# 4. History and Characteristics of C++

C++ is a general-purpose language that enhanced C to include the object-oriented paradigm.

- **Origins:** Developed by **Bjarne Stroustrup** in 1979 at Bell Labs.
- **Evolution:** Originally called **"C with Classes,"** it was renamed to **C++** in 1983. The "++" comes from the C increment operator, symbolizing it is an advanced version of C.
- **Key Features:**
    - **Middle-Level:** It combines features of both high-level and low-level languages.
    - **Compiler-Based:** It translates code into executable files.
    - **Dynamic Memory Allocation:** It allows users to allocate memory for variables at runtime using the `new` and `delete` keywords.