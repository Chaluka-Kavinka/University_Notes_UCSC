**Process Identification** is a systematic set of activities used to define an organization's business processes and establish criteria for prioritizing them. The ultimate result is a **process architecture**, which acts as a framework for specifying the scope of future modeling and redesign projects.

# 1. The Two Phases of Identification

To build a process architecture, organizations follow two main stages:

- **Designation Phase:** The goal is to gain an initial understanding of all processes and their interrelationships.
    - **Process Enumeration:** This involves deciding how many processes to list. It is a trade-off: broad processes cover more ground but are harder to manage, while narrow processes are easier to fine-tune but have less strategic impact.
    - **Defining Boundaries:** Since processes are interdependent, analysts must define where one ends and another begins.
- **Evaluation Phase:** Analysts prioritize which processes need the most attention based on three criteria:
    - **Importance:** Which processes have the greatest impact on strategic goals?
    - **Dysfunction:** Which processes are in the "deepest trouble" or currently performing poorly?
    - **Feasibility:** How easy or likely is it that a BPM initiative will succeed for this process?

# 2. Process Architecture Levels

Process architecture is often visualized as a three-level pyramid, moving from abstract to detailed:

- **Level 1 (Process Landscape):** Shows the main, high-level processes of the company.
- **Level 2 (Abstract Process Models):** Often called **process maps**, these show a finer degree of granularity but remain relatively abstract, usually showing linear progress without exceptions.
- **Level 3 (Detailed Process Models):** These are full BPMN models showing every detail, including control flows, data inputs/outputs, and specific participants.

# 3. The Dijkman Approach

These notes highlight a specific four-step method for identifying processes to build that Level 1 architecture:

1. **Identify Case Types:** Determine what the organization handles, such as products (toys), services (insurance), or specific customer types (frequent flyers vs. regular).
2. **Identify Functions:** List what the organization _does_ (e.g., purchasing, sales). Analysts often use reference models like ITIL or APQC as a starting point.
3. **Construct Case/Function Matrices:** Create a grid with case types as columns and functions as rows. An "X" is placed where a function applies to a specific case.
4. **Identify Processes:** Group these "X" marks into distinct processes using guidelines. For example, you might split a process if it has different flow objects (like a mortgage application vs. a monthly payment) or if it is performed differently in different locations.