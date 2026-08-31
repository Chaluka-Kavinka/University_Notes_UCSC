> [!Info]
> Based on the organization we established earlier, **Topic 04** covers **Macros and the Preprocessor**, which are tools used to manipulate your source code before the actual compilation process begins.

---
# 1. What is a Macro?

In C, a macro is a fragment of code that is assigned a specific name. When the preprocessor encounters this name in your code, it **replaces** it with the defined code segment.

- **Definition:** Macros are created using the **#define** directive.
- **Purpose:** They are primarily used to define constants (like `PI`), create small **inline functions**, and simplify code that is used repeatedly.
- **Example:** You can use a macro to represent an algebraic expression, such as `#define f(n) (n/3.0 + 2)`, and then call it multiple times in your program as if it were a function.

# 2. How the Preprocessor Works

The preprocessor acts as an initial pass over your source code. Its workflow includes:

- **Macro Expansion:** Replacing all macro names with their assigned content.
- **File Inclusion:** Replacing `#include` directives with the actual content of the header files (like `<stdio.h>`).
- **Conditional Compilation:** Evaluating specific directives to include or exclude parts of the code based on conditions.

# 3. Conditional Compilation

Programmers use **conditional directives** to control which parts of a file are actually compiled. Common directives include **#if**, **#elif**, **#else**, **#endif**, **#ifdef**, and **#ifndef**.

- **Applications:** This is useful for writing code that must run differently on various operating systems (e.g., specific code for iOS vs. Android) or for excluding code from a program while keeping it as a reference for the future.
- **Special Operator:** The **#defined** operator is often used within `#if` statements to check if a specific macro exists.

# 4. Predefined Macros and Operators

C includes several built-in **predefined macros** that provide information about the current state of the program:

- **__DATE__**: A string containing the current date.
- **__TIME__**: A string containing the current time.
- **__FILE__**: A string containing the name of the current file.
- **__LINE__**: An integer representing the current line number in the source file.

Additionally, the preprocessor uses two special operators:

- **#** **(Stringizing):** Converts a macro parameter into a string literal.
- **##** **(Token Pasting):** Joins two separate tokens together during macro expansion.

---
# Lecture Notes
![[IS1201 - Preprocesser and Macro.pdf]]