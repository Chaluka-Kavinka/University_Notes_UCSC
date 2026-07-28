This topic explores the basic physics of electronics, the core quantities used to measure electricity, the essential laws for circuit analysis, and the properties of the signals that drive physical computing systems.

# 1. Core Electrical Quantities

Electronics is defined as the study and use of devices that operate by controlling the flow of electrons or other charge carriers. To understand these systems, we must first master the fundamental quantities:

- **Charge (Q):** The fundamental property of matter responsible for electric phenomena. The unit of charge is the **Coulomb (C)**. A single electron carries a charge of approximately, $$−1.6×10^{−19} \text{ C}$$
- **Current (I):** The rate of flow of electric charge through a conductor. It is calculated as $I=\frac{Q}{t}$ and measured in **Amperes (A)**. Conventional current flow is considered to move from positive to negative, while actual electron flow moves from negative to positive.
- **Voltage (V):** The potential difference between two points, often described as the "push" or pressure that drives current through a circuit. The unit is the **Volt (V)**.
- **Resistance (R):** The opposition to the flow of current in a material. It is measured in **Ohms (Ω)**.
- **Power (P):** The rate at which electrical energy is consumed or generated. It is calculated using the formulas $P=VI$, $P=I^2R$, or $P= \frac{V^2}{R}$ and is measured in **Watts (W)**.
- **Impedance (Z):** The total opposition to alternating current (AC) that includes both resistance and **reactance** (opposition from capacitors and inductors). It is represented as $Z=R+jX$ and measured in **Ohms (Ω)**.

# 2. Essential Circuit Laws and Theorems

These mathematical tools allow us to analyze how energy moves through a system:

- **Ohm’s Law:** Defines the linear relationship where Voltage equals Current multiplied by Resistance ($V=I \times R$).
- **Kirchhoff’s Current Law (KCL):** States that the sum of all currents entering a junction (node) must equal the sum of currents leaving it, meaning the algebraic sum of currents at a node is zero.
- **Thevenin’s Theorem:** This theorem states that any linear two-terminal circuit can be simplified into an equivalent circuit consisting of a single voltage source ($V_{th}$​) in series with a single resistor ($R_{th}$​).
- **Norton’s Theorem:** Similarly, any linear two-terminal circuit can be replaced by an equivalent current source ($I_n$​) in parallel with a single resistor ($R_n$​).

# 3. Signal Properties

In physical computing, we use signals to represent information. Signals are generally classified into two types: **Analog** (continuous waves) and **Digital** (discrete steps or 0s and 1s).

- **Amplitude:** The maximum height of the wave from its zero level, measured in Volts.
- **Frequency (f):** How often a wave repeats per second, measured in **Hertz (Hz)**. It is the inverse of the **Period (T)** ($f= \frac {1}{T}$), which is the time taken to complete one full cycle.
- **Phase (Φ):** The offset or shift of a waveform in time relative to another reference waveform.
- **RMS (Root Mean Square) Voltage:** The effective value of an AC voltage. For example, the standard 230V AC household supply is an RMS value; its actual peak voltage is approximately 325V ($V_\text{peak} ​=\sqrt{2} \times V_{RMS}$​).
- **Duty Cycle:** Specifically for digital or pulse waves, this is the percentage of time the signal is "HIGH" (ON) during one full period. A 50% duty cycle means the signal is ON for half the time and OFF for half the time.

# 4. Signal Analysis and Integrity

Advanced fundamentals involve how we view and protect signals:

- **Time vs. Frequency Domain:** We typically view signals in the **Time Domain** (amplitude vs. time) using an oscilloscope. However, we can use a **Fast Fourier Transform (FFT)** algorithm to view them in the **Frequency Domain** (amplitude vs. frequency) to see the individual frequency components present.
- **Modulation:** The process of encoding information into a carrier wave by changing its properties, such as its amplitude, frequency, or phase.
- **Signal Integrity:** Techniques used to protect signals from noise, including **Shielding** (using metal enclosures or shielded cables) and **Filtering**.
    - **Low-pass filters** allow slow signals to pass while blocking high-frequency noise.
    - **High-pass filters** remove low-frequency drift or DC components.
    - **Decoupling capacitors** are used near integrated circuits to filter out power supply noise.