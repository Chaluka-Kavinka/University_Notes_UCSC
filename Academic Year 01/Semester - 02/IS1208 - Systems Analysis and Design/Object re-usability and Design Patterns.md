>[!tip] Introduction
>**Object re-usability** is considered a primary benefit of Object-Oriented Analysis (OOA), enabling more **effective problem solving** and modularity for easier troubleshooting. This concept allows developers to build systems more efficiently by leveraging existing structures rather than starting from scratch.

---
# Mechanisms for Re-usability

The sources highlight several ways re-usability is integrated into system development:

- **Inheritance:**
	This is the fundamental OO concept where attributes and methods defined in a **parent class (super-type)** are inherited or **reused** by a **child class (sub-type)**. For instance, common traits like _firstName_ or _birthdate_ in a _Person_ class are reused by _Student_ and _Teacher_ classes.
- **Reuse-Oriented Software Engineering:**
	This is a specific software process model based on the existence of a significant number of **reusable components**. The focus of this approach is integrating these pre-existing components into a system rather than developing them from scratch.
- **Use-Case Redundancy Reduction:**
	During requirement modeling, analysts look for **reuse possibilities** by identifying common steps shared between different tasks. By using the **\<include\>** **relationship**, common behavior is extracted into an **abstract use case** that can be reused by multiple base use cases, thereby reducing redundancy.
- **Generalization:**
	This technique simplifies models by factoring out behaviors common to two or more actors or use cases into a "parent" element.

# Design Patterns

The provided sources **do not explicitly define or list "Design Patterns"** (such as the Gang of Four patterns like Singleton or Observer). However, they emphasize that **UML (Unified Modeling Language)** provides the standard modeling conventions and notations used to specify these types of object-oriented architectures. Design patterns typically represent proven solutions to common design problems within these UML structures. _Note: You may want to independently verify specific design patterns as they are not detailed in these materials._

---
# Short Note for Easy Memorization

- **Re-usability Goal:** Build faster and improve troubleshooting through **Modularity**.
- **The Big Three of Reuse:**
	- **Inheritance:** "Is-a" relationship; Child reuses Parent’s attributes/methods.
	- **Reuse-Oriented SE:** A process model centered on **integrating existing parts**.
	- **Include (\<include\>):** Extracts common task steps to **avoid redundancy**.
- **UML’s Role:** Provides the **standard notation** (the "alphabet") used to document these reusable designs.