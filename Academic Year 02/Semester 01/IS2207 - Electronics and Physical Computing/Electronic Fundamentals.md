This topic explores the basic physics of electronics, the core quantities used to measure electricity, the essential laws for circuit analysis, and the properties of the signals that drive physical computing systems.

# 1. Core Electrical Quantities

Electronics is defined as the study and use of devices that operate by controlling the flow of electrons or other charge carriers. To understand these systems, we must first master the fundamental quantities:

- **Charge (Q):** The fundamental property of matter responsible for electric phenomena, calculated as $Q = I \times t$. The unit of charge is the **Coulomb (C)**. A single electron carries a charge of approximately $-1.6 \times 10^{-19} \text{ C}$.
- **Current (I):** The rate of flow of electric charge through a conductor. It is calculated as $I = \frac{Q}{t}$ and measured in **Amperes (A)**. Conventional current flow is considered to move from positive to negative, while actual electron flow moves from negative to positive.
- **Voltage (V):** The potential difference between two points, defined as the work done per unit charge ($V = \frac{W}{Q}$), often described as the "push" or pressure that drives current through a circuit. The unit is the **Volt (V)**.
- **Resistance (R):** The opposition to the flow of current in a material. It is measured in **Ohms ($\Omega$)**. For a uniform conductor, $R = \rho \frac{L}{A}$, where $\rho$ is resistivity, $L$ is conductor length, and $A$ is cross-sectional area.
- **Power (P) & Energy (E):** The rate at which electrical energy is consumed or generated.
  - Power: $P = VI = I^2 R = \frac{V^2}{R}$ measured in **Watts (W)**.
  - Energy: $E = P \times t = V I t$ measured in **Joules (J)** or **Watt-hours (Wh)**.
- **Impedance (Z) & Reactance (X):** The total opposition to alternating current (AC) combining both resistance ($R$) and reactance ($X$). Represented in complex form as $Z = R + jX$ and measured in **Ohms ($\Omega$)**.
  - **Capacitive Reactance ($X_C$):** Opposition from a capacitor, calculated as $X_C = \frac{1}{2\pi f C} = \frac{1}{\omega C}$.
  - **Inductive Reactance ($X_L$):** Opposition from an inductor, calculated as $X_L = 2\pi f L = \omega L$.
  - **Impedance Magnitude ($|Z|$):** For a series RLC circuit, $|Z| = \sqrt{R^2 + (X_L - X_C)^2}$ with phase angle $\theta = \arctan\left(\frac{X_L - X_C}{R}\right)$.

# 2. Essential Circuit Laws, Rules, and Theorems

These mathematical tools allow us to analyze how energy and current move through a circuit:

- **Ohm’s Law:** Defines the linear relationship between voltage, current, and resistance:
  $$V = I \times R \quad \implies \quad I = \frac{V}{R}, \quad R = \frac{V}{I}$$
- **Kirchhoff’s Current Law (KCL):** States that the sum of all currents entering a junction (node) must equal the sum of currents leaving it ($\sum I_{\text{in}} = \sum I_{\text{out}}$), meaning the algebraic sum of currents at a node is zero ($\sum I = 0$).
- **Kirchhoff’s Voltage Law (KVL):** States that the algebraic sum of all electrical potential differences (voltages) around any closed loop or mesh in a circuit must equal zero ($\sum V = 0$).
- **Voltage Divider Rule:** Calculates the voltage drop across a specific resistor in a series chain. Crucial for analog sensor interfaces:
  $$V_{\text{out}} = V_{\text{in}} \times \left(\frac{R_2}{R_1 + R_2}\right)$$
- **Current Divider Rule:** Calculates the branch current in a parallel circuit:
  $$I_1 = I_{\text{total}} \times \left(\frac{R_2}{R_1 + R_2}\right)$$
- **Equivalent Series & Parallel Combinations:**
  - **Resistors:**
    - Series: $R_{\text{eq}} = R_1 + R_2 + \dots + R_n$
    - Parallel: $\frac{1}{R_{\text{eq}}} = \frac{1}{R_1} + \frac{1}{R_2} + \dots + \frac{1}{R_n} \quad \left(\text{for two resistors: } R_{\text{eq}} = \frac{R_1 R_2}{R_1 + R_2}\right)$
  - **Capacitors:**
    - Parallel: $C_{\text{eq}} = C_1 + C_2 + \dots + C_n$
    - Series: $\frac{1}{C_{\text{eq}}} = \frac{1}{C_1} + \frac{1}{C_2} + \dots + \frac{1}{C_n}$
- **Thevenin’s Theorem:** States that any linear two-terminal circuit can be simplified into an equivalent circuit consisting of an open-circuit voltage source ($V_{\text{th}}$) in series with an equivalent resistance ($R_{\text{th}}$).
- **Norton’s Theorem:** States that any linear two-terminal circuit can be replaced by an equivalent short-circuit current source ($I_{\text{n}}$) in parallel with an equivalent resistance ($R_{\text{n}} = R_{\text{th}}$).

# 3. Signal Properties & Sinusoidal Waveform Analysis

In physical computing, we use signals to represent information. Signals are generally classified into two types: **Analog** (continuous waves) and **Digital** (discrete steps or 0s and 1s).

- **Sinusoidal Waveform Equation:** A mathematical model representing a continuous AC sinusoidal signal over time:
  $$v(t) = A \sin(2\pi f t + \phi) = V_m \sin(\omega t + \phi)$$
  - **$v(t)$:** Instantaneous voltage at time $t$ (Volts, V).
  - **$A$ (or $V_m$ / $V_{\text{peak}}$):** Peak Amplitude — the maximum displacement of the waveform from the zero reference level (Volts, V).
  - **$f$:** Signal Frequency in Hertz (Hz), representing the number of full wave cycles per second.
  - **$\omega$:** Angular Frequency in radians per second ($\text{rad/s}$), defined as $\omega = 2\pi f = \frac{2\pi}{T}$.
  - **$t$:** Time variable in seconds (s).
  - **$\phi$ (Phi):** Phase Angle (in radians or degrees), representing the time shift of the waveform relative to the reference origin ($t = 0$).
- **Period ($T$) & Frequency ($f$):**
  - Period ($T$) is the duration of one complete wave cycle (seconds, s).
  - Frequency ($f$) is the reciprocal of period: $f = \frac{1}{T}$ (Hertz, Hz).
- **Voltage Magnitudes ($V_{\text{peak}}$, $V_{\text{p-p}}$, $V_{\text{rms}}$, $V_{\text{avg}}$):**
  - **Peak-to-Peak Voltage ($V_{\text{p-p}}$):** The difference between the maximum positive peak and minimum negative peak:
    $$V_{\text{p-p}} = 2 \times V_{\text{peak}}$$
  - **RMS (Root Mean Square) Voltage ($V_{\text{rms}}$):** The effective DC-equivalent voltage that delivers equal average power to a resistive load. For a pure sine wave:
    $$V_{\text{rms}} = \frac{V_{\text{peak}}}{\sqrt{2}} \approx 0.707 \times V_{\text{peak}} \quad \implies \quad V_{\text{peak}} = \sqrt{2} \times V_{\text{rms}} \approx 1.414 \times V_{\text{rms}}$$
    *(Example: Standard 230V AC household supply is an RMS value; its peak voltage is $V_{\text{peak}} = 230 \times \sqrt{2} \approx 325\text{V}$).*
  - **Average Voltage ($V_{\text{avg}}$):** The average amplitude calculated over a half sinusoidal cycle (the average over a complete cycle of pure AC is zero):
    $$V_{\text{avg}} = \frac{2 V_{\text{peak}}}{\pi} \approx 0.637 \times V_{\text{peak}}$$
- **Duty Cycle:** For pulse-width modulated (PWM) or digital pulse waves, the percentage of time the signal is in the "HIGH" (ON) state during one full period ($T$):
  $$\text{Duty Cycle (\%)} = \left(\frac{t_{\text{ON}}}{T}\right) \times 100\%$$
  - *Example:* A 50% duty cycle means the signal is HIGH for half the period ($t_{\text{ON}} = t_{\text{OFF}} = 0.5 T$).

# 4. Signal Analysis and Integrity

Advanced fundamentals involve how we view, process, and protect signals:

- **Time vs. Frequency Domain:**
  - **Time Domain:** Displays amplitude vs. time, typically observed using an oscilloscope.
  - **Frequency Domain:** Displays amplitude vs. frequency, analyzed using a **Fast Fourier Transform (FFT)** to break signals down into fundamental frequencies and harmonics.
- **Modulation:** Encoding information onto a carrier wave by modifying properties such as amplitude (AM), frequency (FM), or phase (PM).
- **Signal Filtering & Cutoff Frequency ($f_c$):** Filters block or pass specific frequency ranges. The cutoff frequency ($f_c$, or $-3\text{ dB}$ point) is where output signal power drops to half (voltage drops to $\frac{1}{\sqrt{2}} \approx 70.7\%$ of maximum):
  - **RC Filter Cutoff Frequency:**
    $$f_c = \frac{1}{2\pi R C}$$
  - **RL Filter Cutoff Frequency:**
    $$f_c = \frac{R}{2\pi L}$$
  - **Low-pass filters:** Allow frequencies below $f_c$ to pass while attenuating high-frequency noise.
  - **High-pass filters:** Allow frequencies above $f_c$ to pass while blocking low-frequency drift or DC offsets.
  - **Decoupling capacitors:** Bypass high-frequency power supply noise to ground near integrated circuit power pins.