This topic covers how C++ handles situations where external functions need access to private class members and how the compiler manages assignments between different data types.

# 1. Friend Functions: Accessing the Inner Sanctum

A **friend function** is a function that is not a member of a class but is granted access to its **private and protected members**.

- **Why use Friend Functions?**
    - They allow external functions or other classes to interact with private data without making that data public, preserving **Data Hiding**.
    - They are essential for certain types of **operator overloading**, specifically when the left operand is not an object of the class (like `cout << obj`).
- **Syntax and Declaration:**
    - **Declaration:** Must be declared **inside** the class body using the `friend` keyword.
    - **Definition:** Defined **outside** the class like a normal function (without the `friend` keyword or the class name prefix).

## Operator Overloading via Friend Functions

| Operator Type | Member Function Approach                                              | Friend Function Approach                                   |
| ------------- | --------------------------------------------------------------------- | ---------------------------------------------------------- |
| **Unary**     | No parameters; invoking object generates the call.                    | **One parameter** (the operand itself).                    |
| **Binary**    | **One parameter**; left operand invokes, right is passed as argument. | **Two parameters**; both operands are passed as arguments. |

- **Mandatory Friend Overloading:** The **I/O operators (****<<** **and** **>>****)** must be overloaded as friend functions because their left operands are stream objects (`ostream` or `istream`) rather than the class object.
- **Mandatory Member Overloading:** The **assignment operator (****=****)** must always be overloaded as a member function, never as a friend.

### C++ Example: Friend Function Accessing Private Members
```cpp
#include <iostream>

class Box {
private:
    double width;

public:
    Box(double w) : width(w) {}

    // 1. Friend Function Declaration: inside class body
    friend void printWidth(const Box& b);
    friend double doubleWidth(const Box& b);
};

// 2. Friend Function Definition: outside class (no 'friend' keyword, no 'Box::' scope)
void printWidth(const Box& b) {
    // Directly accesses private member 'width'
    std::cout << "Box width: " << b.width << "\n";
}

double doubleWidth(const Box& b) {
    return b.width * 2.0;
}

int main() {
    Box box(15.5);
    printWidth(box);
    std::cout << "Doubled Width: " << doubleWidth(box) << "\n";
    return 0;
}
```

# 2. Data Conversion: Bridging Types

Data conversion occurs when a variable of one type is assigned to a variable of another type. While the compiler handles basic type assignments (like `int` to `float`) automatically, custom rules are needed for user-defined classes.

## A. Basic Types vs. User-Defined Types

- **Implicit Conversion:** Automatically performed by the compiler when types are compatible.
- **Explicit Conversion:** Performed by the programmer using **casting operators** (e.g., `static_cast`, `(int)var`).

## B. Conversion Categories

There are three main scenarios for complex data conversion:

1. **Basic Type to Class Type:**
    - Achieved using a **parameterized constructor** that takes a single argument of the basic type.
    - _Example:_ Assigning an `int` representing minutes to a `Time` class object.
2. **Class Type to Basic Type:**
    - Achieved using an **overloaded casting operator function** (also called a conversion function).
    - _Syntax:_ `operator typename() { ... }` (e.g., `operator int()`).
    - These functions have no return type and no arguments.
3. **Class Type to Class Type:**
    - Achieved either through a **constructor** in the destination class that accepts the source class as an argument, or by overloading the **assignment operator (****=****)** in the destination class.

### C++ Example: The Three Data Conversion Scenarios
```cpp
#include <iostream>

// -------------------------------------------------------------
// Scenario 1: Basic Type to Class Type
// Scenario 2: Class Type to Basic Type
// -------------------------------------------------------------
class Time {
private:
    int hours;
    int minutes;

public:
    Time() : hours(0), minutes(0) {}

    // 1. Basic Type (int total minutes) to Class Type via Constructor
    Time(int totalMinutes) {
        hours = totalMinutes / 60;
        minutes = totalMinutes % 60;
    }

    // 2. Class Type to Basic Type (int total minutes) via Casting Operator
    operator int() const {
        return (hours * 60) + minutes;
    }

    void display() const {
        std::cout << hours << " hrs " << minutes << " mins\n";
    }
};

// -------------------------------------------------------------
// Scenario 3: Class Type to Class Type
// -------------------------------------------------------------
class Celsius {
private:
    double temp;
public:
    Celsius(double t = 0.0) : temp(t) {}
    double getTemp() const { return temp; }
};

class Fahrenheit {
private:
    double temp;
public:
    Fahrenheit(double t = 32.0) : temp(t) {}

    // Converting constructor: Destination accepts Source as parameter
    Fahrenheit(const Celsius& c) {
        temp = (c.getTemp() * 9.0 / 5.0) + 32.0;
    }

    void display() const {
        std::cout << temp << " °F\n";
    }
};

int main() {
    // 1. Basic Type to Class Type
    int rawMinutes = 135;
    Time t = rawMinutes; // Automatically calls Time(int)
    std::cout << "135 minutes -> ";
    t.display();

    // 2. Class Type to Basic Type
    int extracted = t;   // Automatically calls operator int()
    std::cout << "Extracted minutes: " << extracted << "\n";

    // 3. Class Type to Class Type
    Celsius boilingWater(100.0);
    Fahrenheit convertedF = boilingWater; // Calls Fahrenheit(const Celsius&)
    std::cout << "100 °C in Fahrenheit: ";
    convertedF.display();

    return 0;
}
```