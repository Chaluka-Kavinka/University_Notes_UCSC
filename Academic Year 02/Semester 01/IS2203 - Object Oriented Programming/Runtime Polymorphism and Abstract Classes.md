This final topic explores **Late Binding**, a powerful feature of C++ that allows programs to decide which function to execute at runtime rather than at compile time.

# 1. Understanding Runtime Polymorphism

Polymorphism, meaning "many forms," allows a single message to be displayed in more than one form. While **Compile-Time Polymorphism** is achieved through function and operator overloading, **Runtime Polymorphism** is achieved through **Function Overriding** and **Virtual Functions**.

- **Definition:** It is the ability of C++ to ensure the correct function is called for an object, regardless of the type of the reference (pointer or alias) used to call it.
- **Late Binding:** Unlike overloading, where the compiler picks the function during compilation, runtime polymorphism involves "dynamic binding," where the decision is made while the program is running.

# 2. Function Overriding

Function overriding occurs when a derived class provides a new definition for a member function that already exists in its base class.

- **Requirement:** The overriding function must have the **exact same signature** (name and parameter list) as the function in the base class.
- **The** **override** **Keyword (C++11):** To prevent accidental mistakes (such as typos or signature mismatches), programmers can use the `override` keyword. This forces the compiler to check if a matching virtual function actually exists in the base class; if not, it triggers a compilation error.

# 3. Virtual Functions: The Key to Flexibility

A **virtual function** is a member function declared in a base class using the **virtual** keyword, which you intend to redefine in derived classes.

- **Mechanism (vtable and vptr):**
    - For every class containing virtual functions, the compiler creates a **vtable (virtual table)**.
    - This table stores the addresses of the virtual functions for that specific class.
    - Each object of such a class contains a hidden **vptr (virtual pointer)** that points to its class's vtable.
    - When a virtual function is called via a pointer, the program looks up the address in the vtable to ensure the "actual" object's version is executed.
- **Costs:** Using virtual functions requires a small amount of extra memory for the vtable and incurs a minor performance penalty during the lookup process.

### C++ Example: Virtual Functions and Late Binding
```cpp
#include <iostream>
#include <vector>

class Animal {
public:
    // Virtual destructor: Essential to guarantee proper cleanup of derived objects
    virtual ~Animal() {
        std::cout << "Animal destructor\n";
    }

    // Virtual function enables Late Binding (Dynamic Dispatch)
    virtual void speak() const {
        std::cout << "Generic animal sound\n";
    }
};

class Dog : public Animal {
public:
    ~Dog() override {
        std::cout << "Dog destructor\n";
    }

    // The 'override' keyword ensures the base virtual function exists
    void speak() const override {
        std::cout << "Dog says: Woof! Woof!\n";
    }
};

class Cat : public Animal {
public:
    ~Cat() override {
        std::cout << "Cat destructor\n";
    }

    void speak() const override {
        std::cout << "Cat says: Meow!\n";
    }
};

int main() {
    // Base class pointers holding addresses of derived class objects
    Animal* animals[] = { new Dog(), new Cat() };

    for (int i = 0; i < 2; ++i) {
        // Late binding: The decision of which speak() to call happens at runtime
        animals[i]->speak();
    }

    // Cleaning up dynamically allocated objects
    for (int i = 0; i < 2; ++i) {
        delete animals[i]; // Virtual destructor ensures Dog/Cat destructor is called first!
    }

    return 0;
}
```

# 4. Pure Virtual Functions and Abstract Classes

Sometimes, a base class is so general that it cannot provide a meaningful implementation for a function (e.g., a `Shape` class cannot calculate an area because it doesn't know its geometry).

- **Pure Virtual Functions:** These are functions declared in the base class without any implementation. They are defined by assigning **0** to the declaration (e.g., `virtual void draw() = 0;`).
- **Abstract Classes:**
    - A class is considered **Abstract** if it contains at least one pure virtual function.
    - **Instantiation Rule:** Abstract classes **cannot be instantiated** (you cannot create objects of that class).
    - **Mandatory Implementation:** If a derived class does not override the pure virtual function, it also becomes an abstract class and cannot be instantiated.

### C++ Example: Abstract Classes and Pure Virtual Functions
```cpp
#include <iostream>

// Abstract Base Class: acts as an interface/blueprint
class Shape {
public:
    virtual ~Shape() {}

    // Pure Virtual Functions (declared with = 0)
    virtual double calculateArea() const = 0;
    virtual void draw() const = 0;
};

// Concrete Derived Class: MUST implement all pure virtual functions
class Circle : public Shape {
private:
    double radius;

public:
    Circle(double r) : radius(r) {}

    double calculateArea() const override {
        return 3.14159 * radius * radius;
    }

    void draw() const override {
        std::cout << "Drawing Circle of area: " << calculateArea() << "\n";
    }
};

int main() {
    // Shape s; // COMPILE ERROR: cannot declare variable 's' to be of abstract type 'Shape'
    
    // Abstract class pointer pointing to concrete derived instance
    Shape* shape = new Circle(7.0);
    shape->draw();
    
    delete shape;
    return 0;
}
```

# 5. Method Hiding: A Cautionary Note

In C++, if a derived class redefines a base class member method, **all** methods in the base class with that same name become **hidden** in the derived class.

- **The Trap:** Even if the derived class version has a different signature, the base class's overloaded versions are still hidden and cannot be accessed through the derived object without explicit scope resolution.

### C++ Example: Method Hiding and the `using` Keyword
```cpp
#include <iostream>
#include <string>

class Base {
public:
    void print() {
        std::cout << "Base: print() with no parameters\n";
    }

    void print(int x) {
        std::cout << "Base: print(int) with value " << x << "\n";
    }
};

class Derived : public Base {
public:
    // SOLUTION: Bring Base's overloaded methods into Derived scope
    using Base::print;

    // Redefining print with a different signature hides Base's versions unless 'using' is added
    void print(std::string str) {
        std::cout << "Derived: print(string) with value '" << str << "'\n";
    }
};

int main() {
    Derived d;

    // Both Base overloads are accessible thanks to 'using Base::print;'
    d.print();          // Calls Base::print()
    d.print(100);       // Calls Base::print(int)
    d.print("UCSC");    // Calls Derived::print(string)

    return 0;
}
```