# What is Jetpack Compose?

- **Definition:** A modern UI library for Android development that uses **composable functions** as its basic building blocks.
- **Declarative vs. Imperative:**
    - **Imperative (Traditional XML):** You manually mutate a tree of View components using methods like `findViewById()` or `setText()`.
    - **Declarative (Compose):** You formulate the UI as an immutable function that **automatically updates** whenever the underlying data changes.
# Composable Functions

- **Annotations:** To define a UI component, you must use the **@Composable** annotation. This attaches metadata that the Jetpack Compose compiler understands.
- **Naming Convention:** Unlike standard functions (verbs in camel-Case), composables are typically **nouns in Pascal-Case** (e.g., `SubmitButton`).
- **Functionality:** They take inputs (parameters), do not return a value, and are responsible for describing a specific part of the UI.
# Structural Containers (Layouts)

Compose replaces traditional View-groups with lightweight structural composables:

- **Column:** Arranges elements in a **vertical axis** (replaces vertical `LinearLayout`).
- **Row:** Arranges elements in a **horizontal axis** (replaces horizontal `LinearLayout`).
- **Box:** Stacks elements **on top of each other** in the z-axis (replaces `FrameLayout`).
- **ConstraintLayout:** Used for complex boundaries to flatten layout trees and reduce nesting.
# Styling with Modifiers

Compose uses the **Decorator Pattern** to handle styling rather than inline XML attributes.

- **The Modifier Chain:** You chain `Modifier` instances to set padding, width, background, and more.
- **Sequential Ordering:** Modifiers are processed **strictly sequentially**. For example, setting padding before a background will yield a different visual result than setting a background before padding.

# Integrated Previews

- **@Preview** **Annotation:** You can view your UI directly in the IDE without running the app on a device or emulator.
- **Dynamic Settings:** By adding parameters to the annotation (e.g., `@Preview(showBackground = true, showSystemUi = true)`), you can see how the UI looks in various contexts.
# Event Handling and State Hoisting

- **Decoupling:** In Compose, UI elements typically do not hold or modify their own data.
- **State Hoisting:** Components accept a **data state value** as a parameter and expose execution events (like a button click) upward as **Kotlin lambdas**. This makes the View decoupled from the control logic and highly reusable.