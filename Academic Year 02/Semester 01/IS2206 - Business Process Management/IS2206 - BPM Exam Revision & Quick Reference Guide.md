# 📑 IS2206: Business Process Management — Exam Quick Revision Guide

#Exam-Prep #BPM #IS2206 #Revision-Guide

> [!Tip] Purpose of this Guide
> A high-yield, concise exam-revision summary covering the core definitions, formulas, BPMN modeling rules, analysis frameworks, and change management models for **IS 2206 (Business Process Management)**.

---

## 1. 🔄 The 6-Phase BPM Life Cycle

![[The 6-Phase BPM Life Cycle.png]]


| Phase | Core Objective | Key Deliverable / Focus |
| :--- | :--- | :--- |
| **1. Identification** | Define process architecture & rank priority. | Process Portfolio & Prioritization Matrix |
| **2. Discovery** | Elicit and document the current state. | **"As-Is" Process Model** |
| **3. Analysis** | Identify issues, bottlenecks, waste, and costs. | Issue Register, Root-Cause Analysis, Flow Analysis |
| **4. Redesign** | Design improvements addressing identified issues. | **"To-Be" Process Model** |
| **5. Implementation** | Transform model into executable workflows/IT. | BPMS Deployment, Organizational Change |
| **6. Monitoring** | Track operational KPIs, logs, and conformance. | Dashboards, Performance Metrics, Process Mining |

---

## 2. 🏛️ Process Identification & Architecture

### Process Architecture Levels
* **Level 1 (Process Categories):** High-level enterprise scope (e.g., Core / Operational, Management, Support).
* **Level 2 (Process Groups):** Logical cluster of processes (e.g., Procurement, Manufacturing, Customer Care).
* **Level 3 (Core Processes):** End-to-end executable flows (e.g., Order-to-Cash, Procure-to-Pay).

### Prioritization Criteria (The 3 Dimensions)
1. **Importance:** Which processes have the greatest impact on strategic company goals?
2. **Dysfunction (Urgency):** Which processes are experiencing the worst bottlenecks or customer complaints?
3. **Feasibility:** Which processes are easiest or most realistic to change given budget, culture, and technology?

---

## 3. 📐 BPMN 2.0 Golden Rules & Elements

### 🏊 Pools vs. 🛣️ Lanes
* **Pool:** Represents an **independent participant or external organization** (e.g., *Customer*, *Bank*, *Vendor*).
* **Lane:** Represents an **internal department, role, or system** inside the *same* organization (e.g., *Sales*, *Finance*, *Warehouse*).

### 🎯 Arrow Rules
* **Sequence Flow (`──────►` Solid line):**
  * ✅ Can connect activities within the **same Lane**.
  * ✅ Can cross **Lanes** within the **same Pool**.
  * ❌ **NEVER crosses Pool boundaries.**
* **Message Flow (`- - - ▷` Dashed line):**
  * ✅ Connects **two DIFFERENT Pools** (or a Pool and an external event).
  * ❌ **NEVER connects elements inside the same Pool or Lane.**

### 🔀 Gateway Types
| Gateway | Symbol | Behavior / Rule |
| :--- | :---: | :--- |
| **Exclusive (XOR)** | `[ ✕ ]` | Evaluates conditions and chooses **EXACTLY ONE** branch. |
| **Parallel (AND)** | `[ + ]` | Executes **ALL** outgoing branches simultaneously in parallel. |
| **Inclusive (OR)** | `[ ◯ ]` | Evaluates conditions and chooses **ONE OR MORE** active branches. |
| **Event-Based** | `[ ⬡ ]` | Waits for external events; path taken depends on **which event occurs first**. |

---

## 4. 🔍 Process Discovery & Quality Assurance

### Information Gathering Techniques
1. **Evidence-Based:** Document analysis, direct observation, automated process mining from event logs.
2. **Interview-Based:** Structured 1-on-1 interviews with process actors and managers.
3. **Workshop-Based:** Interactive group sessions resolving cross-departmental discrepancies.

### Model Quality Dimensions
* **Syntactic Quality (Verification):** *"Are we building the model right?"* (Conforms to BPMN 2.0 syntax, free of deadlocks/livelocks).
* **Semantic Quality (Validation):** *"Are we building the right model?"* (Truthfully represents real-world business activities and outcomes).
* **Pragmatic Quality (Readability):** Easy for humans to read (guided by the **Seven Process Modeling Guidelines — 7PMG**).

---

## 5. 📊 Process Analysis: Qualitative & Quantitative

### A. Qualitative Analysis
1. **Value-Added Analysis:**
   * **VA (Value-Adding):** Directly generates value that the customer is willing to pay for.
   * **BVA (Business Value-Adding):** Necessary for business survival, compliance, accounting, or risk management (customer does not directly value it).
   * **NVA (Non-Value-Adding / Waste):** Pure waste (rework, waiting, redundant handoffs, duplicated data entry).
2. **Root-Cause Analysis:**
   * **Cause-and-Effect / Fishbone (Ishikawa) Diagram:** Categorizes causes using the **6 Ms** (*Machine, Method, Material, Manpower, Measurement, Milieu/Mother Nature*).
   * **5 Whys Analysis:** Recursively asking "Why?" to reach the core root cause.
3. **Issue Register:** Structured catalog recording Issue Name, Impact, Frequency, and Estimated Financial Loss.

### B. Quantitative Analysis & Formulas

#### 📐 Little’s Law
$$\mathbf{WIP = \lambda \times CT}$$
* $WIP$ = Work In Progress (average number of items in system)
* $\lambda$ = Arrival Rate (throughput / items per unit time)
* $CT$ = Cycle Time (total time an item spends from start to finish)

#### ⏱️ Cycle Time Efficiency ($CTE$)
$$\mathbf{CTE = \frac{TCT}{CT} \times 100\%}$$
* $TCT$ = Theoretical Cycle Time (pure hands-on processing time without waiting)
* $CT$ = Total Cycle Time (Processing Time + Waiting/Queue Time)

---

## 6. 🛠️ Process Redesign & The Devil's Quadrangle

### 😈 The Devil's Quadrangle
When improving a process, balancing these four dimensions is critical (improving one often tradeoffs with another):

![[The Devils Quadrangle.png]]


1. **Time:** Reduce cycle time, processing time, and waiting time.
2. **Cost:** Lower operational costs, labor costs, and material waste.
3. **Quality:** Increase external customer satisfaction and reduce internal error rates.
4. **Flexibility:** Enhance the ability to respond to changing market demands and custom orders.

### 🧩 Core Redesign Heuristics
* **Task Elimination:** Remove unnecessary checks, redundant approvals, and non-value-adding steps.
* **Task Automation:** Deploy automated scripts, OCR, or BPMS to execute repetitive tasks.
* **Parallelism:** Execute independent tasks simultaneously rather than sequentially.
* **Triage (Case Specialization):** Route easy cases to fast tracks / bots, and complex cases to senior experts.
* **Resequencing:** Postpone expensive checks or perform high-rejection-rate checks first ("knockout" approach).

---

## 7. 🚀 Implementation, BPMS & Change Management

### BPMS Architecture Components
* **Execution Engine:** Coordinates process state and routes work tokens based on BPMN logic.
* **Worklist Handler:** Presents human tasks to the assigned user inbox/dashboard.
* **Process Modeling Tool:** Environment for designing and configuring executable BPMN diagrams.
* **Administration & Monitoring Console:** Tracks runtime instances, bottlenecks, and system health.

### 🧊 Kurt Lewin’s 3-Stage Change Management Model
1. **Unfreeze (Melt the Status Quo):**
   * Communicate why the old process is failing and build readiness for change.
   * Address employee anxiety and build stakeholder alignment.
2. **Change / Move (Transition):**
   * Deploy the new process/system, provide hands-on training, and guide new behaviors.
3. **Refreeze (Lock in New Habits):**
   * Institutionalize new standard operating procedures (SOPs), align KPIs, reward adoption, and prevent relapse into old habits.

### ⚖️ Lewin's Force Field Analysis
* **Driving Forces:** Pressures *for* change (technology, competition, strategy).
* **Restraining Forces:** Pressures *against* change (fear, loss of power, habits).
* **Equilibrium:** Status quo where Driving Forces = Restraining Forces.
* **Goal:** Enable change primarily by **reducing restraining forces** (lowers resistance with less friction).

### 🚀 Kotter's 8-Step Change Model
1. **Create Urgency:** Highlight threats, opportunities, and competitive realities.
2. **Form a Guiding Coalition:** Assemble key influencers across levels and departments.
3. **Create a Vision for Change:** Define clear values and a concise future-state strategy.
4. **Communicate the Vision:** Share constantly, address fears, and lead by example.
5. **Remove Obstacles:** Align structures/rewards and empower change agents.
6. **Create Short-Term Wins:** Deliver early, visible, low-risk successes.
7. **Build on the Change:** Consolidate gains and drive continuous improvement.
8. **Anchor Changes in Corporate Culture:** Institutionalize values in hiring, training, and norms.

