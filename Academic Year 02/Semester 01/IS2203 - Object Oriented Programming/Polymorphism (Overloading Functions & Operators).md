**Polymorphism** means having "many forms". In C++, it is the ability of a message or function to be displayed in more than one form. The two primary ways we implement this in this module are through **Function Overloading** and **Operator Overloading**.

---
# 1. Function Overloading

Function overloading is a feature that allows two or more functions in the same scope to have the **same name** but **different parameters**.

- **Compiler Selection:** When a function is called, the compiler determines which version to use based on the argument list.
- **Rules for Overloading:** Overloaded functions must differ in their parameter lists, either by the **number of parameters** or the **types of parameters**.
- **Restrictions:** You **cannot** overload functions if they differ only by their return type.
- **Ambiguity:** Ambiguous situations can occur if the compiler cannot choose between functions, often due to implicit type conversions or default arguments.
# 2. Operator Overloading

While standard operators (like `+` or `++`) typically work with built-in data types (like `int`), C++ allows you to redefine them to work with **user-defined classes**.

- **The** **operator** **Keyword:** To overload an operator, you must define an operator function using the keyword `operator` followed by the symbol you wish to redefine.
- **Unary Operator Overloading:** These act on a **single operand** (e.g., `++`, `--`, and the unary `-`).
    - **Prefix vs. Post-fix:** To distinguish between prefix (e.g., `++obj`) and postfix (e.g., `obj++`), the postfix version includes a dummy `int` parameter.
- **Binary Operator Overloading:** These act on **two operands** (e.g., `+`, `-`, `>`, `==`).
# 3. Rules and Restrictions for Operator Overloading

Not every aspect of an operator can be changed, and some operators cannot be overloaded at all:

- **Non-over-loadable Operators:** You cannot overload the dot operator (`.`), the scope resolution operator (`::`), the ternary operator (`? :`), or the `sizeof` operator.
- **Fixed Properties:** You cannot create new operators, change an operator’s **precedence**, alter its **associativity**, or change the number of operands it requires.
- **Default Overloading:** Some operators, such as assignment (`=`) and address-of (`&`), are overloaded by default by the compiler.
# 4. Summary of Approaches

Polymorphism can be achieved using three main approaches in C++:

1. Overloading **unary** operators.
2. Overloading **binary** operators.
3. Overloading operators using **friend functions**.