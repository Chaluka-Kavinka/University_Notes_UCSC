>[!tip] Introduction
>**Class Diagrams** are the primary example of structural UML diagrams, used to document software architecture by emphasizing the static structure of a system through classes, their attributes, methods, and relationships. Complementing these structural models in modern development are **Agile techniques**, which prioritize customer-oriented delivery over heavy documentation.

---
# Components of a Class Diagram

A class is a generalized description of a collection of similar objects, which are referred to as "instances" of that class. In a diagram, a class is represented as a box divided into three compartments:

- **Class Name:** Located in the top compartment, it is the most essential information and is typically centered and bold.
- **Attributes:** Representing properties or data members, these are listed in the second compartment and often include their data type.
- **Methods:** These represent the functionality or behavior of the class and are listed in the third compartment.

**Visibility Notations** indicate the access level for these components:

- **+ (Public):** Visible to all classes.
- **- (Private):** Visible only within that specific class.
- **# (Protected):** Visible to sub-classes.
- **~ (Package):** Visible to classes within the same package.

![[Class diagram notation.webp]]
# Class Relationships

Relationships define how different classes interact within the system:

- **Association:** A bidirectional connection between classes.
- **Aggregation:** A "whole-part" relationship where the "part" (child class) can **exist independently** of the "whole" (parent class), such as computer parts in a store.
- **Composition:** A stronger "whole-part" relationship where the part **cannot exist independently** of the whole, such as a headlight on a specific car.
- **Generalization (Inheritance):** An "is-a" relationship where a subclass inherits properties and behaviors from a super-class.
- **Dependency/Usage:** A loosely coupled connection where one class utilizes the services of another to perform a task.

![[Class diagrams relations.png]]
# Class Diagram Arrows

![[Class diagrams arrows.webp]]
# Agile Techniques

Agile methods are newer than UML and focus on flexibility and the needs of the user.

- **User Stories:**
	These are short, simple descriptions of a feature from the user's perspective. They follow the format: _"As a [type of user], I want [goal], so that [reason]"_.
- **User Story Points:**
	A relative measure used to indicate how long it will take programmers to implement a specific story.
- **Epics and Themes:**
	An **Epic** is a large user story that is too big to be completed in a single sprint and must be decomposed into smaller stories. **Themes** are collections of related smaller stories organized around a common topic.
- **CRC Cards (Class-Responsibility-Collaborator):**
	A technique used to identify a class's name, its specific responsibilities, and the other classes it must collaborate with to realize those responsibilities.
---
# Comparison: User Stories vs. Use Cases**

The sources distinguish these two requirements tools as follows:

- **User Stories:** Short (one index card), focus on one goal with no details, and serve as a **"placeholder for conversation"**.
- **Use Cases:** Long documents containing multiple goals and formal details, serving as a **"record of conversation"**.
---
# Short Note for Easy Memorization

- **Class Diagram (N-A-M):**
	- **N**ame (Bold/Top).
	- **A**ttributes (Data/Middle).
	- **M**ethods (Behavior/Bottom).
- **Visibility Symbols:** **+** (Public), **-** (Private), **#** (Protected).
- **Relationships:**
	- _Aggregation:_ Part lives alone (Open diamond).
	- _Composition:_ Part dies with whole (Filled diamond).
	- _Generalization:_ "Is-a" / Inheritance.
- **Agile Vocabulary:**
	- **User Story:** "As a... I want... So that..."
	- **Epic:** A story too big for one sprint.
	- **CRC Card:** Class, Responsibility, Collaborators.
---
# Lecture Notes
![[IS1208 - Class Diagrams and some Agile Techniques.pdf]]