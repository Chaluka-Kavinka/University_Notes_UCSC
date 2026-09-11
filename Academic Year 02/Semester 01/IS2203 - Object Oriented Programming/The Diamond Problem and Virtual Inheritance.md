The **Diamond Problem** is a complex ambiguity that arises in C++ through a specific type of multiple inheritance known as **Multipath Inheritance**.

# 1. Defining the Problem

The Diamond Problem occurs when a derived class has two base classes, and those two base classes share a common base class of their own. This creates a "diamond" shape in the class hierarchy:

- **Base Class:** `Person`.
- **Intermediate Classes:** `Student` and `Faculty` both inherit from `Person`.
- **Derived Class:** `TA` (Teaching Assistant) inherits from both `Student` and `Faculty`.

# 2. The Ambiguity Issue

Because the derived class (`TA`) inherits from two classes that both contain the members of the same ancestor (`Person`), the derived class receives **two separate copies** of the ancestor's attributes and methods.

## Technical Consequences:

- **Memory Redundancy:** The object contains duplicate data (e.g., two copies of `Name` and `Age` from the `Person` class).
- **Compiler Confusion:** If you try to access a member from the common ancestor through the bottom-most object, the compiler cannot determine which "path" to follow, resulting in a **compilation error**.
- **Duplicate Execution:** In a standard diamond structure, the constructor for the common ancestor is called twice, and its destructor is also called twice when the object is destroyed.

### C++ Code: Demonstrating the Ambiguity Error
```cpp
#include <iostream>
#include <string>

class Person {
public:
    std::string name;
};

// Both inherit normally from Person
class Student : public Person {};
class Faculty : public Person {};

// TA inherits two separate copies of Person (one via Student, one via Faculty)
class TA : public Student, public Faculty {};

int main() {
    TA ta;
    
    // ta.name = "Kalindu";
    // COMPILE ERROR: request for member 'name' is ambiguous!
    // The compiler cannot determine if 'name' refers to Student::Person::name 
    // or Faculty::Person::name.
    
    return 0;
}
```

# 3. Solution 1: Virtual Inheritance (Recommended)

The most robust way to solve the Diamond Problem is to use **Virtual Base Classes**. By using the **virtual** keyword during the intermediate inheritance, you tell the compiler to ensure only one copy of the ancestor exists.

- **Syntax:** `class Student : virtual public Person { ... };`.
- **How it Works:** When the bottom-most class (`TA`) is instantiated, the compiler recognizes the virtual base class and ensures that both `Student` and `Faculty` share a **single common instance** of `Person`.
- **Result:** The third statement in a program will overwrite the value from the second statement because there is now only one copy of the data member.

### C++ Example: Virtual Inheritance Resolving the Diamond Problem
```cpp
#include <iostream>
#include <string>

class Person {
public:
    std::string name;

    Person(std::string n = "Anonymous") : name(n) {
        std::cout << "Person initialized (" << name << ")\n";
    }
};

// Virtual base class inheritance ensures a single Person subobject
class Student : virtual public Person {
protected:
    int studentId;
public:
    Student(std::string n, int id) : Person(n), studentId(id) {}
};

class Faculty : virtual public Person {
protected:
    std::string department;
public:
    Faculty(std::string n, std::string dept) : Person(n), department(dept) {}
};

class TA : public Student, public Faculty {
public:
    // With virtual inheritance, the most derived class (TA) directly initializes Person
    TA(std::string n, int id, std::string dept)
        : Person(n), Student(n, id), Faculty(n, dept) {}

    void print() const {
        // Direct access: no ambiguity!
        std::cout << "TA Name: " << name 
                  << ", ID: " << studentId 
                  << ", Department: " << department << "\n";
    }
};

int main() {
    TA ta("Kalindu", 22001, "Information Systems");
    ta.print(); // Works perfectly; Person constructor called only once
    return 0;
}
```

# 4. Solution 2: Scope Resolution Operator

If virtual inheritance is not used, you can still resolve the ambiguity manually by telling the compiler exactly which path to use to access a data member.

- **Syntax:** `obj.IntermediateClass::member;`.
- **Example:** `obj.ClassB::a = 10;` specifies that the version of member `a` inherited via `ClassB` should be used.
- **Limitation:** While this resolves the compiler's immediate confusion, it does not solve the underlying issue of having redundant data in memory.

### C++ Example: Disambiguation via Scope Resolution Operator
```cpp
#include <iostream>
#include <string>

class Person {
public:
    std::string name;
};

class Student : public Person {};
class Faculty : public Person {};
class TA : public Student, public Faculty {};

int main() {
    TA ta;

    // Explicitly specify which intermediate branch to access
    ta.Student::name = "Kalindu (Student Branch)";
    ta.Faculty::name = "Kalindu (Faculty Branch)";

    std::cout << "Student copy: " << ta.Student::name << "\n";
    std::cout << "Faculty copy: " << ta.Faculty::name << "\n";
    // Redundant copies still consume extra memory!

    return 0;
}
```