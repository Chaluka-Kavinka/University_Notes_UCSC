This topic covers how C++ manages data in memory, the classification of data types, and the evolution of structures into classes.

# 1. Understanding Data Types

A **data type** defines the type of data a variable can store. When a variable is declared, the compiler allocates a specific amount of memory based on its type.

- **Memory Requirements:** Different types require different amounts of space. For example, an **Integer (****int****)** typically requires **4 bytes**, while a **Character (****char****)** requires **1 byte**.
- **Classification:** C++ categorizes data types into three main groups: **Primary**, **Derived**, and **User-Defined**.

# 2. Primary (Built-in) Data Types

These are predefined by the language and can be used directly to declare variables.

- **Examples:** `int` (Integer), `char` (Character), `float` (Floating point), `double` (Double floating point), `bool` (Boolean), and `void` (representing the absence of data).

# 3. Derived Data Types

These types are formed by deriving them from primary or built-in data types.

- **Functions:** A block of code designed to perform a specific task.
- **Arrays:** A collection of items of the same type stored at **contiguous memory locations**.
- **Pointers:** A symbolic representation of memory addresses. A pointer "points" to the specific address that holds data.
    - _Syntax:_ `datatype *var_name;`.
- **References:** An **alternative name** (alias) for an existing variable, declared using the **&** symbol.

# 4. Pointers and Memory Mechanics

Pointers are a fundamental tool for managing memory directly.

- **Address-of Operator (****&****):** Used to retrieve the memory location of a variable (e.g., `ptr = &var;`).
- **Dereferencing Operator (*********):** Used to access the actual value stored at the address a pointer is holding.
- **Pointer to Pointer:** C++ allows multiple levels of indirection, such as double pointers (`int **pt`) or triple pointers (`int ***ptr`).

### C++ Example: Pointers, References, and Memory Addresses
```cpp
#include <iostream>

int main() {
    int num = 42;
    
    // 1. Pointer: Holds the memory address of num
    int* ptr = &num;
    
    // 2. Pointer to Pointer: Holds the memory address of ptr
    int** ptrToPtr = &ptr;
    
    // 3. Reference: An alias (alternative name) for num
    int& ref = num;

    std::cout << "Original Value: " << num << "\n";
    std::cout << "Memory Address (&num): " << &num << "\n";
    std::cout << "Pointer value (ptr): " << ptr << "\n";
    std::cout << "Dereferenced (*ptr): " << *ptr << "\n";
    std::cout << "Double Dereference (**ptrToPtr): " << **ptrToPtr << "\n";

    // Modifying through reference modifies the original variable
    ref = 99;
    std::cout << "After modifying ref, num = " << num << " and *ptr = " << *ptr << "\n";

    return 0;
}
```

# 5. User-Defined Data Types: Structures (*struct*)

Structures allow you to organize simple variables into complex entities, such as grouping a student's name, age, height, and weight.

- **Aggregate Type:** Aggregates elements of different types into a single unit.
- **Syntax:** Defined using the `struct` keyword and must always end with a **semicolon (****;****)**.
- **Declaration:** In C++, the keyword `struct` is optional when defining a variable of that type (e.g., `date today;` instead of `struct date today;`).
- **Member Access:** Use the **dot operator (****.****)** to access specific data members (e.g., `today.day`).

### C++ Example: Defining and Using Structures
```cpp
#include <iostream>
#include <string>

// Defining a structure
struct Student {
    int id;
    std::string name;
    float gpa;
};

int main() {
    // In C++, the 'struct' keyword is optional during declaration
    Student s1;
    
    // Member access using the dot (.) operator
    s1.id = 22001;
    s1.name = "Kalindu";
    s1.gpa = 3.85f;

    // Initialization using aggregate list
    Student s2 = {22002, "Amara", 3.92f};

    std::cout << "Student 1: " << s1.name << " (ID: " << s1.id << ", GPA: " << s1.gpa << ")\n";
    std::cout << "Student 2: " << s2.name << " (ID: " << s2.id << ", GPA: " << s2.gpa << ")\n";

    return 0;
}
```

# 6. Evolution: Structures to Classes

Classes in C++ are a natural evolution of the C notion of structures. While they are very similar, there are two critical differences:

- **Member Functions:** In standard C, structures only hold data. In C++, both **Data Members** and **Member Functions** (behaviors) can be included inside a structure.
- **Default Access (The Key Distinction):**
    - In a **Structure**, members are **PUBLIC** by default.
    - In a **Class**, members are **PRIVATE** by default.

### C++ Example: Struct with Functions vs. Class Default Access
```cpp
#include <iostream>

// 1. C++ Struct: Members are PUBLIC by default & can have methods
struct DateStruct {
    int day, month, year; // public by default

    void display() const {
        std::cout << "Date: " << day << "/" << month << "/" << year << "\n";
    }
};

// 2. C++ Class: Members are PRIVATE by default
class DateClass {
    int day, month, year; // private by default! Cannot be accessed outside directly

public:
    void setDate(int d, int m, int y) {
        day = d; month = m; year = y;
    }

    void display() const {
        std::cout << "Date: " << day << "/" << month << "/" << year << "\n";
    }
};

int main() {
    DateStruct ds;
    ds.day = 15; // OK: public by default
    ds.month = 8;
    ds.year = 2026;
    ds.display();

    DateClass dc;
    // dc.day = 15; // COMPILE ERROR: 'day' is private within this context!
    dc.setDate(15, 8, 2026); // OK: calling public member function
    dc.display();

    return 0;
}
```