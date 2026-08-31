# 1 Understanding Software Architecture

**Software Architecture** is defined as the fundamental organization of a system, consisting of its components, their relationships to one another and the environment, and the principles guiding its design and evolution. **Every system has an architecture**, whether it is formally documented or not.

The primary reasons for explicitly designing an architecture include:

- **Managing Complexity:** Providing a high-level view to help understand how the system works.
- **Development Organization:** Allowing for the partitioning of development tasks among teams.
- **Facilitating Reuse:** Creating structures that can be applied to similar systems in the future.
- **Enabling Evolution:** Managing changes and dependencies throughout the product's life.

# 2 Advantages and Principles

Explicitly designing and documenting software architecture offers three main advantages:

1. **Stakeholder Communication:** It provides a high-level presentation that serves as a focus for discussion among stakeholders.
2. **System Analysis:** It allows architects to analyze whether a system can realistically meet its non-functional requirements (NFRs).
3. **Large-Scale Reuse:** Architectures are often similar for systems with similar requirements, allowing for significant reuse.

## Basic Architectural Principles:

- **Abstraction and Encapsulation:** Separating _what_ a component does from _how_ it does it and hiding internal structures.
- **Separation of Concerns:** Distinguishing between different layers like interfaces vs. implementation or data vs. business logic.
- **Modularity:** Organizing the system into discrete modules, focusing on high **cohesion** (related tasks stay together) and low **coupling** (minimizing dependencies between modules).

# 3 Architectural Design Decisions

Architectural design is a creative process where decisions depend on the system type, the architect's experience, and the specific requirements. These decisions directly influence the system's ability to meet **Non-Functional Requirements (NFRs)**:

- **Performance:** To increase response times, critical operations should be localized to minimize communication, and architects should use large-grain rather than fine-grain components.
- **Security:** A **layered architecture** should be used, placing critical assets in the innermost layers.
- **Safety:** Safety-critical features should be localized within a small number of sub-systems to simplify verification.
- **Availability:** Redundant components and fault-tolerance mechanisms must be included.

# 4 The 4+1 View Model

Because no single model can show every perspective, the **4+1 View Model** is used to describe architecture from the viewpoint of different stakeholders:

1. **Logical View:** Focuses on functional requirements—what the system provides to the **end-user**.
2. **Process View:** Used by **integrators** to see how the system is composed of interacting processes at run-time (deals with concurrency and scalability).
3. **Development View:** Shows how the software is decomposed into building blocks for **programmers and managers** to organize development and reuse.
4. **Physical View:** Used by **system engineers** to see how software components are distributed across system hardware and processors.
5. **Scenarios (+1):** Uses use cases to validate that the design is complete and consistent across all other views.

# 5 Common Architectural Patterns

An architectural pattern is a **reusable solution** to a commonly occurring problem within a given context.

- **Model-View-Controller (MVC):** Separates system data (**Model**) from its presentation (**View**) and user interaction (**Controller**). This allows data to change independently of its representation.
- **Layered Architecture:** Organizes functionality into layers, where each layer provides services to the one above it. This supports incremental development and makes the system easier to maintain.
- **Repository Architecture:** Describes how components share data through a **central database**. This is ideal for systems managing large volumes of shared information.
- **Client-Server Architecture:** A distributed model where stand-alone **servers** provide specific services (like data management) to a set of **clients**.
- **Pipe and Filter Architecture:** Organizes processing into discrete components (**filters**) that perform one transformation. Data flows through "pipes" from one component to the next