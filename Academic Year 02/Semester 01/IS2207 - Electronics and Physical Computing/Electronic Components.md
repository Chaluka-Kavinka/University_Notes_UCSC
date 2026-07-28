In this second topic, we transition from theoretical laws to the physical building blocks of electronic systems. **Electronic components** are generally categorized into **passive**, which do not require an external power source to operate, and **active**, which require external power and can control, amplify, or generate electrical signals.

# 1. Passive Components

Passive components are the "support staff" of a circuit. They do not amplify signals but are essential for controlling current and storing energy.

- **Resistors (R):**
    - **Function:** Their primary purpose is to **limit current**, divide voltage, or provide biasing for transistors. They convert electrical energy into heat to oppose the flow of charge.
    - **Unit:** Measured in **Ohms (Ω)**.
    - **Packaging:** They come in **Through-Hole (THT)** for prototyping or **Surface Mount (SMD)** for compact commercial PCBs.
- **Capacitors (C):**
    - **Function:** These store electrical energy temporarily in an **electric field** between two conductive plates separated by an insulator. They are used for **filtering noise**, smoothing power supplies, and timing circuits.
    - **Unit:** Measured in **Farads (F)**.
    - **Reactance (XC​):** Capacitors block DC while allowing high-frequency AC signals to pass more easily.
- **Inductors (L):**
    - **Function:** They store energy in a **magnetic field** when current flows through them. They are critical for RF circuits, power supplies, and filters.
    - **Reactance (XL​):** Unlike capacitors, inductors oppose changes in current and their resistance to AC increases with frequency.
- **Transformers:** These consist of coupled inductors used to **step-up** or **step-down** AC voltage levels based on the turn ratio of the coils.

---

# 2. Active Components (Semiconductors)

Active components are the "controllers" of the system. They are made of semiconductor materials like Silicon and can provide **power gain**, where the output signal is stronger than the input.

- **Diodes:**
    - **Mechanism:** A two-terminal device that acts as a **one-way valve**, allowing current to flow only when **forward-biased** (positive to P-type, negative to N-type).
    - **Types:**
        - **Signal Diodes:** Used for low-current signal processing.
        - **Power Diodes:** Designed to handle large currents, primarily for **rectification** (converting AC to DC).
        - **Zener Diodes:** Designed to operate in the **reverse breakdown region** to provide a constant voltage reference or regulation.
        - **LEDs (Light Emitting Diodes):** Convert electrical energy into light when forward-biased.
- **Bipolar Junction Transistors (BJT):**
    - **Terminals:** Consist of three layers: **Emitter (E), Base (B), and Collector (C)**.
    - **Operation:** A **current-controlled** device where a small current at the Base controls a much larger current between the Collector and Emitter.
    - **Modes:** They can function as a **switch** (operating in saturation or cut-off regions) or an **amplifier** (operating in the active region). The **Common Emitter (CE)** configuration is the most widely used for amplification due to its high power gain.
- **Field Effect Transistors (FET/MOSFET):**
    - **Operation:** A **voltage-controlled** device where an electric field at the **Gate (G)** terminal controls the current flow between the **Source (S)** and **Drain (D)**.
    - **Advantage:** They have **very high input impedance**, meaning they draw almost no current from the signal source, making them more efficient than BJTs for many applications.

---

# 3. Specialized and Integrated Components

As systems become more complex, multiple components are combined into single packages.

- **Integrated Circuits (ICs):** These are silicon chips that contain thousands or millions of tiny resistors, capacitors, and transistors fabricated together. Examples include the **555 Timer** for generating pulses or microcontrollers like the **ATmega328P** (the "brain" of an Arduino).
- **Operational Amplifiers (Op-Amps):**
    - **Role:** High-performance differential amplifiers that amplify the **difference** between two inputs.
    - **Ideal Characteristics:** An ideal op-amp has **infinite gain**, **infinite input impedance**, and **zero output impedance**.
    - **Applications:** Using **negative feedback**, they are used for mathematical operations (addition, integration), signal conditioning, and as **comparators** to detect voltage thresholds.
- **Thyristors (SCR, TRIAC):**
    - **Latching Switches:** These act as electronic switches that, once triggered by a gate pulse, stay **ON** as long as current continues to flow. They are essential for high-power AC/DC control and motor drives.

# Summary of Component Selection

Understanding these components allows you to begin the **Electronic Circuit Design Process**, which moves from **Conceptual Design** (selecting the right components) to **Simulation** (testing behavior in software) and finally **Prototyping** on a breadboard or PCB. For instance, if you need to drive a high-power motor with a tiny microcontroller signal, you might choose a **MOSFET** as a switch or a **Darlington Transistor Pair** for high current gain.