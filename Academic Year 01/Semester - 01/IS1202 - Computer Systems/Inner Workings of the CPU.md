> [!Info]
> Topic 03, **Inner Workings of the CPU**, explores the architecture, components, and operational cycles of the Central Processing Unit, which is considered the "brain" of the computer.

# 1. Computer Architecture and the von Neumann Model

The design of a computer system, known as its architecture, encompasses hardware organization and its interaction with software.

- **The von Neumann Architecture:** Proposed by John von Neumann in 1945, this model is the foundation of modern computers. Its key characteristics include:
    - **Three Hardware Systems:** A CPU, a main memory system, and an Input/Output (I/O) system.
    - **Stored-Program Concept:** Both data and instructions are stored in a single address space in memory, allowing programs to be modified without physically rewiring hardware.
    - **Sequential Processing:** Instructions are processed one after another.
    - **The von Neumann Bottleneck:** A single data path exists between the CPU and memory, which can limit performance.

# 2. Key CPU Components

The CPU is divided into two main conceptual parts: the **Control Unit** and the **Execution Unit**.

- **Control Unit (CU):** Manages the flow of data and instructions. It fetches instructions from memory, decodes them, and determines the appropriate operations for the ALU.
- **Arithmetic Logic Unit (ALU):** Performs the actual mathematical and logical operations (like addition, AND, OR) specified by the instructions on binary numbers.
- **Registers:** High-speed storage locations located on the CPU for immediate data access. Key registers include:
    - **Program Counter (PC):** Contains the address of the next instruction to be executed.
    - **Memory Address Register (MAR):** Holds the memory address of the data or instruction the CPU needs to access.
    - **Memory Data Register (MDR):** Holds the data being transferred to or from memory.
    - **Accumulator (AC):** Stores intermediate arithmetic and logic results.
    - **Current Instruction Register (CIR/IR):** Contains the instruction currently being processed.

# 3. Interconnection and Memory Access

The CPU communicates with other components through **Buses**, which are sets of lines for signal transmission.

- **Address Bus:** Used by the CPU to send the specific memory address it wants to read from or write to.
- **Data Bus:** Used to send and receive the actual data.
- **Control Bus:** Sends control signals, such as memory read/write commands or interrupt requests.
- **Memory Controller:** Manages the flow of data to and from main memory and coordinates communication between the CPU and memory modules.

# 4. The Machine Cycle (Fetch-Decode-Execute)

All general-purpose computers follow a repeated cycle to process instructions:

1. **Fetch:** The CPU copies the address from the PC to the MAR, retrieves the instruction from that memory location into the IR, and increments the PC to point to the next instruction.
2. **Decode:** The Control Unit interprets the operation code (opcode) portion of the instruction in the IR.
3. **Execute:** The relevant circuitry is activated (often involving the ALU) to perform the specified operation.
4. **Store:** The result is placed in a register or main memory.

# 5. Instruction Set Architecture (ISA) and Addressing Modes

The **ISA** specifies the set of instructions a CPU can understand and their format.

- **Types of Instructions:** Include **Data Transfer** (LOAD/STORE), **Arithmetic/Logic** (ADD, XOR), and **Control Operations** (JUMP, HALT).
- **Addressing Modes:** These define how the CPU locates the operands (data) for an instruction.
    - **Immediate:** The operand value is included directly in the instruction (very fast but fixed).
    - **Direct:** The instruction contains the actual memory address of the operand.
    - **Indirect:** The instruction contains an address that points to another location where the effective address is stored.
    - **Register (Direct):** The operand is held in a specified register.
    - **Register Indirect:** A register holds the memory address of the operand.

# 6. CPU Performance and Pipe-lining

Several factors determine how quickly a CPU processes a program:

- **Clock Speed:** The number of pulses (ticks) generated per second, measured in Hertz (Hz). A 1GHz clock produces one billion pulses per second.
- **Cycles Per Instruction (CPI):** The average number of clock cycles required to execute one instruction.
- **Performance Calculation:** $$CPUTime = NumberofInstructions \times CPI \times ClockCycleTime$$.
- **Instruction Level Pipelining:** A technique where the FDE cycle is broken into smaller, independent stages (e.g., fetch, decode, execute) so that multiple instructions can be processed in parallel at different stages. This significantly increases throughput and provides a "speedup" over non-pipelined systems.

---
# Lecture Notes
![[IS1202 Lecture 3.1.pdf]]
![[IS1202 Lecture 3.2.pdf]]
![[IS1202 Lecture 3.3.pdf]]