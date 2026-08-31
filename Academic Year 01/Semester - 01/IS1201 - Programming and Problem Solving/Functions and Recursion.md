> [!Info]
> Topic 05, **Functions and Recursion**, is a vital part of modular programming, where you divide complex problems into smaller, manageable components to make your programs easier to understand and debug.

---
# 1. Introduction to Functions

A **function** is a block of code designed to perform a specific task. C programming utilizes two main types of functions:

- **Standard Library Functions:** These are built-in functions defined in header files (like `printf()` and `scanf()` in `<stdio.h>`) that handle common tasks such as I/O processing or mathematical computations.
- **User-Defined Functions:** These are custom blocks of code created by the programmer to solve specific problems.

# 2. Function Structure and Signatures

Every function is defined by its **signature**, which includes its **return type** (the type of data it sends back), the **function name**, and the **arguments** (inputs) it accepts.

- **Types of User-Defined Functions:** Functions can be categorized by whether they take arguments or return values (e.g., no arguments and no return value, or both arguments and a return value).
- **The Return Statement:** This terminates the execution of a function and transfers program control—and potentially a calculated value—back to the caller.

# 3. Passing Arguments: Value vs. Reference

There are two primary ways to pass data to a function in C:

- **Pass by Value:** The function receives a **copy** of the variable. Any changes made inside the function do not affect the original data in the calling code. This is C's default behavior.
- **Pass by Reference:** You pass the **memory address** of a variable using pointers. This allows the function to modify the actual original variable in the caller.

# 4. Recursion

**Recursion** is a technique where a function **calls itself** to solve a problem.

- **Mechanism:** A recursive function must have a **base case**—a specific condition that stops the recursion. Without it, the function will call itself infinitely, causing the program to never terminate.
- **Practical Examples:**
    - **Factorial:** Calculating n! by multiplying n by the factorial of (n−1) until reaching the base case of 1.
    - **Fibonacci Sequence:** A sequence where each number is the sum of the two preceding ones (0,1,1,2,3,5...). This is mathematically defined as `fib(n) = fib(n-1) + fib(n-2)`.
    - **Countdown:** A function that prints a number and then calls itself with a smaller number until it hits a base case (e.g., "Blast!!").

# 5. Why Use These Tools?

Functions allow for code reuse and better organization, while recursion provides an "elegant" way to implement solutions for mathematically defined problems that would otherwise require complex loops.

---
# Lecture Notes
![[IS1201 - Functions  Recursion.pdf]]