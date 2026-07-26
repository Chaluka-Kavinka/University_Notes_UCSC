> [!Info]
> Topic 02, **Basic Logic Circuit Design**, provides the mathematical and physical foundations for building computer hardware, moving from abstract logic to actual circuit components.

# 1. Boolean Algebra and Logic Operations

Boolean Algebra, introduced by George Boole in 1854, is the branch of mathematics where variables have only two states: **1 (True)** or **0 (False)**. These states are manipulated using specific logic operators:

- **AND $(A⋅B)$:** The output is 1 only if both inputs are 1.
- **OR $(A+B)$:** The output is 1 if at least one input is 1.
- **NOT $(Aˉ or A′)$:** This is an inverter; it flips 1 to 0 and 0 to 1.
- **XOR $(A⊕B)$:** The output is 1 only if the inputs are different.
- **NAND and NOR:** These are the negated versions of AND and OR respectively.
- **XNOR $(A⊙B)$:** The output is 1 only if the inputs are the same.
- **Buffer:** Passes the input unchanged, often used to introduce propagation delay.

These operations are physically implemented using **logic gates** (hardware pieces built from transistors, resistors, and diodes) which are manufactured into **Integrated Circuits (ICs)**.

# 2. Expressing Boolean Functions

A Boolean function consists of binary variables and logic operations and can be expressed in two primary ways:

- **Truth Tables:** Lists all 2n possible input combinations (where n is the number of variables) and the resulting output.
- **Canonical Forms:**
    - **Sum of Minterms (SoM):** A logical OR of "minterms," where each minterm is an AND combination of all variables in the function.
    - **Product of Maxterms (PoM):** A logical AND of "maxterms," where each maxterm is an OR combination of all variables.
- **Standard Forms:** Similar to canonical forms, but terms (Sum of Products or Product of Sums) do not need to contain every variable in the function.

# 3. Simplification Techniques

Simplifying Boolean expressions is critical for reducing the number of gates required, which improves efficiency and lowers cost.

- **Boolean Laws:** Expressions are manipulated using axioms such as the **Annulment Law** $(A⋅0=0)$, **Identity Law** $(A+0=A)$, **Complement Law** $(A⋅Aˉ=0)$, and **Distributive Law**.
- **De Morgan’s Theorem:** A vital rule for simplification stating that $A⋅B=Aˉ+Bˉ$ and $A+B​=Aˉ⋅Bˉ$.
- **Karnaugh Maps (K-Maps):** A visual technique for gate-level minimization. A truth table is mapped onto a grid of cells $(2^n)$. By grouping 1s (for Sum of Products) or 0s (for Product of Sums) in groups of $2^k$, variables that change state within a group are eliminated, leaving the simplest expression. K-Maps also allow for the use of **Don’t Care conditions (X)**—input patterns where the output is unspecified—to create larger, more efficient groups.

# 4. Combinational Logic Circuits

In these circuits, the **output depends only on the current inputs**. Standard combinational units include:

- **Adders:** The **Half Adder** adds two bits to produce a Sum and a Carry Out. The **Full Adder** can handle a carry input from a previous stage.
- **Subtractors:** Units like the Half and Full Subtractor perform binary subtraction.
- **Decoders:** These interpret an n-bit code and activate one of 2n unique output channels. They can be used as circuit builders to implement any Boolean function.
- **Encoders:** Perform the inverse of a decoder, converting an active input into a binary code.
- **Multiplexers (MUX):** Acts as a switch that directs one of many input channels to a single output based on control lines.

# 5. Sequential Logic Circuits

Unlike combinational circuits, sequential circuits have **memory**; their output depends on both current inputs and **previous states**.

- **Asynchronous:** State changes immediately when inputs change, but can be unstable.
- **Synchronous:** State changes occur only at discrete time intervals, typically triggered by a **clock signal**.
- **Storage Elements:**
    - **Latches:** Level-sensitive asynchronous elements that serve as building blocks for flip-flops.
    - **Flip-Flops:** Edge-sensitive storage elements that store one bit of information and are triggered by clock pulses.
- **Counters:** Sets of flip-flops that produce a sequence of states (e.g., Ripple Counters or Synchronous Counters).

# 6. Universal Gates

**NAND** and **NOR** gates are known as **Universal Gates** because either one can be used to implement any other logic operation (AND, OR, NOT). Using a single gate type is often preferred in manufacturing to reduce costs and avoid unused gates on ICs.

---
# Lecture Notes
![[IS1202 Lecture 2.1.pdf]]
![[IS1202 Lecture 2.2.pdf]]
![[IS1202 Lecture 2.3.pdf]]
![[IS1202 Lecture 2.4.pdf]]
![[IS1202 Lecture 2.5.pdf]]