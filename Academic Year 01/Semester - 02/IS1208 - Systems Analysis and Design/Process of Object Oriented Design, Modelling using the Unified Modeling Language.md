>[!tip] Introduction
>The process of **Object-Oriented Design (OOD)** shifts the focus from understanding a business problem to defining the technical and **implementation concerns** of the system—essentially moving from "what" the system must do to "**how to do it**". This process results in a detailed **design specification** that serves as a blueprint for the final computer-based solution.

---
# The Four Main Design Specifications

OOD is typically organized into four distinct areas of technical specification:

- **Architecture Design:** Describes the technical infrastructure, including hardware, software, and network components.
- **Software Design:** Defines the specific programs, modules, and files that need to be constructed.
- **Database Design:** Specifies the technical models for database tables and data structures.
- **Interface Design:** Details the user interface, including the specific forms and reports to be used.

# UML: The Language of Design

The **Unified Modeling Language (UML)** provides a standard set of modeling conventions and notations to describe a system in terms of **objects**. UML diagrams are divided into two main categories:

1. **Structural Diagrams:** These emphasize the **static structure** and architecture of the software. The **Class Diagram** is the primary example, representing classes, their **attributes** (data), and their **methods** (behavior).
2. **Behavioral Diagrams:** These emphasize the **dynamic behavior** and functionality of a system by showing how objects collaborate and change state over time. Examples include **Use Case Diagrams** and **Sequence Diagrams**.

# Key UML Class Relationships

In OOD, analysts use specific notations to define how different classes interact:

- **Association:** A bidirectional connection indicating that instances of classes are linked.
- **Aggregation:** A "whole-part" relationship where the child class (the part) can **exist independently** of the parent (the whole).
- **Composition:** A stronger ownership relationship where the part **cannot exist independently** of the whole.
- **Generalization (Inheritance):** An "**is-a**" relationship where a subclass (child) inherits attributes and behaviors from a superclass (parent).

# Core Concepts Driving OOD

Effective design relies on three fundamental object-oriented pillars:

- **Encapsulation:** The packaging of data and behavior into a single unit to **hide inner workings** from other objects, protecting the system from unintended side effects when changes are made.
- **Inheritance:** The ability for a class to **reuse or inherit** attributes and methods defined in a parent class.
- **Polymorphism:** The concept where different objects can respond to the **same message** in unique ways, allowing for flexible and specialized operations.
- **Message Passing:** The process by which objects communicate by **invoking methods** in other objects to request information or actions.