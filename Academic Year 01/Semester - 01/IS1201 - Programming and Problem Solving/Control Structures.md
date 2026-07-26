> [!Info]
> Topic 03, **Control Structures**, focuses on how to manage the flow of execution in a C program through conditions and loops. This topic is typically covered over two weeks.

---
# 1. Selection Logic (Decision Making)

Selection structures allow a program to choose between different paths of execution based on specific conditions.

- **Simple Selection (if and if...else):** The `if` statement evaluates a test expression; if true, the code block is executed. The `if...else` variant provides an alternative path, executing one block if the condition is true and another if it is false.
- **The** **else if** **Ladder:** This is used to check multiple alternatives sequentially until a true condition is found.
- **Multiple Selection (switch):** If you are checking a **single variable** against many potential values, the `switch` statement is preferred over an `else if` ladder because it is often **faster and cleaner**. It uses `case` labels and a `default` block for when no matches are found.
- **Ternary Operator (?:):** This is a compact version of an `if...else` statement that works on **three operands**. It evaluates a condition and returns one of two values depending on whether the condition is true (1) or false (0).

# 2. Looping (Iteration)

Loops are used to repeat a specific block of code multiple times. C provides three primary types of loops:

- **for** **Loop:** Best used when the **number of iterations is known**. It includes an initialization statement, a test expression, and an update statement all in one line.
- **while** **Loop:** This evaluates the test expression _before_ executing the loop body. It continues repeating as long as the expression remains true.
- **do...while** **Loop:** Unlike the others, this loop executes its body **at least once** because the condition is checked _after_ the code block runs.

# 3. Jump Statements: Break and Continue

These statements allow you to further control the behavior of loops and switches:

- **break**: This statement **terminates the loop or switch** immediately when encountered, skipping all remaining code in that structure.
- **continue**: Rather than ending the loop, `continue` **skips the remaining statements** in the current iteration and jumps directly to the next cycle of the loop.

# 4. Practical Examples

- **Finding Factors:** You can use a `for` loop to check every number from 1 up to half of a given number to see if it divides evenly (using the modulo `%` operator).
- **Grading Systems:** An `else if` ladder or a `switch` statement can be used to assign letter grades (A, B, C, D, E) based on a numerical mark.
- **Filtering Numbers:** A `continue` statement can be used within a loop to print numbers divisible by 5 but skip those that are also divisible by 10.

---
# Lecture Notes
![[IS1201 - Conditions and Loops.pdf]]