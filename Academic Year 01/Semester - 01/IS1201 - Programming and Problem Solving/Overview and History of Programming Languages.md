> [!Info]
> Topic 01 of the course provides an **Overview and History of Programming Languages**, serving as an introduction to how we communicate with computers and the fundamental logic behind software design.

---
# 1. Understanding Computers and Algorithms

At its most basic level, a computer is a machine that **performs calculations** at high speeds (billions per second) and **remembers results** using vast amounts of storage. However, computers only know what a programmer tells them.

**Computer Science** is fundamentally the study of **algorithms**. An algorithm is a formal, step-by-step procedure used to solve a specific problem. For an algorithm to be effective, it must:

- Produce a correct solution within a **finite amount of time**.
- Be **clear, precise, and unambiguous**.
- Be formatted in a way that allows for **elegant implementation** in a programming language.

# 2. Modeling Tools: Flow Charts

Algorithms are often modeled using **flow charts** before any code is written. Flow charts use standard symbols to represent different actions:

- **Ovals:** Start and Stop points.
- **Parallelograms:** Input and Output operations.
- **Rectangles:** Processes or calculations.
- **Diamonds:** Decisions (Selection logic).

The design of an elegant algorithm typically relies on three core **control structures**: **Sequence**, **Iteration** (looping), and **Selection** (decision-making).

# 3. Introduction to Scratch

Before moving to text-based coding, the course introduces **Scratch**, a high-level, **block-based visual programming language**. It uses an event-driven paradigm where "Scratchers" snap blocks together to create projects.

Practical problems solved in Scratch include:

- **Basic Output:** Printing a name on the screen.
- **User Input:** Reading a name from the user and responding with a greeting.
- **Decision Logic:** Reading a temperature and printing "Cool" if it is less than 30, or "Hot" otherwise.
- **Looping:** Reading temperatures for five consecutive days and calculating the average.

# 4. Transitioning to C Programming

A **programming language** consists of words and symbols that allow humans to give instructions (like doing calculations or saving data) that a computer can understand. These languages have evolved through different **generations**, starting from **Machine Language (1GL)**.

## The Structure of a C Program

Every C program must contain a **main()** **function**, as this is where code execution begins. A simple "Hello World" program looks like this:

- **Preprocessor Directive:** `#include <stdio.h>` tells the compiler to include the standard input-output library so functions like `printf()` can be used.
- **The Body:** The code is enclosed in **curly braces** **{ }**.
- **Statements:** Each statement (like `printf`) must end with a **semicolon (;)**.
- **Return Statement:** `return 0;` is used to end the program; while not strictly mandatory, it is considered best practice.

## The Compilation Process

C is a compiled language, meaning source code must be transformed into an executable file. The steps are:

1. **Source Code:** The code you write.
2. **Preprocessor:** Processes directives (lines starting with `#`) to create **Expanded Code**.
3. **Compiler:** Translates expanded code into **Assemble Code**.
4. **Assembler:** Converts assemble code into **Object Code**.
5. **Linker:** Combines object code with library files to create the **Final Executable** (e.g., `a.exe` in Windows).

To compile a file named `hello.c` using the GCC compiler, you would use the command `> gcc hello.c`.

# 5. Best Practices: Comments

As programs become more complex, they become harder to read. To maintain clarity, programmers use **comments**—notes written in natural language to explain what the code is doing. In C, these are created using **//** for single-line comments or **/* ... */** for multi-line blocks.

---
# Lecture Notes
![[IS1201 - Introduction.pdf]]