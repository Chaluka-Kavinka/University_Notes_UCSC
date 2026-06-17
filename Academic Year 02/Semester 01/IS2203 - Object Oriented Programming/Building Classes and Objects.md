>Next Topic : [[The Object Life-cycle (Constructors & Destructors)]]

# 1. Classes vs. Objects

The relationship between a class and an object is often compared to a blueprint and the actual structure built from it.

- **Class:** A user-defined data type that acts as a **blueprint or template** for creating objects. it defines what data the objects will hold and what actions they can perform.
- **Object:** A basic unit of OOP representing a **real-life entity**. It is a specific **instance of a class**. For example, if "Car" is the class, "My Blue Car" is a specific object of that class.

# 2. Anatomy of a Class

A class consists of two primary components:

- **Data Members (Attributes):** Variables declared within a class that hold the state or characteristics of the object (e.g., a car's color or registration number).
- **Member Functions (Behaviors/Methods):** Functions declared within a class that define the actions an object can take (e.g., `start()`, `accelerate()`, or `calculateAverage()`).

# 3. Access Specifiers and Data Hiding

Access specifiers define how the members of a class can be accessed from other parts of the program, which is the foundation of **Data Hiding**.

- **private** **(Default):** Members are only accessible from within the same class. This protects data from accidental outside interference.
- **public****:** Members are accessible from any non-member function outside the class.
- **protected****:** Similar to private, but members can be accessed by derived (inherited) classes.
- **Important Distinction:** In C++, the default access for a `class` is **private**, whereas for a `struct`, it is **public**.

# 4. Accessing Class Members

To use an object's data or functions, you must use specific operators:

- **Dot Operator (****.****):** Used to access members when you are working directly with an object name (e.g., `myObject.variableName` or `myObject.functionName()`).
- **Arrow Operator (****->****):** Used to access members when you are referring to an object through a **pointer** (e.g., `ptrToObject->functionName()`).

# 5. Defining Member Functions

You can define how a class's behavior works in two ways:

- **Inside the Class:** Functions defined here are automatically treated as **inline functions**.
- **Outside the Class:** Used for functions with multiple statements to keep the class definition clean. This requires the **Scope Resolution Operator (****::****)** to link the function back to its class (e.g., `void ClassName::FunctionName()`).

# 6. Complex Class Relationships

- **Nested Classes:** You can define a class inside another class to represent a localized relationship.
- **Member Objects:** A class can have a data member that is itself an object of another class. For example, a `Cylinder` class might contain a `Circle` object to represent its base.