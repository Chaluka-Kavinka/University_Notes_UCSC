This topic explores advanced C++ features that control how data is shared across a class, how we protect data from unintended modification, and how an object identifies itself.

# 1. Static Members: Shared Class Logic

In C++, the **static** keyword allows you to define members that belong to the **class as a whole** rather than to any specific instance (object).

- **Static Data Members:**
    - **Shared Identity:** These variables are shared by all objects of the class; there is only one copy regardless of how many objects are created.
    - **Initialization:** They cannot be initialized using constructors because they do not depend on individual object initialization. Instead, they must be **initialized explicitly outside the class** using the scope resolution operator: `Type ClassName::variable_name = value;`.
    - **Scope:** Static objects persist for the entire lifetime of the program.
- **Static Member Functions:**
    - **Class-Level Access:** These functions work for the class as a whole and do not depend on a particular object.
    - **Invocation:** They can be called using an object, but it is recommended to call them using the class name and scope resolution operator: `ClassName::staticMemberName()`.
    - **Strict Limitations:** They can **only access static data members** or other static member functions. They **do not have a** **this** **pointer** and cannot be declared as `const`.

### C++ Example: Static Data Members and Functions
```cpp
#include <iostream>
#include <string>

class Student {
private:
    std::string name;
    static int studentCount; // Static data member declaration

public:
    Student(std::string n) : name(n) {
        studentCount++; // Increment count when an object is created
    }

    // Static member function: Accessible without an object instance
    static int getStudentCount() {
        // 'name' cannot be accessed here because static functions have no 'this' pointer
        return studentCount;
    }
};

// Explicit definition and initialization outside the class (Mandatory)
int Student::studentCount = 0;

int main() {
    std::cout << "Initial Count: " << Student::getStudentCount() << "\n";

    Student s1("Nimal");
    Student s2("Sunil");

    // Invoked using the class name and scope resolution operator
    std::cout << "Total Students: " << Student::getStudentCount() << "\n";
    return 0;
}
```

# 2. The **const** Keyword: Ensuring Immutability

The **const** keyword is a safety feature used to create "read-only" entities that cannot be changed after their initial value is set.

- **Constant Data Members:** These are not initialized during declaration but rather within the **constructor's initializer list**. Once initialized, their value can never be changed during the object's lifetime.
- **Constant Pointers:**
    - **Pointer to a Constant:** The value being pointed to cannot change, but the pointer can point elsewhere.
    - **Constant Pointer:** The address the pointer holds cannot change, but the value at that address can be modified.
- **Constant Member Functions:**
    - **Guarantee:** These functions are guaranteed **never to modify the data members** of the object.
    - **Syntax:** The keyword is added after the function signature: `void getVal() const;`.
- **Constant Objects:** When an object is declared as `const`, it can **only call constant member functions** to ensure its state remains unchanged.

### C++ Example: Const Members, Functions, and Objects
```cpp
#include <iostream>

class Account {
private:
    const int accountNumber; // Constant data member: immutable once set
    double balance;

public:
    // Must initialize const member in initializer list
    Account(int accNo, double bal) : accountNumber(accNo), balance(bal) {}

    // Const member function: Guarantees it will not alter object state
    int getAccountNumber() const {
        return accountNumber;
    }

    double getBalance() const {
        return balance;
    }

    void deposit(double amount) {
        balance += amount; // Non-const function modifies state
    }
};

int main() {
    // Regular object: Can call const and non-const methods
    Account acc1(1001, 5000.0);
    acc1.deposit(1000.0);

    // Constant object: Can ONLY call const member functions
    const Account acc2(1002, 8500.0);
    std::cout << "Account: " << acc2.getAccountNumber() << ", Balance: $" << acc2.getBalance() << "\n";

    // acc2.deposit(500.0); // COMPILE ERROR: cannot call non-const method on const object!
    return 0;
}
```

# 3. The **this** Pointer: Object Self-Reference

Every non-static member function in C++ has access to a hidden implicit pointer called **this**.

- **Definition:** The `this` pointer contains the **memory address of the specific object** that is currently invoking the function.
- **Mechanics:** It is passed as a hidden argument to all non-static member function calls and is available as a local variable within the function body.
- **Static Limitation:** Because static member functions are not associated with a particular object, the **this** **pointer is not available** within them.
- **Usage:** It is commonly used to distinguish between class data members and local parameters if they share the same name (e.g., `this->width = width;`).

### C++ Example: Disambiguation and Method Chaining via `this`
```cpp
#include <iostream>

class Box {
private:
    double width;
    double height;

public:
    Box() : width(1.0), height(1.0) {}

    // 1. Disambiguating parameters from member variables with identical names
    Box& setWidth(double width) {
        this->width = width;
        return *this; // Return reference to current object to enable chaining
    }

    Box& setHeight(double height) {
        this->height = height;
        return *this;
    }

    void display() const {
        std::cout << "Box (" << this->width << " x " << this->height << ")\n";
    }
};

int main() {
    Box myBox;
    
    // Method chaining / cascading enabled by returning *this
    myBox.setWidth(12.5).setHeight(8.0);
    myBox.display();

    return 0;
}
```