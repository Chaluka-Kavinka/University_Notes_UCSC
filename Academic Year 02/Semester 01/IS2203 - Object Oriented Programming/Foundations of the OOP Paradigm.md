This topic explores the fundamental shift in software development from following a linear sequence of steps to modeling software after real-world entities.

# 1. The Procedural Programming Paradigm

Procedural programming views a problem as a **sequence of instructions** or a list of things for the computer to do.

- **Core Logic:** Statements tell the computer to perform specific actions, such as getting input, performing calculations, and displaying output.
- **Organization:** Large programs are divided into **functions and modules** (also referred to as subroutines or procedures). Each function has a clearly defined purpose and interface.
- **Approach:** It follows a **top-down approach** to software design.
- **Examples:** C, Pascal, FORTRAN, COBOL, and BASIC.

## Limitations of Procedural Programming

As programs grow in size and complexity, procedural methods face several critical issues:

- **Unrestricted Global Data Access:** Functions have unrestricted access to global data, making it easy for one function to accidentally corrupt data needed by another.
- **Difficulty in Modification:** Because data and functions are often unrelated, a single change to a global data item may require rewriting every function that accesses it.
- **Poor Real-World Modeling:** It is difficult to represent complex real-world problems because the focus is on the "procedure" rather than the "entities" involved.
- **Maintenance Hurdles:** As complexity increases, costs skyrocket, schedules slip, and the program's structure becomes difficult to conceptualize.

### C++ Example: The Procedural Approach (Global Data Vulnerability)
```cpp
#include <iostream>

// Global data is exposed and vulnerable to unintended modifications
double accountBalance = 1000.0;

void deposit(double amount) {
    accountBalance += amount;
}

void withdraw(double amount) {
    accountBalance -= amount;
}

int main() {
    deposit(500.0);
    
    // Any function or rogue line can directly corrupt global data:
    accountBalance = -99999.0; // No data validation or protection!
    
    std::cout << "Corrupted Balance: $" << accountBalance << "\n";
    return 0;
}
```

# 2. The Object-Oriented Programming (OOP) Paradigm

OOP organizes software design around **objects**—real-world entities that combine data and behavior—rather than just functions and logic.

- **What is an Object?** An object represents a real-world entity (such as a student, car, or sensor).
- **Components of an Object:**
    - **Attributes (Data/Fields):** Variables inside a class that hold the state of the entity (e.g., a student's name and marks).
    - **Methods (Behaviors):** Functions inside a class that define what the object can do (e.g., calculating an average).
- **Approach:** OOP follows a **bottom-up approach**, focusing on data security and modularity.
- **Core Benefits:** Using a modular, object-oriented design makes development groups significantly more productive than earlier techniques. Key advantages include modularity, reusability, maintainability, and extensibility.

### C++ Example: The Object-Oriented Approach (Data & Behaviors Bundled)
```cpp
#include <iostream>
#include <string>

class BankAccount {
private:
    // Attributes (State) are hidden from direct outside access
    std::string accountNumber;
    double balance;

public:
    // Constructor initializes the object in a valid state
    BankAccount(std::string accNo, double initialBalance) {
        accountNumber = accNo;
        balance = (initialBalance >= 0) ? initialBalance : 0.0;
    }

    // Methods (Behaviors) control how attributes are modified
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            std::cout << "Deposited: $" << amount << "\n";
        }
    }

    void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            std::cout << "Withdrew: $" << amount << "\n";
        } else {
            std::cout << "Withdrawal denied: Insufficient funds or invalid amount.\n";
        }
    }

    double getBalance() const {
        return balance;
    }
};

int main() {
    BankAccount account("BA-1002", 1000.0);
    account.deposit(500.0);
    account.withdraw(200.0);
    
    // account.balance = -99999.0; // COMPILE ERROR: 'balance' is private!
    
    std::cout << "Current Balance: $" << account.getBalance() << "\n";
    return 0;
}
```

# 3. Procedural vs. Object-Oriented: Key Differences

| Feature               | Procedural Programming (PP)                 | Object-Oriented Programming (OOP)        |
| --------------------- | ------------------------------------------- | ---------------------------------------- |
| **Organization**      | Divided into functions.                     | Divided into objects.                    |
| **Focus**             | Function is more important than data.       | Data is more important than functions.   |
| **Approach**          | Top-down.                                   | Bottom-up.                               |
| **Data Security**     | Less secure; no proper way for data hiding. | Highly secure; provides data hiding.     |
| **Access Specifiers** | None.                                       | Includes public, private, and protected. |
| **Real-World Model**  | Based on "unreal" world logic.              | Based on the real world.                 |
| **Overloading**       | Not possible.                               | Possible.                                |

# 4. The Four Pillars of OOP

These core principles allow developers to handle software complexity effectively:

- **Encapsulation (Data Hiding):** The wrapping of data and functions into a single unit (a class). This protects data from accidental outside interference and ensures that implementation details are hidden within the objects themselves.

```cpp
class Student {
private:
    int marks; // Hidden from direct external modification

public:
    void setMarks(int m) {
        if (m >= 0 && m <= 100) { // Controlled data access with validation
            marks = m;
        }
    }
    int getMarks() const { return marks; }
};
```

- **Abstraction:** Providing only essential information to the outside world while hiding the background implementation details. For example, a driver knows how to use a car's accelerator to increase speed without needing to know the mechanical implementation.

```cpp
class Car {
private:
    // Internal mechanical details hidden from the driver
    void injectFuel() { /* ... */ }
    void igniteSpark() { /* ... */ }

public:
    // Simple, essential public interface
    void accelerate() {
        injectFuel();
        igniteSpark();
        std::cout << "Car is accelerating smoothly.\n";
    }
};
```

- **Inheritance:** The capability of a class (subclass) to derive properties and characteristics from another class (superclass). Often called an **"is-a" hierarchy**, it is the key to code reuse and reducing redundancy.

```cpp
// Base Class (General)
class Vehicle {
protected:
    int speed;
public:
    Vehicle(int s) : speed(s) {}
    void drive() const { std::cout << "Moving at " << speed << " km/h\n"; }
};

// Derived Class (Specialized: Car IS-A Vehicle)
class SportsCar : public Vehicle {
public:
    SportsCar(int s) : Vehicle(s) {}
    void turboBoost() {
        speed += 50;
        std::cout << "Turbo engaged! Speed: " << speed << " km/h\n";
    }
};
```

- **Polymorphism:** Meaning "many forms," it is the ability of a message or function to be displayed or behave in more than one form. This allows objects of different classes to be used interchangeably.

```cpp
class Shape {
public:
    virtual void draw() const {
        std::cout << "Drawing generic shape\n";
    }
    virtual ~Shape() {}
};

class Circle : public Shape {
public:
    void draw() const override {
        std::cout << "Drawing Circle (○)\n";
    }
};

class Rectangle : public Shape {
public:
    void draw() const override {
        std::cout << "Drawing Rectangle (▭)\n";
    }
};

// Runtime Polymorphism in action:
// Shape* s = new Circle();
// s->draw(); // Calls Circle's draw() dynamically!
// delete s;
```

# 5. History and Characteristics of C++

C++ was developed as an enhancement to the C language to include the object-oriented paradigm.

- **Origins:** Developed by **Bjarne Stroustrup** in 1979 at Bell Labs.
- **Evolution:** Originally called **"C with Classes,"** it was renamed **C++** in 1984. The "++" symbolizes the C increment operator, signifying it is an advanced version of C.
- **Key Features:**
    - **Middle-Level Language:** It combines features of both high-level and low-level languages.
    - **Life-cycle Control:** It allows the explicit creation and destruction of objects while programming.
    - **Portability:** It is machine-independent but platform-dependent.
- **Major Updates:** The language has been updated significantly over time, notably with the releases of C++11, C++14, and C++17.