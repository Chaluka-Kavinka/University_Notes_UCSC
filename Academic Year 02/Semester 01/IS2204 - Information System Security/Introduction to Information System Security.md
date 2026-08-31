# 1. The Core Objective: Protecting Valuables

Security is fundamentally about the protection of valuables. In the context of Information Systems (IS), these valuables have transitioned from physical currency to **computer-related assets and information**, which is now considered the "currency of the 21st century".

A key distinction is made between types of security:

- **Information Security:** Focuses on data in all its forms.
- **Information System Security:** Focuses on the **systems** that manage that data.
- **Cybersecurity:** Focuses on defending against threats in **cyberspace** (the internet and connected systems).

# 2. The CIA Triad: Detailed Breakdown

A secure system requires the presence of three properties. If even one is missing, the system is not truly secure.

- **Confidentiality:** Ensures computer-related assets are only available to **authorized parties**.
    - **Scope:** "Access" includes more than reading; it encompasses viewing, printing, or simply knowing that an asset exists (a concept related to steganography).
    - **Implementation:** It is a straightforward concept but notoriously difficult to implement effectively.
- **Integrity:** Defined as information being **precise, accurate, unmodified, consistent, meaningful, and usable**.
    - **Implementation Pillars:** Achieved through **authorized actions**, **separation and protection of resources**, and **error detection and correction**.
- **Availability:** The requirement that there is a **timely response** to requests and a **fair allocation of resources** (preventing "starvation").
    - **Reliability:** In a secure system, failures should lead to a **graceful cessation of services** rather than an abrupt, catastrophic crash.
    - **Usability:** Services must be easy to use in the manner intended and support **controlled concurrency** (simultaneous access without deadlocks).

# 3. Essential Security Terminology

To analyze security, one must use precise terms to describe the relationship between weaknesses and harmful events:

- **Vulnerability:** A specific weakness in the security system.
- **Threat:** A set of circumstances that has the **potential** to cause loss or harm.
- **Attack:** A deliberate **human exploitation** of a vulnerability.
- **Problems:** The consequences of unintentional, accidental errors.
- **Risks:** The **probabilities** that a threat or problem will occur because of a system vulnerability.
- **Control:** A protective measure (action, device, or procedure) that removes, reduces, or neutralizes a vulnerability.

# 4. Categories of Threats and Concerns

Threats generally target one or more of the CIA properties through these actions:

- **Interruption:** A resource is lost, becomes unavailable, or is rendered unusable (targets **Availability**).
- **Interception:** Unauthorized access to a computer resource (targets **Confidentiality**).
- **Modification:** Illegal or accidental change/tampering with a resource (targets **Integrity**).
- **Fabrication:** The creation of illegal, counterfeit, or incorrect resources.

# 5. The Human Element: "The People Involved"

The sources classify the individuals who interact with system security into four groups based on their intent and the impact of their actions:

- **Amateurs:** Often cause "problems" through accidental access or unauthorized operations; they generally cause no harm to regular users.
- **Crackers:** Engage in active attempts to access sensitive resources and discover vulnerabilities, causing "minor inconveniences".
- **Criminals:** Actively utilize weaknesses in the protection system to **steal or destroy** resources, causing serious problems for users.
- **Regular Users:** Have specific requirements for authentication, authorization, and message integrity in open networks.

# 6. Information States and Protection Models

Security must be maintained throughout the **Information Life Cycle**, which includes data in three states: **At rest** (stored), **In transit** (moving across networks), and **In use** (being processed).

**The Onion Model of Protection:** This hierarchy visualizes security starting from the core hardware and moving outward through various layers, each requiring its own protection mechanisms:

1. **Hardware** (The Core)
2. **OS Kernel**
3. **Operating System**
4. **Services**
5. **Applications** (The Outer Layer)

# 7. Methods of Protection

System defense is implemented through four primary controls:

- **Encryption:** Used for confidentiality, authentication of users/messages, and access control.
- **SW & HW Controls:** Includes internal software, OS controls, and special hardware devices.
- **Policies:** Precise specifications regarding organizational issues, security methods, and parameters.
- **Physical Controls:** Physical measures like isolation of equipment, biometric locks, and archiving/backups.

# 8. The "MOM" Principle and User Responsibility

For an attack to occur, a perpetrator needs **Method** (skills/tools), **Opportunity** (time/access), and **Motive** (the reason for the attack). Ultimately, your sources emphasize that **"Sec_rity is not Complete without U"**. As a user, you are responsible for the protection of the hardware, software, data, and services you own or manage.