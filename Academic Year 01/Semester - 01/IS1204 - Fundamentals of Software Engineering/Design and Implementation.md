# 1 Introduction to Design and Implementation

In modern software engineering, **software design and implementation activities are invariably interleaved**, meaning they often happen simultaneously rather than as strictly separate phases.

- **Software Design:** A creative activity where you identify software components and their relationships based on customer requirements. It is essentially deciding **how to solve the problem**.
- **Implementation:** The process of **realizing the design as an executable program**.

# 2 Object-Oriented Design (OOD)

OOD promotes a component-based approach where a system is built as a set of interacting objects. Objects are **stand-alone entities**, meaning changing one object should not affect others in the system.

## Key OO Concepts:

- **Abstraction:** Hiding unwanted details while showing essential information. It focuses on **what an object does** rather than how it works.
- **Inheritance:** Allows methods or attributes from one class to be reused by another (Generalization/Specialization).
- **Polymorphism:** Allows different forms of the same service to be defined, such as an "open" operation performing differently for a door versus a bank account.
- **Encapsulation (Information Hiding):** Packaging attributes and behaviors together so that an object's internal workings are hidden from the outside world.

## OOD Process Stages:

1. **Define Context and Interactions:** Understand the relationships between the software and its external environment.
2. **Design System Architecture:** Organize components using patterns like layered or client-server models.
3. **Identify Principal Objects:** An iterative process that relies on designer experience to define object classes.
4. **Develop Design Models:** Creating **Structural models** (static structure/classes) and **Dynamic models** (interactions/state changes).
5. **Specify Object Interfaces:** Defining how objects communicate so that components can be designed in parallel.

# 3 Design Patterns

A design pattern is a **reusable, abstract solution to a commonly occurring problem** in software design. It is not a finished piece of code but a **template** for how to solve a problem.

## Main Elements of a Pattern Description:

- **Name:** A meaningful identifier.
- **Problem Description:** Explains when and why the pattern is used.
- **Solution Description:** A template for a design solution that can be instantiated in different ways.
- **Consequences:** The results and trade-offs of applying the pattern.

## Types of Patterns:

- **Creational:** Focus on the object instantiation process.
- **Structural:** Concern how classes and objects are composed into larger structures.
- **Behavioral:** Concern algorithms and communication between objects (e.g., the **Observer Pattern**, which notifies multiple displays when an object's state changes).

# 4 Implementation Issues

Software engineering also addresses practical implementation challenges beyond simple programming:

- **Software Reuse:** Most modern software is built by reusing existing components, libraries, or complete systems to reduce costs and schedule pressure.
- **Configuration Management (CM):** The process of managing changes to an evolving system. It involves keeping track of different **versions**, managing **system releases**, and tracking **bugs** so multiple developers can work together controlledly.
- **Host-Target Development:** Software is usually developed on one computer (**Host**) but executed on a separate platform (**Target**).

# 5 Open Source Development

Open-source development is an approach where the **source code is published and volunteers are invited to participate** in the development.

- **Business Model:** Companies often provide the software for free and make money by selling **support services**.
- **Licensing:** Even though code is free, developers still own it and can apply restrictions through licenses:
    - **GPL (GNU General Public License):** Reciprocal; if you use it, your new software must also be open source.
    - **LGPL (Lesser GPL):** Allows linking to open-source code without forced disclosure of your own source code.
    - **BSD (Berkeley Standard Distribution):** Non-reciprocal; you can use the code in proprietary, closed-source systems.