- **Course Code** : IS 2207
- **Course Name** : Electronics and Physical Computing
- **Lecture** : Dr. Hiran Ekanayake

#Lesson-Plan 

This lesson is designed to provide computing undergraduates with a solid foundation in both the theoretical principles and practical applications of electronics and interactive hardware systems. Below is a detailed breakdown of the goal of this lesson and its intended learning outcomes, drawing from your lecture notes.


> [!tip] The Goal of Studying This Lesson
> The primary objective of this course is to bridge the gap between the digital world of software and the physical world we inhabit. Rather than focusing solely on abstract code, this lesson teaches you how to create **interactive systems** that use hardware and software to **sense** environmental data and **respond** with physical actions.

By studying this course, you aim to:

- **Understand the "Sense-Process-Act" Loop:** Learn how a system uses sensors to gather information, a microcontroller (like Arduino or ESP32) to process that information, and actuators to perform a physical task.
- **Master the Fundamentals of Electronics:** Gain the knowledge required to design, build, and troubleshoot electronic circuits safely and effectively.
- **Develop IoT and Embedded Systems Skills:** Learn to create "smart" devices that are connected to networks and the cloud to collect and exchange data.
---
# Intended Learning Outcomes (ILOs)

The curriculum is structured so that by the end of the course, you will be able to perform several key technical tasks across different domains of electronics and computing:

1. Mastery of Electronic Principles

- **Explain Fundamental Concepts:** You will be able to describe and apply core concepts such as **voltage, current, resistance, power, and impedance**.
- **Apply Circuit Laws:** You will learn to use essential laws like **Ohm’s Law, Kirchhoff’s Current Law (KCL), and Kirchhoff’s Voltage Law (KVL)** to analyze and design circuits.
- **Component Identification:** You will be able to differentiate between **passive components** (resistors, capacitors, inductors) and **active components** (diodes, transistors, ICs), understanding their specific roles within a larger system.

2. Digital Logic and Systems

- **Logical Design:** You will apply **Boolean algebra and digital logic** to build systems.
- **Combinational and Sequential Systems:** You will learn to implement **combinational circuits** (like adders and multiplexers) and **sequential circuits** (like flip-flops and counters), which form the basis of modern computing hardware.

3. Microcontroller Programming and Interfacing

- **Hardware Programming:** You will gain proficiency in programming microcontrollers such as the **Arduino Uno R3 and the ESP32**.
- **Input/Output Control:** You will learn to write code that reads data from various **sensors** (temperature, light, motion) and controls **actuators** (motors, displays, buzzers).

4. Communication and Integration

- **Protocol Implementation:** You will learn to integrate various communication protocols, both **wired** (UART, I²C, SPI) and **wireless** (Wi-Fi, Bluetooth/BLE, MQTT), to allow devices to talk to each other and the cloud.
- **IoT Architecture:** You will understand the **seven-layer IoT reference model**, moving data from physical sensors to business-level decision-making.

5. Practical Prototyping and Safety

- **Testing and Simulation:** You will become proficient in using laboratory instruments like **multimeters and oscilloscopes**, as well as software simulation tools (such as LTspice or Proteus), to evaluate circuit performance before building them physically.
- **Real-World Application:** You will design and prototype complete **physical computing systems** that integrate hardware and software for practical, real-world uses.
- **Safety and Best Practices:** You will be able to assess safety requirements and demonstrate professional best practices in electronics experimentation to prevent damage to components or injury to yourself.

# Core Context: Why This Matters

This course places you at the intersection of several rapidly growing fields:

- **Embedded Systems:** You are learning to create the "brains" inside everyday objects like washing machines or automobiles.
- **Internet of Things (IoT):** You are building the infrastructure for a world where billions of devices are connected to the internet.
- **Edge Computing:** You are learning to process data locally at the source (on the microcontroller) rather than relying solely on centralized cloud servers, which is essential for real-time responsiveness.

By completing this course, you transition from being a software-only developer to a **creator of physical systems**, capable of building everything from a smart irrigation system to advanced industrial automation tools.

---

# Topic Covered

1. [[Electronic Fundamentals]]

This section covers the basic physics and mathematical tools needed to analyze circuits.

- **Core Quantities:** Voltage, Current, Resistance, Power, and Impedance.
- **Circuit Laws & Theorems:** Ohm’s Law, Kirchhoff’s Voltage Law (KVL), Kirchhoff’s Current Law (KCL), and Thevenin & Norton Theorems.
- **Signal Properties:** Differentiating between **Analog and Digital signals**, and understanding properties like Frequency, Amplitude, Phase, and Duty Cycle.
- **Advanced Concepts:** Modulation techniques (ASK, FSK, PSK), signal filters, noise reduction, and signal integrity.
- **AC/DC Systems:** DC and AC circuit analysis, RMS (Root Mean Square) values, and Power Factor.

2. [[Electronic Components]]

You will learn to identify and use the physical building blocks of electronic systems.

- **Passive Components:** Resistors, Capacitors, Inductors, Transformers, Relays, and Fuses.
- **Active Components:** Diodes, Thyristors, and Transistors (specifically BJT and MOSFET).
- **Operational Amplifiers (Op-Amps):** Their various modes and practical applications in signal processing.
- **Power Systems:** Understanding power supplies, voltage regulators, batteries, and DC-DC converters.

3. [[Digital Electronics]]

This area bridges electronics with computer logic.

- **Fundamentals:** Logic states, logic gates (AND, OR, NOT, NAND, NOR, XOR, XNOR), and different IC families like TTL and CMOS.
- **Logic Design:** Boolean Algebra, simplification techniques, and Karnaugh Maps.
- **Combinational Circuits:** Complex logic systems like Adders, Multiplexers, Encoders, and Decoders.
- **Sequential Circuits:** Systems with "memory," including Flip-flops (S-R, J-K, D), Counters, and Finite State Machines (FSMs).
- **Specialized Logic:** Schmitt Triggers for noise minimization and Digital Buffers.

4. [[Sensors and Actuators]]

This topic focuses on how systems interact with the environment.

- **Sensing:** Interfacing with sensors for Temperature (e.g., DHT22), Light (LDR), Motion (PIR), Pressure, Distance (Ultrasonic HC-SR04), and Biosensors.
- **Acting:** Controlling physical outputs such as Motors (Servo, DC, Stepper), Solenoids, Buzzers, and Visual Displays (LCD, OLED, 7-Segment).
- **System Integration:** Calibration and signal conditioning for accurate data reading.

5. [[Physical Computing and IoT]]

The "brains" of the projects and how they communicate.

- **Core Concepts:** Embedded Systems, the Internet of Things (IoT), and Edge Computing.
- **Microcontrollers:** Architecture and families, focusing on **Arduino (AVR)** and **ESP32**.
- **Programming & Logic:** Programmable logic (FPGA basics) and hardware programming for I/O and PWM (Pulse Width Modulation).
- **Communication Protocols:** Learning how devices talk to each other via **Wired** (UART, SPI, I2C, USB) and **Wireless** (Wi-Fi, Bluetooth/BLE, MQTT, LoRa) protocols.
- **Cloud Architecture:** Understanding the **Seven-Layer IoT Reference Model** and integrating with Cloud IoT platforms.

6. [[Practical Prototyping and Safety]]

The hands-on skills required to build real devices.

- **Safety:** Professional best practices and safety requirements in experimentation.
- **Measurement Tools:** Proficient use of Multimeters, Oscilloscopes, Function Generators, and Power Supply Units (PSU).
- **Prototyping Methods:** Breadboarding, soldering, and PCB (Printed Circuit Board) design.
- **EDA & Simulation:** Using software like **LTspice, KiCad, Proteus, or Fritzing** to simulate and design circuits before building them.

---

# 📄 IS2207 Course Descriptor

![[IS2207 - Course Descriptor.pdf]]