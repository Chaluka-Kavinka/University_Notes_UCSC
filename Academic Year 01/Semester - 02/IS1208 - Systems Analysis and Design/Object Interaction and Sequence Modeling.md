>[!tip] Introduction
>**Object Interaction and Sequence Modeling** focuses on the **dynamic behavior** of a system by illustrating how objects communicate to fulfill a specific business task or scenario.

---
# 1. Sequence Diagrams

Sequence diagrams are behavioral models that show object interactions arranged in **time sequence**.

- **Structure:** They represent the objects and classes involved in a scenario and the sequence of **messages** exchanged between them.
- **Object Notation:** Objects are represented as rectangles with underlined names, which can be specified as just the object name, the object and its class (e.g., `kamalsAccount:BankAccount`), or just the class name (anonymous object).
- **Boundary Classes:** These are added to the diagram to capture **interface requirements** by showing how an actor interacts with the system surroundings.
# 2. System Sequence Diagrams (SSD)

An SSD is a high-level tool used during the logical design phase to identify the messages that enter and exit the **system boundary**.

- It treats the entire system as a "black box" and identifies the inputs and outputs from an actor's perspective.
- The messages identified in an SSD eventually become the **responsibilities** of individual objects within the system.
# 3. UML 2.x Advanced Features

- **Framing:** This feature borders a diagram with a compartment in the upper-left corner for identification.
- **Interaction Fragments:** These allow related messages to be grouped together. They can be combined to allow for **reuse** of one sequence diagram's logic inside another.
- **Combined Fragments:** A subtype of interaction fragment that uses **interaction operators** to define expressions, such as alternative responses based on specific conditions.
# 4. User Interface (UI) Flow Diagrams

While **not technically part of UML**, UI Flow Diagrams (also called **Storyboards**) model the high-level navigation between major user interface elements.

- **Nodes:** Boxes represent major screens or forms.
- **Transitions:** Arrows indicate the possible flow or navigation between those screens.
- **Scope:** They can be drawn for the whole application to provide a high-level overview or for a single Use Case scenario to map specific navigation.

---
# Short Note for Easy Memorization

- **Sequence Diagram Goal:** The **"When"** and **"Who"** of communication (Time + Messages).
- **Lifelines (Objects):** Underlined rectangles; can be anonymous or named.
- **SSD:** The **"Black Box"** view; shows messages crossing the system boundary.
- **Interaction Fragments:** Grouping messages for **Reuse** and logic (like If/Else).
- **UI Flow (Storyboards):** The **"Roadmap"** of the user interface; maps screen navigation.
- **BEC Reminder:** Sequence diagrams often use **B**oundary (UI), **E**ntity (Data), and **C**ontrol (Logic) classes to show interaction.