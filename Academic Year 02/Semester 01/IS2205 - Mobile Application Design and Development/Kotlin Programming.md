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
## Code Example

```kotlin
val count: Int = 2 // Explicit type definition and initialization [2]
val items = 10     // Implicit type definition (Type inference) [2]

var score = 1      // Mutable variable [1]
score = score + 1  // Updating the value [1]
score++            // Incrementing the value [1]
```
# Data Types

- **Core Types:** Includes **String** (text), **Int** (integers), **Double** (decimal), **Float** (less precise decimal), and **Boolean** (true/false).
- **No Primitive/Wrapper Distinction:** Unlike Java, Kotlin does not differentiate between primitive types (like `int`) and wrapper classes (like `Integer`). This eliminates the need for explicit boxing and unboxing.
# Null Safety: A Key Feature

One of Kotlin's primary goals is to eliminate **Null Pointer Exceptions (NPE)**.

- **Non-Nullable by Default:** Variables cannot be null unless explicitly specified.
- **Safe Call Operator (****?****):** Placing a `?` after a type (e.g., `String?`) allows that variable to hold a null value.
- **Elvis Operator (****?:****):** Used to provide a default value if an expression evaluates to null (e.g., `val length = name?.length ?: -1`).
## Code Example

```kotlin
var name: String? = "John" // The '?' makes this variable nullable [4]

// Safe call operator (?.) checks for null before accessing a property [4, 5]
val length = name?.length 

// Elvis operator (?:) provides a default value if the result is null [6]
val displayLength = name?.length ?: -1 
```
# Functions

- **Syntax:** Functions are declared using the `fun` keyword. The common syntax is: `fun functionName(parameter: Type): ReturnType { ... }`.
- **Named & Default Arguments:** Kotlin supports **default values** for parameters, allowing you to call functions without passing every argument. You can also use **named arguments** to make code more readable.
- **Naming Convention:** Function names should be in **camelCase** and are typically verbs or verb phrases.

## Code Example

```kotlin
// Basic function syntax: fun name(parameter: Type): ReturnType [10]
fun addNumbers(x: Int, y: Int): Int {
    return x + y
}

// Function with default arguments [8]
fun greet(greeting: String = "Good day", name: String = "User") {
    println("$greeting $name")
}

fun main() {
    greet() // Uses defaults: "Good day User" [8]
    greet(name = "Saman", greeting = "Ayubowan") // Using named arguments [9]
}
```

# Control Flow

- **if** **Expression:** In Kotlin, `if` can be an **expression** that returns a value, serving as a replacement for the traditional ternary operator found in Java/C++.
- **when** **Expression:** This is a powerful replacement for the `switch` statement. it matches its argument against all branches sequentially until some branch condition is satisfied.
- **Loops:** Supports standard **while** and **do-while** loops. The **for** loop is used to iterate over anything that provides an iterator, such as ranges or arrays.
## Code Example

```kotlin
val age = 17
// 'if' as a replacement for the ternary operator [6, 11]
val decision = if (age < 18) "No" else "Yes" [11]

val number = 3
// 'when' expression replaces the traditional switch statement [12]
val result = when (number) {
    1 -> "Foo"
    2 -> "Bar"
    3 -> "Whiz"
    else -> "Invalid" // 'else' is mandatory in when expressions [12]
}
```

# Arrays and Ranges

- **Arrays:** Created using `arrayOf()`. Elements can be accessed or replaced using bracket notation (e.g., `cars = "BMW"`).
- **Ranges:** Defined using `..` (e.g., `1..10`). You can iterate in reverse using `downTo` and control the increment size with `step`.
## Code Example

```kotlin
val cars = arrayOf("Toyota", "Honda", "Nissan") // Creating an array [13]
cars = "BMW" // Replacing an element [13]

// For loop with a range [14]
for (num in 0..10) { // Ascending: 0 to 10 [14]
    println(num)
}

// For loop with 'downTo' and 'step' [14, 15]
for (i in 10 downTo 2 step 2) { // 10, 8, 6, 4, 2 [14, 15]
    println(i)
}

// Checking if an item exists in an array [16]
if ("Honda" in cars) {
    println("It's here!")
}
```

# Object-Oriented Programming (OOP)

- **Classes & Objects:** Classes are defined with the `class` keyword, and objects are instantiated without the `new` keyword (e.g., `val c1 = Car()`).
- **Constructors:** A **primary constructor** can be defined in the class header. Initialization logic is placed inside **init** **blocks**.
- **Inheritance:** Classes are **closed by default**. To allow a class to be inherited, it must be marked with the **open** keyword.
## Code Example
```kotlin
// Class with primary constructor [17]
open class Vehicle(var brand: String) { // 'open' allows inheritance [19]
    init {
        println("Initializing a $brand") // Executed when object is created [17, 18]
    }
    
    fun drive() { println("Vroom!") } // Member function [18]
}

// Inheritance syntax [19]
class Car(brand: String, var model: String) : Vehicle(brand) {
    fun showDetails() {
        println("Brand: $brand, Model: $model") // brand is inherited [19]
    }
}

fun main() {
    val myCar = Car("Toyota", "Aqua") // No 'new' keyword required [17]
    myCar.drive() 
}
```

# Exception Handling

- Kotlin uses **try**, **catch**, and **finally** blocks to handle exceptions.
- You can manually throw an exception using the **throw** keyword (e.g., `throw IllegalStateException("Error")`).
## Code Example

```kotlin
fun divide() {
    try {
        val result = 10 / 0
    } catch (e: ArithmeticException) {
        println("Divide by zero is not allowed") // Catches specific errors [20]
    } finally {
        println("Operation finished") // Always executes [21]
    }
}

// Manually throwing an exception [21]
fun checkParam(arg: String?) {
  
```