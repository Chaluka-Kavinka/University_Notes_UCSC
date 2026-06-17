>Next Topic : [[Memory Management and Advanced Scoping]]

# 1. The Need for Constructors

In Object-Oriented Programming, it is considered best practice to initialize variables when creating objects to ensure the object is in a **valid, predictable state** from the moment of instantiation. A **constructor** is a special member function that is automatically called when an object of the class is created.
## Key Characteristics of Constructors:

- **Naming:** The constructor must have the exact same name as the class.
- **No Return Type:** It cannot return any value and has no return type, not even `void`.
- **Automatic Invocation:** It is triggered by the creation of an object and cannot be called explicitly like a normal member function.
- **Placement:** It is typically defined in the `public` section of a class.
# 2. Types of Constructors

There are three main types of constructors utilized in C++:

- **Default Constructor:** This constructor takes **no arguments**. If you do not explicitly define any constructor, the compiler provides one implicitly, though it leaves data members un-initialized.
- **Parameterized Constructor:** This allows you to **pass arguments** to initialize data members with specific values at the time of object creation.
- **Copy Constructor:** A special constructor used to initialize a new object using an existing object of the same class. If one is not defined, the compiler provides a **bit-wise copy**, which may not be suitable for objects containing pointers or dynamic memory.
# 3. Advanced Constructor Concepts

- **Constructor Overloading:** A class can contain multiple constructors as long as they differ in their parameter lists (number, type, or order of parameters).
- **Member Initializer Lists:** This is an efficient syntax for specifying initial values for data members.
    - _Syntax:_ `ClassName(parameterList) : member1(value1), member2(value2) { }`.
- **Implicit vs. Explicit:** If you define at least one parameterized constructor, you must explicitly define a default constructor if you still wish to create objects without arguments, as the compiler will no longer provide one automatically.
# 4. Destructors

A **destructor** is a special member function automatically called whenever an object of its class ceases to exist. Its primary purpose is to **release resources** (such as dynamic memory) that were allocated by the constructor.

**Key Characteristics of Destructors:**

- **Syntax:** The name is the same as the class but is preceded by a **tilde (~)** symbol.
- **Parameters:** It takes **no parameters** and has no return type.
- **Quantity:** A class can have only **one destructor**.
- **Restrictions:** It cannot be declared as `static` or `const`.
# 5. Order of Execution

The order in which constructors and destructors are called depends on the scope of the objects:

- **Global Objects:** Constructors run before `main()` begins; destructors run when the program terminates.
- **Local Objects:** Constructors run when execution enters the object's scope; destructors run when execution leaves that block.
- **The LIFO Rule:** Destructor calls always occur in the **reverse order** of constructor calls. For example, if Object A was created before Object B, Object B will be destroyed before Object A.