Inheritance is one of the most critical features of Object-Oriented Programming. It is a mechanism that allows a new class to derive properties and characteristics from an existing class, effectively establishing an **"is-a" hierarchy**.

# 1. Core Concepts and Terminology

- **Inheritance Defined:** The capability of a class to derive properties and behaviors from another class.
- **Super Class (Base/Parent Class):** The class whose properties are inherited by the subclass.
- **Sub Class (Derived/Child Class):** The class that inherits properties from another class.
- **Key Benefit: Code Reuse:** Inheritance allows developers to create a general software component (base class) and then derive specialized classes from it. This reduces data redundancy and the chance of errors since common functions (like `applyBrakes()` for all vehicles) only need to be written once.

# 2. Implementing Inheritance in C++

To create a subclass, you use a specific syntax involving a colon (`:`) after the subclass name.

- **Syntax:** `class subclass_name : access_mode base_class_name { ... };`.
- **Example:** If `class Child : public Parent` is declared, the `Child` class inherits all public data members and member functions of the `Parent` class.

# 3. Modes of Inheritance

The **access mode** determines how members of the base class are viewed by the derived class.

|Base Class Member Access|**Public** Inheritance|**Protected** Inheritance|**Private** Inheritance|
|---|---|---|---|
|**Public**|Becomes **Public**|Becomes **Protected**|Becomes **Private**|
|**Protected**|Becomes **Protected**|Becomes **Protected**|Becomes **Private**|
|**Private**|**Not Accessible** (Hidden)|**Not Accessible** (Hidden)|**Not Accessible** (Hidden)|

- **Note:** While private members are not directly accessible in the derived class, the derived class still inherits a "full parent object".

### C++ Example: Basic Inheritance and Access Modes
```cpp
#include <iostream>

class Base {
private:
    int privateVar = 10;     // Accessible ONLY inside Base
protected:
    int protectedVar = 20;   // Accessible in Base and Derived classes
public:
    int publicVar = 30;      // Accessible everywhere
};

// Public Inheritance: protected remains protected, public remains public
class Derived : public Base {
public:
    void display() {
        // std::cout << privateVar; // COMPILE ERROR: privateVar is inaccessible
        std::cout << "Protected: " << protectedVar << "\n"; // OK
        std::cout << "Public:    " << publicVar << "\n";    // OK
    }
};
```

# 4. The Five Types of Inheritance

C++ supports various structures for inheriting properties:

1. **Single Inheritance:** A subclass inherits from only one base class.
2. **Multiple Inheritance:** A single subclass inherits from more than one base class.
3. **Multilevel Inheritance:** A derived class is created from another derived class (e.g., Class C inherits from B, which inherits from A).
4. **Hierarchical Inheritance:** More than one subclass is inherited from a single base class.
5. **Hybrid Inheritance:** A combination of more than one type of inheritance (e.g., combining Hierarchical and Multiple).

### C++ Example: The Five Types of Inheritance
```cpp
// 1. Single Inheritance
class Animal {};
class Dog : public Animal {};

// 2. Multilevel Inheritance
class LivingThing {};
class Mammal : public LivingThing {};
class Human : public Mammal {};

// 3. Multiple Inheritance (Subclass has more than one base class)
class Printer {};
class Scanner {};
class AllInOneMachine : public Printer, public Scanner {};

// 4. Hierarchical Inheritance (Multiple subclasses share one base class)
class Shape {};
class Circle : public Shape {};
class Square : public Shape {};

// 5. Hybrid Inheritance (Combines two or more inheritance types)
class Device {};
class Phone : public Device {};
class Camera : public Device {};
class SmartPhone : public Phone, public Camera {}; // Combines Hierarchical + Multiple
```

# 5. Constructors and Destructors in Inheritance

- **Not Inherited:** A derived class does **not** inherit constructors, destructors, or the assignment operator from the base class.
- **Automatic Invocation:** When a derived class object is created, the **base class constructor is invoked first**, followed by the derived class constructor.
- **Destruction Order:** Destructors are called in the **exact reverse order** of constructors.
- **Explicit Calls:** Derived class constructors can manually call base class constructors using a constructor initialization list.

### C++ Example: Constructor and Destructor Call Order
```cpp
#include <iostream>
#include <string>

class Vehicle {
protected:
    std::string brand;
    int speed;

public:
    Vehicle(std::string b, int s) : brand(b), speed(s) {
        std::cout << "1. Base Class (Vehicle) constructor called for " << brand << "\n";
    }

    virtual ~Vehicle() {
        std::cout << "4. Base Class (Vehicle) destructor called for " << brand << "\n";
    }
};

class Car : public Vehicle {
private:
    int numDoors;

public:
    // Calling the Base Class Constructor using the Member Initializer List
    Car(std::string b, int s, int doors) : Vehicle(b, s), numDoors(doors) {
        std::cout << "2. Derived Class (Car) constructor called\n";
    }

    ~Car() override {
        std::cout << "3. Derived Class (Car) destructor called\n";
    }

    void display() const {
        std::cout << brand << " car running at " << speed << " km/h with " << numDoors << " doors.\n";
    }
};

int main() {
    {
        Car myCar("Toyota", 120, 4);
        myCar.display();
    } // Out of scope: Car destructed first, then Vehicle destructed

    return 0;
}
```