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

# 4. Member Access Mechanics

To interact with class members from code outside the class definition, specific operators are required:

- **Dot Operator** (.): Used when working directly with an object name (e.g., `objectName.memberName`).
- **Arrow Operator** (->): Used to refer to a member via a **pointer to an object**.

# 5. Defining Member Functions

Member functions can be implemented in two ways:

- **Inside Class Definition:** Functions defined here are automatically treated as **inline functions**.
- **Outside Class Definition:** Used for functions containing more than one statement to keep the class definition clean. This requires the **Scope Resolution Operator (****::****)** along with the class name (e.g., `void Date::setDate(...)`).

# 6. Object and Array Declarations

Once a class is declared, the class name becomes a new type specifier.

- **Single Objects:** `Date today;`
- **Arrays of Objects:** `Date DtArray``;`
- **Object Pointers:** `Date *newDatePtr;`