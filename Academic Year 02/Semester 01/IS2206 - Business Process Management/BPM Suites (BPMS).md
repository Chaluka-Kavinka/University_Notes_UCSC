# What is Business Process Modeling?

It is the **graphical representation** of a company’s workflows, used to identify potential improvements. It primarily focuses on two states:

- **As-is Model:** The current state of the process without any changes.
- **To-be Model:** The future state after improvements or redesigns have been applied.
#  Modeling Levels

The lectures categorize BPMN into three distinct levels based on the target audience and purpose:

- **Level 1 (Descriptive):** A strategic level that managers can easily understand. It uses basic symbols to clarify the scope, identify resources, and assign responsibilities.
- **Level 2 (Analytical):** More detailed, showing all steps, including **exception paths**. It is often used to create requirements for IT implementation or process simulation.
- **Level 3 (Executable):** The most technical level where the model is part of the actual software implementation. This level is often dependent on specific **BPM Suite (BPMS)** tools.
# Core BPMN Elements

BPMN uses a standardized set of symbols categorized into four main groups:
## A. Swimlanes (Organization)

- **Pools:** Represent a primary participant or the organizational boundary (e.g., "Customer" or "Restaurant"). Interaction between different pools is handled through **Message Flows**, and **Sequence Flows** cannot cross a pool boundary.
- **Lanes:** Sub-partitions within a pool used to organize activities by specific roles (e.g., "Manager" or "Chef").
## B. Flow Objects (Behavior)

- **Activities:** Represent the work being performed.
    - **Tasks:** Atomic work that cannot be broken down further (e.g., User, Manual, Service, Script, or Message tasks).
    - **Sub-processes:** Complex activities that hide internal steps (collapsed) or show them (expanded) to improve readability.
- **Events:** Things that "happen" during a process.
    - **Types:** Start (thin circle), Intermediate (double circle), and End (thick circle).
    - **Triggers:** Includes Timer, Message, Signal, Error, and Compensation.
- **Gateways:** Used to control the flow of the process (forking and joining paths).
    - **Exclusive (X):** Proceed with only one path (if-else).
    - **Parallel (+):** Execute multiple paths concurrently.
    - **Inclusive (O):** Execute any paths where conditions are met.
##  C. Connecting Objects (Flow)

- **Sequence Flow:** A solid arrow showing the chronological order of activities.
- **Message Flow:** A dashed line showing communication between two separate pools.
- **Association:** A dotted line used to link information or **Artifacts** to flow objects.
## D. Artifacts (Additional Information)

- **Data Objects:** Represent inputs and outputs of activities (documents or data).
- **Groups:** A visual grouping of elements for documentation or analysis.
- **Text Annotations:** Comments added to the diagram for better clarity.
# General Guidelines and Naming Conventions

To ensure models are professional and easy to read, follow these rules:

- **Orientation:** Models should be chronological and oriented on a timeline.
- **Activity Naming:** Start with a **verb** followed by a **noun** (e.g., "Approve order").
- **Event Naming:** Start with a **noun** and end with a **past participle verb** (e.g., "Order received").
- **Conciseness:** Avoid labels with more than five words and keep names under 32 characters.
- **Flow Consistency:** Each event and activity should ideally have only one inbound and one outbound sequence flow to avoid ambiguity.