>Next Topic : [[Android Application Project Elements]]

# What is Kotlin?

- **Definition:** Kotlin is a **modern, statically-typed** programming language developed by **JetBrains** (the creators of IntelliJ IDEA) around 2011-2012.
- **Platform:** it runs on the **Java Virtual Machine (JVM)** and is **fully interoperable with Java**, allowing for a gradual transformation of codebases.
- **Key Characteristics:** It is designed for **productivity**, being expressive and concise (less boilerplate) while focusing on **safer code**.
# Variables and Values

Kotlin distinguishes between mutable and immutable data:

- **val** **(Value):** Immutable references. Once a value is assigned, it **cannot be reassigned**.
- **var** **(Variable):** Mutable references that **can be reassigned**.
- **Type Inference:** Kotlin has powerful type inference, meaning the compiler can often determine the data type automatically, though you can explicitly declare it if needed.
- **Statically-Typed:** Once a type is assigned (by you or the compiler), it **never changes**.
# Data Types

- **Core Types:** Includes **String** (text), **Int** (integers), **Double** (decimal), **Float** (less precise decimal), and **Boolean** (true/false).
- **No Primitive/Wrapper Distinction:** Unlike Java, Kotlin does not differentiate between primitive types (like `int`) and wrapper classes (like `Integer`). This eliminates the need for explicit boxing and unboxing.
# Null Safety: A Key Feature

One of Kotlin's primary goals is to eliminate **Null Pointer Exceptions (NPE)**.

- **Non-Nullable by Default:** Variables cannot be null unless explicitly specified.
- **Safe Call Operator (****?****):** Placing a `?` after a type (e.g., `String?`) allows that variable to hold a null value.
- **Elvis Operator (****?:****):** Used to provide a default value if an expression evaluates to null (e.g., `val length = name?.length ?: -1`).
# Functions

- **Syntax:** Functions are declared using the `fun` keyword. The common syntax is: `fun functionName(parameter: Type): ReturnType { ... }`.
- **Named & Default Arguments:** Kotlin supports **default values** for parameters, allowing you to call functions without passing every argument. You can also use **named arguments** to make code more readable.
- **Naming Convention:** Function names should be in **camelCase** and are typically verbs or verb phrases.
# Control Flow

- **if** **Expression:** In Kotlin, `if` can be an **expression** that returns a value, serving as a replacement for the traditional ternary operator found in Java/C++.
- **when** **Expression:** This is a powerful replacement for the `switch` statement. it matches its argument against all branches sequentially until some branch condition is satisfied.
- **Loops:** Supports standard **while** and **do-while** loops. The **for** loop is used to iterate over anything that provides an iterator, such as ranges or arrays.
# Arrays and Ranges

- **Arrays:** Created using `arrayOf()`. Elements can be accessed or replaced using bracket notation (e.g., `cars = "BMW"`).
- **Ranges:** Defined using `..` (e.g., `1..10`). You can iterate in reverse using `downTo` and control the increment size with `step`.
# Object-Oriented Programming (OOP)

- **Classes & Objects:** Classes are defined with the `class` keyword, and objects are instantiated without the `new` keyword (e.g., `val c1 = Car()`).
- **Constructors:** A **primary constructor** can be defined in the class header. Initialization logic is placed inside **init** **blocks**.
- **Inheritance:** Classes are **closed by default**. To allow a class to be inherited, it must be marked with the **open** keyword.
# Exception Handling

- Kotlin uses **try**, **catch**, and **finally** blocks to handle exceptions.
- You can manually throw an exception using the **throw** keyword (e.g., `throw IllegalStateException("Error")`).