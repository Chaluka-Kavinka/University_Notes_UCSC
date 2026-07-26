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

# 4. The Five Types of Inheritance

C++ supports various structures for inheriting properties:

1. **Single Inheritance:** A subclass inherits from only one base class.
2. **Multiple Inheritance:** A single subclass inherits from more than one base class.
3. **Multilevel Inheritance:** A derived class is created from another derived class (e.g., Class C inherits from B, which inherits from A).
4. **Hierarchical Inheritance:** More than one subclass is inherited from a single base class.
5. **Hybrid Inheritance:** A combination of more than one type of inheritance (e.g., combining Hierarchical and Multiple).

# 6. Constructors and Destructors in Inheritance

- **Not Inherited:** A derived class does **not** inherit constructors, destructors, or the assignment operator from the base class.
- **Automatic Invocation:** When a derived class object is created, the **base class constructor is invoked first**, followed by the derived class constructor.
- **Destruction Order:** Destructors are called in the **exact reverse order** of constructors.
- **Explicit Calls:** Derived class constructors can manually call base class constructors using a constructor initialization list.