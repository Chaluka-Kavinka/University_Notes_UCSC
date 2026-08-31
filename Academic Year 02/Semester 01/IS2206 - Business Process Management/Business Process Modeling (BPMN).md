**Business Process Model and Notation (BPMN)** is the global standard for graphical process modeling, providing a set of over 100 symbols that make workflows understandable to both business analysts and technical developers,.

# 1. Modeling Detail Levels

Process models are created at different levels of granularity depending on their purpose:

- **Level 1 (Descriptive):** High-level strategic models that define process scope and KPIs using basic symbols; they are designed to be easily understood by managers without BPMN experience.
- **Level 2 (Analytical):** Detailed models that include exception paths and every process step; these are used for performance simulation or creating IT requirements.
- **Level 3 (Executable):** Technical models used for actual process implementation; these are often specific to the software tools being used.

# 2. Core BPMN Elements

BPMN elements are divided into four main categories:

## A. Swimlanes (Organizational Responsibility)

- **Pools:** Represent a process or a primary participant, such as an entire company.
- **Lanes:** Sub-partitions within a pool used to assign tasks to specific roles (e.g., "Manager") or departments. While _Message Flow_ connects pools, _Sequence Flow_ is used to connect elements within a single pool,.

## B. Flow Objects (The Work Itself)

- **Activities (Rounded Rectangles):** Represent the work performed. These can be **Tasks** (single, atomic units of work) or **Sub-processes** (composite activities that can be "collapsed" to simplify a complex diagram),,.
- **Events (Circles):** Represent something that "happens". They are categorized as **Start** (thin circle), **Intermediate** (double circle), and **End** (thick circle),,.
- **Gateways (Diamonds):** Control the flow of a process by forking or joining paths. Common types include **Exclusive (X)** for choosing one path and **Parallel (+)** for executing multiple tasks concurrently.

## C. Connecting Objects (The Logic)

- **Sequence Flow (Solid Arrow):** Indicates the chronological order of activities.
- **Message Flow (Dashed Arrow):** Shows communication between two separate pools/participants.
- **Association (Dotted Line):** Links artifacts, like documentation or data, to specific flow objects.

## D. Artifacts (Additional Context)

- **Data Objects:** Define the inputs and outputs of activities (e.g., a "Purchase Order" document).
- **Text Annotations:** Allow modelers to add comments or explanations for better readability.

# 3. Modeling Guidelines

To maintain professional standards, analysts follow specific naming conventions:

- **Activity Labels:** Must begin with a verb followed by a noun (e.g., "Approve request").
- **Event Labels:** Should begin with a noun and end with a past participle verb (e.g., "Invoice sent").
- **Length:** Labels should generally be under five words to ensure the diagram remains clear.