>[!important] Introduction
>**Use-case modeling** is a user-centered process used to model a system’s functions in terms of **business events**, the actors who initiate them, and how the system responds to those events. Originally conceived by Dr. Ivar Jacobson in 1986, it has become a best practice for defining and documenting the **functional requirements** of an information system.

---
# Key Components of Use-Case Modeling

A use-case model consists of several essential elements that graphically and textually describe the system's behavior:

- **Use Cases:**
	These are behaviorally related sequences of steps—both automated and manual—for the purpose of completing a single business task. Graphically, a use case is represented by a **horizontal ellipse**.

- **Actors:**
	An actor is anyone or anything (such as another system) that interacts with the system to exchange information. They are represented as **stick figures**. The sources identify four primary types: **Primary Business Actors**, **Primary System Actors**, **External Server Actors**, and **External Receiver Actors**.
	
- **System Boundary:**
	This is a box drawn around the use cases (referred to as the "Subject" in UML 2) to denote the limits of the system being modeled.
	
- **Use-Case Narrative:**
	This is a textual description of the business event and how the user interacts with the system to accomplish the task. Narratives can be **High-Level** (for quick understanding) or **Expanded** (including details like preconditions, triggers, and typical/alternate courses of events).

# Relationship in Use-Case Diagram

Relationships define how actors and use cases interact. The meaning of a relationship varies depending on the type of line used:

- **Associations:** A relationship where an interaction occurs between an actor and a use case, modeled as a solid line.

- **Include:** Used when a base use case incorporates the behavior of another use case; this helps reduce redundancy by combining common steps.

- **Extend:** Provides a way to insert optional or new behavior into an existing use case through specific "extension points".

- **Generalization:** Factors out behavior common to multiple actors or use cases into a "parent" actor or use case to simplify the model.

- **Depends on:** Indicates that one use case (e.g., Make a Withdrawal) cannot be performed until another (e.g., Make a Deposit) has been executed.

# The Modeling Process

To produce an effective model, analysts typically follow these four steps:

1. **Identify business actors:** Concentrate on who uses the system rather than how it is built.
2. **Identify business requirements use cases:** Determine the goals the actors want to achieve.
3. **Construct use-case model diagram:** Visualize the scope and boundaries.
4. **Document use-case narratives:** Detail the interactions for each use case

# Use Cases vs. User Stories

In **Agile development**, analysts may use **User Stories** as a simpler, shorter way to describe scenarios from a user perspective. While use cases are often long documents containing multiple goals and formal details, user stories are typically short (written on one index card), focus on a single goal with no details, and serve as a "placeholder for conversation".

# Benefits of Use-Case Modeling

Use-case modeling provides several advantages for system development:

- It captures **functional requirements** in a language users understand.
- It assists in decomposing complex systems into **manageable pieces**.
- It aids in estimating **project scope, effort, and schedule**.
- It provides a baseline for **test plans, test cases, and user documentation**.
- It provides a framework for **driving the entire system development project**.

---
# Lecture Notes
![[IS1208 - Use case Modelling.pdf]]