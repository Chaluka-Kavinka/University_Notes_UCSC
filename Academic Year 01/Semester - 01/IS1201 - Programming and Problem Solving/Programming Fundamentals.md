> [!Info]
> Topic 02, **Programming Fundamentals**, is a core component of the course scheduled to be covered over three weeks. It transitions from algorithmic logic into the actual syntax and building blocks of the C programming language.
> 

---
# 1. Variables, Constants, and Identifiers

- **Identifiers:** These are unique names given to entities like variables and functions. C is **case-sensitive**, meaning `money` and `Money` would be treated as different identifiers.
- **Variables:** A variable acts as a container or storage area for data. Each variable name is a symbolic representation of a specific memory location.
- **Constants:** Unlike variables, the value of a constant cannot be changed during program execution.
- **Literals:** These are fixed values used directly in the code, such as the number `73` or the string `"Hello"`.

# 2. Primitive Data Types and Size Qualifiers

C uses different data types to determine what kind of data a variable can hold and how much memory it requires.

- **Common Types:** `int` (integers), `float` (single-precision floating point), `double` (double-precision floating point), and `char` (single characters).
- **Size Qualifiers:** Keywords like `long` and `short` alter the size of basic types. For example, a standard `int` is typically 4 bytes, but using `short int` can reduce it to 2 bytes.
- **sizeof()** **Operator:** This built-in function is used to calculate the exact size (in bytes) that a data type or variable occupies in memory.

# 3. Input and Output (I/O) Operations

Standard I/O tasks are performed using built-in library functions from the `<stdio.h>` header.

- **printf()****:** Sends formatted output to the screen. It uses **format specifiers** like `%d` for integers and `%f` for floats to display variable values.
- **scanf()****:** Reads formatted input from the keyboard and stores it in specified variables. It requires the address-of operator (`&`) before the variable name (e.g., `&age`) to tell the program where to store the input.

# 4. Operators and Expressions

Operators are symbols that trigger specific mathematical or logical manipulations.

- **Arithmetic:** Perform basic math: `+`, `-`, `*`, `/`, and `%` (modulo, which returns the remainder).
- **Increment/Decrement:** `++` and `--` are unary operators that increase or decrease a value by exactly 1.
- **Assignment:** Used to assign values to variables. Compound assignments like `+=` (e.g., `a += b` is the same as `a = a + b`) simplify code.
- **Relational:** Check relationships between operands (e.g., `==`, `>`, `<`, `!=`) and return `1` for true or `0` for false.
- **Logical:** Used for decision-making logic: `&&` (AND), `||` (OR), and `!` (NOT).
- **Ternary (****?:****):** A shortcut for `if...else` that works on three operands to evaluate a condition and return one of two values.

# 5. Expressions

An expression is a combination of operators, constants, and variables that are evaluated to produce a single value. For example, a program might take a temperature in Celsius from a user and use an expression like `ºF = ºC * 1.8 + 32.00` to calculate the Fahrenheit equivalent.

---
# Lecture Notes
![[IS1201 - C Programming.pdf]]
![[IS1201 - Data Types.pdf]]
![[IS1201 - Operators.pdf]]