**Process Discovery** is the act of gathering information about an existing process and organizing it into an **"As-is" process model**. The primary goal is to create models that are both **correct and complete**.

# 1. The Discovery Team

A successful discovery project requires a collaboration between two distinct roles:

- **Process Analyst:** A "translator" with strong BPMN modeling skills but limited knowledge of the specific business operations.
- **Domain Expert:** Has detailed knowledge of the process operations (inputs, outputs, participants) but typically has limited modeling skills and may prefer natural language over diagrams.

# 2. Information Gathering Techniques

Analysts use several methods to build a process understanding:

- **Evidence-Based Discovery:**
    - **Document Analysis:** Reviewing org charts, policies, and forms. It is low-cost and unbiased but documents are often outdated or not process-oriented.
    - **Observation:** Watching experts perform their work. It provides context-rich insights but can be intrusive, and people may act differently when watched.
    - **Automated Discovery (Process Mining):** Extracting knowledge from system event logs. It is objective and covers extensive cases but depends on high data quality.
- **Interview-Based Discovery:** Direct inquiries with experts to identify activities and exceptions. It captures "rich" information and history but is time-consuming.
- **Workshop-Based Discovery:** Bringing all stakeholders together with a facilitator to map the process (often using sticky notes). This is excellent for resolving conflicting views but difficult to schedule.

# 3. The Five-Stage Modeling Method

Once information is gathered, the model is constructed in these steps:

1. **Identify Boundaries:** Define the start/end points, triggers, and expected outcomes.
2. **Identify Activities and Events:** List all major tasks and milestones.
3. **Identify Resources and Handovers:** Determine who is responsible for each task and where work moves between participants.
4. **Identify Control Flow:** Establish the logical sequence, including decision points and parallel paths.
5. **Identify Additional Elements:** Add data objects, annotations, and exception handlers.

# 6. Quality Assurance

Analysts must ensure the model meets three quality criteria:

- **Syntactic Quality (Verification):** The model follows BPMN rules (e.g., no sequence flows across pool boundaries).
- **Semantic Quality (Validation):** The model makes "true" statements that accurately reflect the real-world domain.
- **Pragmatic Quality (Layout):** The model is easy to read, maintain, and use for learning.

# 5. "7" Process Modeling Guidelines (7PMG)

To reduce complexity and improve clarity, analysts follow these rules:

- **G1:** Use as few elements as possible.
- **G2:** Minimize routing paths per element.
- **G3:** Use one start and one end event per path.
- **G4:** Model as structured as possible.
- **G5:** Avoid OR gateways.
- **G6:** Use verb-noun labels for activities.
- **G7:** Decompose any model with more than 30 elements.