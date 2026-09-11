This topic details the internal structure of a class and the mechanics of creating and interacting with objects.

# 1. Classes vs. Objects

A class and an object are the two primary building blocks of Object Orientation.

- **Class:** A user-defined data type that acts as a **blueprint or template** for creating objects. It defines the set of properties (attributes) and methods (behaviors) common to all entities of that type.
- **Object:** A basic unit of OOP and an **instance of a class**. Each object has an identity, state (data), and behavior (code).

# 2. Internal Components of a Class

A class combines data and functions into a single unit.

- **Data Members (Attributes/Fields):** Variables declared within a class that hold the object's data.
- **Member Functions (Behaviors/Methods):** Functions declared within a class that define the actions the object can perform.

# 3. Access Specifiers and Data Hiding

Access specifiers define how class members can be accessed, which is the foundation of **Data Hiding** (concealing data within a class to prevent mistaken access from outside).

- **private** **(Default):** Members are only accessible from within the same class. The default access model for C++ classes is private.
- **public**: Members are accessible from any non-member function outside the class.
- **protected**: Members are inaccessible from the outside but can be accessed by **derived (inherited) classes**.

### C++ Example: Class Blueprint with Access Specifiers
```cpp
#include <iostream>
#include <string>

class Rectangle {
private:
    // Private Data Members (Data Hiding): accessible only within this class
    double length;
    double width;

protected:
    // Protected Member: accessible within this class and derived (child) classes
    std::string color;

public:
    // Public Member Functions: accessible from any code outside the class
    void setDimensions(double l, double w) {
        length = (l > 0) ? l : 1.0;
        width = (w > 0) ? w : 1.0;
    }

    double calculateArea() const {
        return length * width;
    }
};
```

# 4. Member Access Mechanics

To interact with class members from code outside the class definition, specific operators are required:

- **Dot Operator** (.): Used when working directly with an object name (e.g., `objectName.memberName`).
- **Arrow Operator** (->): Used to refer to a member via a **pointer to an object**.

# 5. Defining Member Functions

Member functions can be implemented in two ways:

- **Inside Class Definition:** Functions defined here are automatically treated as **inline functions**.
- **Outside Class Definition:** Used for functions containing more than one statement to keep the class definition clean. This requires the **Scope Resolution Operator (****::****)** along with the class name (e.g., `void Date::setDate(...)`).

### C++ Example: Inside vs. Outside Definition
```cpp
#include <iostream>

class Date {
private:
    int day, month, year;

public:
    // 1. Defined INSIDE class: implicitly treated as inline
    int getYear() const {
        return year;
    }

    // Function prototypes (declarations)
    void setDate(int d, int m, int y);
    void display() const;
};

// 2. Defined OUTSIDE class: requires Scope Resolution Operator (::)
void Date::setDate(int d, int m, int y) {
    day = d;
    month = m;
    year = y;
}

void Date::display() const {
    std::cout << (day < 10 ? "0" : "") << day << "/"
              << (month < 10 ? "0" : "") << month << "/"
              << year << "\n";
}
```

# 6. Object and Array Declarations

Once a class is declared, the class name becomes a new type specifier.

- **Single Objects:** `Date today;`
- **Arrays of Objects:** `Date dtArray[3];`
- **Object Pointers:** `Date *newDatePtr;`

### C++ Example: Instantiating and Accessing Objects
```cpp
int main() {
    // 1. Single Object and Dot Operator (.)
    Date today;
    today.setDate(10, 9, 2026);
    std::cout << "Today's Date: ";
    today.display();
    std::cout << "Year: " << today.getYear() << "\n";

    // 2. Object Pointer and Arrow Operator (->)
    Date* datePtr = &today;
    std::cout << "Via Pointer: ";
    datePtr->display(); // Equivalent to (*datePtr).display()

    // Dynamically allocated object
    Date* newDatePtr = new Date();
    newDatePtr->setDate(1, 1, 2027);
    newDatePtr->display();
    delete newDatePtr; // Free dynamic memory

    // 3. Array of Objects
    Date dtArray[3];
    dtArray[0].setDate(1, 1, 2026);
    dtArray[1].setDate(14, 4, 2026);
    dtArray[2].setDate(25, 12, 2026);

    std::cout << "\nDates in Array:\n";
    for (int i = 0; i < 3; ++i) {
        std::cout << "Item " << (i + 1) << ": ";
        dtArray[i].display();
    }

    return 0;
}
```