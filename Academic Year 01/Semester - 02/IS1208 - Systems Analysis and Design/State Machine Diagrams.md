>[!tip] Introduction
>**State Machine Diagrams** (also known as State Transition Diagrams) are behavioral UML models that capture the **internal life history of a single object**. While Class Diagrams show the static structure of a system, State Diagrams show its **dynamic behavior** by illustrating how an object changes in response to events and time.

---
# 1. Fundamental Components

- **State:** A condition or situation during the life of an object where it satisfies a condition or performs an activity (e.g., a hotel room being "Occupied" or "Available"). It is represented by a **rounded rectangle**.

- **Transition:** A change from one state (originating) to another (successor), represented by an **arrow**.

- **Events:** Triggers—such as a user message or the passage of time—that cause a transition to occur.

- **Initial and Final States:**
    - **Start State:** A **solid black circle**; a diagram must have exactly one.
    - **Stop/End State:** A **bull’s eye symbol** (circle with a ring); an object can have multiple end states.

## Basic Components and Notations of a State Machine Diagram

### 1. Initial state

We use a black filled circle represent the initial state of a System or a Class.
![[Iinitial -state.jpg]]
### 2. Transition

We use a solid arrow to represent the transition or change of control from one state to another. The arrow is labelled with the event which causes the change in state.
![[transition.jpg]]
### 3. State

We use a rounded rectangle to represent a state. A state represents the conditions or circumstances of an object of a class at an instant of time.
![[state.jpg]]
### 4. Fork

We use a rounded solid rectangular bar to represent a Fork notation with incoming arrow from the parent state and outgoing arrows towards the newly created states. We use the fork notation to represent a state splitting into two or more concurrent states.
![[Academic Year 01/Semester - 02/IS1208 - Systems Analysis and Design/Images/State Machine Diagram/fork.jpg]]
### 5. Join

We use a rounded solid rectangular bar to represent a Join notation with incoming arrows from the joining states and outgoing arrow towards the common goal state. We use the join notation when two or more states concurrently converge into one on the occurrence of an event or events.
![[Academic Year 01/Semester - 02/IS1208 - Systems Analysis and Design/Images/State Machine Diagram/join.jpg]]
### 6. Self transition

We use a solid arrow pointing back to the state itself to represent a self transition. There might be scenarios when the state of the object does not change upon the occurrence of an event. We use self transitions to represent such cases.
![[self-transition.jpg]]
### 7. Composite state

We use a rounded rectangle to represent a composite state also. We represent a state with internal activities using a composite state.
![[composite-state.jpg]]
### 8. Final State

We use a filled circle within a circle notation to represent the final state in a state machine diagram.
![[Academic Year 01/Semester - 02/IS1208 - Systems Analysis and Design/Images/State Machine Diagram/final-state.jpg]]
## How to draw a State Machine diagram in UML?

Below are the steps on how to draw the State Machine Diagram in UML:
![[State-Machine-Diagrams-Unified-Modeling-Language-(UML).jpg]]

### Step 1: Identify the System:

- Understand what your diagram is representing.
- Whether it's a machine, a process, or any object, know what different situations or conditions it might go through.
### Step 2: Identify Initial and Final States:

- Figure out where your system starts (initial state) and where it ends (final state).
- These are like the beginning and the end points of your system's journey.
### Step 3: Identify Possible States:

- Think about all the different situations your system can be in.
- These are like the various phases or conditions it experiences.
- Use boundary values to guide you in defining these states.
### Step 4: Label Triggering Events:

- Understand what causes your system to move from one state to another.
- These causes or conditions are the events.
- Label each transition with what makes it happen.
### Step 5: Draw the Diagram with appropriate notations:

- Now, take all this information and draw it out.
- Use rectangles for states, arrows for transitions, and circles or rounded rectangles for initial and final states.
- Be sure to connect everything in a way that makes sense.

>[!example]
>Let's understand State Machine diagram with the help of an example, ie for an ****Online Order**** :
>
>![[state-machine-diagram-for-an-online-order.jpg]]

---
# 2. Transition and State Details

To provide a precise map of behavior, analysts add specific details to these diagrams:

- **Guard Condition:** A Boolean statement in square brackets (e.g., `[count < 10]`) that allows a transition only if the condition is **true**.

- **Action:** A behavior that occurs **instantaneously** during a transition or upon entering/exiting a state.

- **Activity (do:):** A behavior that **takes time** and is performed while the object is in a particular state (e.g., `do: Initialize course`).

- **Entry and Exit Actions:** Specific behaviors triggered the moment an object enters (`entry:`) or leaves (`exit:`) a state.

# 3. Advanced UML 2.0 Features

- **Connection Points:** Specialized **entry and exit points** that show different ways to enter or abruptly leave a complex state.

- **Nested Sub-states:** A "state within a state." For example, a car's "Moving" state might have nested sub-states like "First Gear" and "Second Gear" to show more granular behavior.

# 4. Why We Need State Diagrams

These diagrams are essential for developers because they remove the guesswork regarding **how an object is supposed to behave**. They are typically created only for classes with **significant dynamic behavior**, such as those with a "status" attribute that changes frequently based on complex business rules.

---
# Short Note for Easy Memorization

- **Scope:** Models **ONE** object's life cycle (Dynamic Behavior).
- **Key Shapes:**
    - **Rounded Rectangle:** The State.
    - **Solid Circle:** The Start.
    - **Bull’s Eye:** The End.
- **Triggers:**
    - **Event:** What happened?
    - **Guard:** Is it allowed? `[Condition]`.
- **Internal Behavior (EED):**
    - **E** → Entry: Do this when arriving.
    - **E** → Exit: Do this when leaving.
    - **D** → Do: Do this while staying.
- **Pro-Tip:** If a class has a **"Status"** attribute, it probably needs a State Diagram.

---
# Lecture Notes
![[IS1208 - State Diagrams.pdf]]