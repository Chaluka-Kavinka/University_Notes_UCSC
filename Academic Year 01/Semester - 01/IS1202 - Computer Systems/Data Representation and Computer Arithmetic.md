> [!Info]
> Topic 01 of this course is **Data Representation and Computer Arithmetic**. This section provides the foundational knowledge of how information is stored, categorized, and processed within a computer system.

# 1. History of Computer Systems

The evolution of computing is categorized into generations based on the technological milestones achieved over time.

- **Generation Zero (1642–1940):** Characterized by **mechanical calculating machines** like Wilhelm Schickard's Calculating Clock (1623), Blaise Pascal’s Pascaline (1642), and Charles Babbage's Difference Engine (1819).
- **First Generation (1940–1956):** Used **vacuum tubes** for circuitry and magnetic drums for memory. These machines, like the **ENIAC** (first general-purpose) and **UNIVAC** (first commercial), were massive, expensive, and generated significant heat.
- **Second Generation (1956–1963):** **Transistors** replaced vacuum tubes, making computers smaller, faster, and more reliable. This era also saw the development of high-level languages like COBOL and FORTRAN.
- **Third Generation (1964–1971):** Marked by the **Integrated Circuit (IC)**. Users began interacting via keyboards and monitors instead of punched cards, and operating systems allowed for multitasking.
- **Fourth Generation (1971–Present):** Defined by **Microprocessors** and **VLSI** (Very Large Scale Integration), which placed thousands of circuits on a single silicon chip. This led to the development of personal computers, GUIs, and handheld devices.
- **Fifth Generation (Present & Beyond):** Focuses on **Artificial Intelligence (AI)** and **ULSI** technology, aiming for machines that process natural language and utilize parallel processing.
- **Sixth Generation (Future):** Anticipated signposts include **nanotechnology**, **quantum bits (qubits)**, and advanced robotics to boost processing speed and multitasking capabilities.

# 2. Data Representation Fundamentals

Computers represent data in two main categories:

- **Quantitative Data:** Can be counted or measured (integers and non-integers, signed or unsigned).
- **Qualitative Data:** Descriptive and conceptual (categorized by traits and characteristics).

## Units of Measurement:

- **Bit:** The smallest unit of data, holding a value of 0 or 1.
- **Byte:** A group of **8 consecutive bits**, capable of storing a single character.
- **Word:** The natural unit of data handled by a specific processor design (e.g., a 32-bit or 64-bit word).
- **Storage Hierarchy:** 1024 Bytes = 1 Kilobyte (KB); 1024 KB = 1 Megabyte (MB); 1024 MB = 1 Gigabyte (GB).

# 3. Numbering Systems and Character Coding

Computers use several numbering systems based on different alphabets: **Decimal** (0-9), **Binary** (0-1), **Octal** (0-7), and **Hexadecimal** (0-9, A-F).

## Character Representation:

- **ASCII:** Uses 7-bit patterns to represent 128 characters, including English letters, digits, and special symbols.
- **Unicode (UTF-16):** A 16-bit system capable of encoding characters for most languages globally (over 65,000 characters). Most modern systems now use Unicode by default.

# 4. Computer Arithmetic

Computers perform arithmetic on binary numbers following rules similar to decimal systems but restricted to two digits.

- **Binary Addition:** 1+1=10 (results in 0 with a carry of 1).
- **Binary Subtraction:** 0−1=1 with a borrow from the next column.
- **Binary Multiplication & Division:** Follow the same long-form processes used in decimal arithmetic.

# 5. Signed and Unsigned Number Representation

- **Unsigned:** Represents only non-negative integers (range for n bits is 0 to 2n−1).
- **Signed:** Uses the **Most Significant Bit (MSB)** as a sign bit (0 for positive, 1 for negative).
    - **Sign-Magnitude:** Simple but has problems, such as having two representations for zero (+0 and −0) and complicated arithmetic.
    - **One’s Complement:** Negative numbers are formed by flipping all bits of the positive equivalent.
    - **Two’s Complement:** The standard modern method. A negative number is formed by flipping all bits and **adding 1 to the LSB**. Benefits include a single representation of zero and simplified arithmetic circuitry.

# 6. Floating-Point Representation (IEEE 754)

To represent fractions (non-integers), computers use a format consisting of a **Sign bit**, a **Biased Exponent**, and a **Significand (Mantissa)**.

- **IEEE Standard 754:** Defines standard formats to ensure program portability across different processors.
    - **Single-Precision (32-bit):** 1 sign bit, 8 exponent bits (with a bias of 127), and 23 significand bits.
    - **Double-Precision (64-bit):** 1 sign bit, 11 exponent bits, and 52 significand bits.
- **Normalization:** A process where the radix point is shifted so the most significant digit of the significand is non-zero (always 1 in binary, which is often implicit and not stored).
- **Limitations:** Floating-point representations are only approximations of real numbers. This leads to issues like **Overflow** (number too large), **Underflow** (number too tiny), and **Round-off errors**.

---
# Lecture Notes
![[IS1202 Lecture 1.1.pdf]]
![[IS1202 Lecture 1.2.pdf]]
![[IS1202 Lecture 1.3.pdf]]
![[IS1202 Lecture 1.4.pdf]]