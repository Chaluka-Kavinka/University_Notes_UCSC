# 1 What is System Modeling?

System modeling is the process of developing abstract models of a system, with each model presenting a different view or perspective of that system. It typically uses graphical notations, most commonly the **Unified Modeling Language (UML)**.

The main objectives of modeling include:

- Helping the team find inconsistencies and redundancies.
- Forming a common understanding of activities and resources.
- Providing a way to better understand the flow of information and interactions within a system.


# 2 Perspectives of System Modeling

To fully understand a system, software engineers look at it from several perspectives:

1. **Context models:** Show the system’s environment and how it interacts with other systems.
2. **Interaction models:** Focus on the communication between the system and its environment, or between its internal components.
3. **Structural models:** Display the organization of a system in terms of the components that make it up.
4. **Behavioral models:** Show the dynamic behavior of the system and how it responds to events.

# 3 Sequence Diagrams (Interaction Modeling)

Sequence diagrams are a critical part of UML used extensively by developers to model the **interactions between objects within a single use case**. They show the order in which these interactions occur over time.

## A. Key Components and Notations:

- **Lifeline:** Represented by a labeled rectangle (or actor symbol) at the top with a dashed vertical line extending downward. It represents the passage of time.
- **Actor Symbol:** Represents an entity external to the system that interacts with it.
- **Activation Bar:** A thin rectangle placed on a lifeline to indicate that an object is currently active or performing a task. The longer the box, the longer the task duration.
- **Message Arrows:** Arrows drawn from one lifeline to another to show communication.
    - **Synchronous Message:** (Solid line, solid arrowhead) The sender waits for a response before continuing.
    - **Asynchronous Message:** (Solid line, lined arrowhead) The sender continues without waiting for a response.
    - **Return Message:** (Dashed line, lined arrowhead) Indicates the receiver is done and is returning control to the caller.

## B. Advanced Sequence Diagram Features:

- **Participant Creation/Destruction:** Objects can be created during a sequence (indicated by a `<<create>>` message) or destroyed when no longer needed (indicated by an **'X'** at the end of the lifeline).
- **Reflexive Messages:** Occur when an object sends a message to itself.
- **Alternatives (Choice Box):** A box labeled **"alt"** symbolizes a choice between mutually exclusive message sequences based on a specific condition (similar to an `if-else` statement).

# 4 Other Important UML Diagrams

- **Class Diagrams:** Describe the static structure of the system by showing its classes, attributes, operations, and the relationships between objects.
- **Use Case Diagrams:** Show the interactions between the system and its external environment (actors).
- **State Diagrams:** Describe how the system behaves in response to internal or external events.