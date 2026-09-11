This topic details **Compile-Time Polymorphism**, where C++ allows functions and operators to have multiple meanings depending on the context of their use.

# 1. Function Overloading

Function overloading allows multiple functions in the same scope to share the **same name** but have **different parameter lists**.

- **Function Signature:** The compiler distinguishes between overloaded functions using their signatures, which include:
    1. Function name.
    2. Number of parameters.
    3. Types of parameters.
    4. Order of parameters.
- **Resolution Rules:** When a function is called, the compiler selects the "best match" using these priorities:
    1. **Exact Match:** The arguments match the parameters perfectly.
    2. **Standard Promotions:** e.g., `char` to `int` or `float` to `double`.
    3. **Standard Conversions:** e.g., `int` to `float`.
    4. **User-Defined Conversions**.
- **Overloading Restrictions:**
    - Functions **cannot** be overloaded if they differ only by their **return type** or **parameter names**.
    - **Ambiguity:** Errors occur if the compiler cannot choose between versions, often caused by default arguments or implicit type conversions (e.g., passing an `int` when versions for `float` and `double` both exist).

### C++ Example: Function Overloading
```cpp
#include <iostream>

// 1. Overloaded by parameter type
int multiply(int a, int b) {
    return a * b;
}

double multiply(double a, double b) {
    return a * b;
}

// 2. Overloaded by number of parameters
int multiply(int a, int b, int c) {
    return a * b * c;
}

int main() {
    std::cout << "multiply(3, 4):       " << multiply(3, 4) << "\n";       // Calls int version
    std::cout << "multiply(2.5, 4.0):   " << multiply(2.5, 4.0) << "\n";   // Calls double version
    std::cout << "multiply(2, 3, 4):    " << multiply(2, 3, 4) << "\n";    // Calls 3-parameter version
    return 0;
}
```

# 2. Operator Overloading

Operator overloading allows built-in C++ operators (like `+`, `-`, `++`) to work with **user-defined classes**.

- **The** **operator** **Keyword:** Overloading is achieved by defining an "operator function" using the syntax: `returnType operator symbol(parameters)`.
- **Rules and Restrictions:**
    - **Fixed Properties:** You cannot create new operators, change an operator's **precedence**, alter its **associativity**, or change the number of required operands.
    - **Non-Overloadable Operators:** The dot operator (`.`), scope resolution operator (`::`), ternary operator (`? :`), and `sizeof` cannot be overloaded.
    - **Default Overloading:** Operators like assignment (`=`), address-of (`&`), and comma (`,`) are overloaded by default by the compiler.
    - **No Default Arguments:** Operator functions cannot have default arguments.

# 3. Overloading Approaches

Operators can be overloaded either as **member functions** or **friend functions**. The choice depends on the specific operator and design needs.

|Feature|Member Function|Friend Function|
|---|---|---|
|**Unary Operators**|No parameters; the invoking object generates the call.|One parameter (the operand).|
|**Binary Operators**|One parameter; the left operand invokes the function, the right is passed as an argument.|Two parameters; both operands are passed as arguments (left first, right second).|
|**Chaining**|Often returns a reference to `*this` to allow operations like `a = b = c`.|Can return class references to allow chaining.|

## Special Cases:

- **Unary Prefix vs. Post-fix:** To distinguish between `++obj` (prefix) and `obj++` (postfix), the postfix version must include a **dummy** **int** **parameter** in its signature.
- **Assignment Operator (****=****):**
    - Used to copy values from one object to another **already existing object**.
    - **Must** be overloaded as a **member function**, never a friend.
    - By default, the compiler performs a **shallow (bit-wise) copy**, which can cause issues with classes using pointers.
- **I/O Operators** (<< and >>):
    - **Must** be overloaded as **friend functions** because their left operand is a stream object (like `cout` or `cin`) rather than your class object.

### C++ Example: Member and Friend Operator Overloading
```cpp
#include <iostream>
#include <cmath>

class Complex {
private:
    double real;
    double imag;

public:
    Complex(double r = 0.0, double i = 0.0) : real(r), imag(i) {}

    // 1. Binary Operator + (Member Function: Left operand invokes, right is argument)
    Complex operator+(const Complex& other) const {
        return Complex(this->real + other.real, this->imag + other.imag);
    }

    // 2. Unary Prefix Increment ++obj (Member Function)
    Complex& operator++() {
        ++real;
        ++imag;
        return *this; // Returns reference to updated object
    }

    // 3. Unary Postfix Increment obj++ (Dummy int parameter distinguishes postfix)
    Complex operator++(int) {
        Complex temp = *this; // Save original state
        ++real;
        ++imag;
        return temp;          // Returns original state by value
    }

    // 4. Assignment Operator = (MUST be a member function)
    Complex& operator=(const Complex& other) {
        if (this != &other) { // Protect against self-assignment
            this->real = other.real;
            this->imag = other.imag;
        }
        return *this; // Allows assignment chaining: a = b = c
    }

    // 5. Stream Insertion Operator << (MUST be a friend function)
    friend std::ostream& operator<<(std::ostream& os, const Complex& c) {
        os << c.real << (c.imag >= 0 ? " + " : " - ") << std::abs(c.imag) << "i";
        return os; // Allows stream chaining: cout << c1 << c2;
    }
};

int main() {
    Complex c1(2.5, 3.5);
    Complex c2(1.5, 2.0);

    // Binary +
    Complex sum = c1 + c2; // Equivalent to: c1.operator+(c2)
    std::cout << "Sum: " << sum << "\n";

    // Unary Prefix vs Postfix
    Complex prefixResult = ++c1;  // Prefix: increments, then returns new value
    std::cout << "After ++c1: " << c1 << "\n";

    Complex postfixResult = c2++; // Postfix: returns old value, then increments
    std::cout << "Postfix returned: " << postfixResult << ", New c2: " << c2 << "\n";

    // Assignment chaining
    Complex c3;
    c3 = sum;
    std::cout << "Assigned c3: " << c3 << "\n";

    return 0;
}
```