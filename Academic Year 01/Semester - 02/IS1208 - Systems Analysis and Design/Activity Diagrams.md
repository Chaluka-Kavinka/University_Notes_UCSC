>[!tip] Introduction
>**Activity Diagrams** model the process steps or specific use-case activities within a system, representing its **dynamic behavior**. While they are similar to flowcharts, they are unique because they can graphically represent **parallel activities**.

# Key Components of Activity Diagrams

- **Activities:** Represent the performance of a behavior in the workflow, shown as **rounded rectangles**.
- **Transitions:** Arrows that show the passing of the flow of control from one activity to the next.
- **Initial and Final Nodes:** A **solid filled circle** indicates the starting point, while a **bull’s eye symbol** indicates the final activity.
- **Decision Points:** Branching points where control follows different paths based on a **guard condition** (a statement in square brackets).
- **Merge Points:** Used to combine multiple flows that were previously separated by a decision point back into a single flow.
## Activity Diagram Notations
![[Activity-Diagram-Notations.jpg]]

### 1. Initial State

The starting state before an activity takes place is depicted using the initial state.
![[initial-state.jpg]]
### 2. Action or Activity State

An activity represents execution of an action on objects or by objects. We represent an activity using a rectangle with rounded corners. Basically any action or event that takes place is represented using an activity.
![[activity-state.jpg]]
### 3. Action Flow or Control flows

Action flows or Control flows are also referred to as paths and edges. They are used to show the transition from one activity state to another activity state.
![[control-flow.jpg]]
### 4. Decision node and Branching

When we need to make a decision before deciding the flow of control, we use the decision node. The outgoing arrows from the decision node can be labelled with conditions or guard expressions. It always includes two or more output arrows.
![[decision-node.jpg]]
### 5. Guard

A Guard refers to a statement written next to a decision node on an arrow sometimes within square brackets.
![[guard.jpg]]
### 6. Fork

Fork nodes are used to support concurrent activities. When we use a fork node when both the activities get executed concurrently i.e. no decision is made before splitting the activity into two parts. Both parts need to be executed in case of a fork statement. We use a rounded solid rectangular bar to represent a Fork notation with incoming arrow from the parent activity state and outgoing arrows towards the newly created activities.
![[Academic Year 01/Semester - 02/IS1208 - Systems Analysis and Design/Images/Activity Diagram/fork.jpg]]
### 7. Join

Join nodes are used to support concurrent activities converging into one. For join notations we have two or more incoming edges and one outgoing edge.
![[Academic Year 01/Semester - 02/IS1208 - Systems Analysis and Design/Images/Activity Diagram/join.jpg]]
### 8. Merge or Merge Event

Scenarios arise when activities which are not being executed concurrently have to be merged. We use the merge notation for such scenarios. We can merge two or more activities into one if the control proceeds onto the next activity irrespective of the path chosen.
![[merge.jpg]]
### 9. Swimlanes

We use Swimlanes for grouping related activities in one column. Swimlanes group related activities into one column or one row. Swimlanes can be vertical and horizontal. Swimlanes are used to add modularity to the activity diagram. It is not mandatory to use swimlanes. They usually give more clarity to the activity diagram. It's similar to creating a function in a program. It's not mandatory to do so, but, it is a recommended practice.
![[swimlane.jpg]]
### 10. Time Event

This refers to an event that stops the flow for a time; an hourglass depicts it. We can have a scenario where an event takes some time to completed.
![[time-event.jpg]]
### 11. Final State or End State

The state which the system reaches when a particular process or activity ends is known as a Final State or End State. We use a filled circle within a circle notation to represent the final state in a state machine diagram. A system or a process can have multiple final states.
![[Academic Year 01/Semester - 02/IS1208 - Systems Analysis and Design/Images/Activity Diagram/final-state.jpg]]

## Draw an Activity Diagram in UML
![[Steps-to-Draw-an-Activity-Diagram.jpg]]
### Step 1. Identify the Initial State and Final States:

- This is like setting the starting point and ending point of a journey.
- Identify where your process begins (initial state) and where it concludes (final states).
- For example, if you are modelling a process for making a cup of tea, the initial state could be "No tea prepared," and the final state could be "Tea ready."

### Step 2. Identify the Intermediate Activities Needed:

- Think of the steps or actions required to go from the starting point to the ending point.
- These are the activities or tasks that need to be performed.
- Continuing with the tea-making , intermediate activities could include "Boil water," "Pour tea into a cup".

### Step 3. Identify the Conditions or Constraints:

- Consider the conditions or circumstances that might influence the flow of your process.
- These are the factors that determine when you move from one activity to another.
- Using the tea-making scenario, a condition could be "Water is boiled," which triggers the transition to the next activity.

### Step 4. Draw the Diagram with Appropriate Notations:

Now, represent the identified states, activities, and conditions visually using the appropriate symbols and notations in an activity diagram. This diagram serves as a visual map of your process, showing the flow from one state to another.

---
# Synchronization: Forks and Joins

Activity diagrams use **synchronization bars** to manage concurrent workflows:

- **Fork:** A bar with one incoming transition and multiple outgoing transitions, splitting execution into **concurrent threads** that occur at the same time or in any order.
- **Join:** A bar with multiple incoming transitions and one outgoing transition; the flow cannot continue until **all incoming actions** are completed.

# Organizational Tools: Swimlanes

**Swimlanes** are used to partition a diagram into vertical columns. This allows the analyst to clearly show **who is responsible** (which actor or department) for each specific activity in a complex business process.

# Practical Application

Activity diagrams are highly useful for **communicating logic to programmers**. However, analysts are cautioned when using them with non-technical users, who may find them difficult to follow; for users, **use-case narratives** are often preferred.

---
# Short Note for Easy Memorization

- **Definition:** The "Workflow" or "Dynamic" model (Flowchart + Parallelism).
- **Nodes (Shapes):**
	- **Rounded Rectangle:** Activity (Action).
	- **Diamond:** Decision / Merge.
	- **Solid Circle:** Start.
	- **Bull’s Eye:** End.

- **Concurrency (Bars):**
	- **Fork:** 1 in → Many out (Split).
	- **Join:** Many in → 1 out (Wait for all).

- **Swimlanes:** Define **Accountability** (Who does what?).

---
# Lecture Notes
![[IS1208 - Activity Diagrams.pdf]]
