- **Course Code** : IS 2205
- **Course Name** : Mobile Application Design and Development
- **Lecture** : Mr. Dasun Bamunuarachchi (dtb@ucsc.cmb.ac.lk)

#Lesson-Plan 


> [!important] Goal
> The primary goal of this course is to provide a comprehensive foundation in **designing and developing mobile applications**, with a specific focus on the **Android platform** using both traditional XML-based layouts and modern **Jetpack Compose** frameworks.

---
# Intended Learning Objectives

By the end of these lessons, you should be able to:
- **Develop Android Apps:** Comfortably build a minimal Android app with a simple user interface.
- **Master Kotlin:** Understand and apply Kotlin programming concepts, including its syntax, null safety, and Object-Oriented Programming (OOP) features.
- **Analyze Android Architecture:** Explain the Android platform architecture (Linux kernel, HAL, ART) and how activities function from a programming perspective.
- **Manage App States:** Explain the **Activity Life-cycle**, including how to manage state transitions and navigate the **Back Stack** and tasks.
- **Design User Interfaces:** Transition from traditional **XML markup** to modern **declarative UI** using Jetpack Compose.
- **Utilize Development Tools:** Use Android Studio, manage project structures, and handle build automation with **Gradle**.
---
# Topic Covered

1. [[Introduction to Mobile Computing]]
	- **Concepts:** Definition of mobile computing, communication progress (3G to 5G), and mobile hardware/sensors.
	- **Market Overview:** Global OS market shares (Android vs. iOS) and the pros/cons of Native, Web, and Hybrid apps.
	- **Android Architecture:** The hierarchy of the Android platform, including the Linux Kernel, Hardware Abstraction Layer (HAL), Android Runtime (ART), and the Java API Framework.

2. [[Kotlin Programming]]
	- **Fundamentals:** Variables and values (`var` vs. `val`), powerful type inference, and statically-typed nature.
	- **Safety Features:** Kotlin’s default non-nullability and the **Safe Call Operator (?)** to prevent null pointer exceptions.
	- **Syntax & Control Flow:** Functions (declaration vs. definition), String templates, logical/comparison operators, and the `when` expression.
	- **Data Structures & OOP:** Using Arrays, Ranges, and loops (`for`, `while`, `do-while`) alongside core OOP concepts like **Classes, Objects, Constructors, and Inheritance**.
	- **Exception Handling:** Using `try-catch-finally` blocks and throwing exceptions.

3. [[Android Application Project Elements]]
	- **Tools:** Setting up Android Studio, using the **Android Virtual Device (AVD) Manager**, and choosing API levels (min vs. target SDK).
	- **Project Structure:** Understanding the `app` directory, `res` (resources), and Gradle scripts (`build.gradle.kts`).
	- **UI Basics:** Introduction to **Views** (Text-view, Button) and **View-groups** (Linear-layout, Constraint-layout) defined via XML.

4. [[Activity Life Cycle]]
	- **Task Management:** How Android identifies the "main" activity in the **Manifest** and how the **Back Stack** manages activity instances.
	- **The Life-cycle:** Detailed study of states (**Created, Started, Resumed, Paused, Stopped, Destroyed**) and their corresponding callback methods like `onCreate()`, `onStart()`, and `onPause()`.
	- **State Persistence:** Using `onSaveInstanceState()` and `onRestoreInstanceState()` to handle force-killed instances.

5. [[Modern UI with Jetpack Compose]]
	- **Declarative UI:** Shifting from XML to **Composable functions** annotated with `@Composable`.
	- **Structural Composables:** Using **Column, Row, and Box** instead of traditional View-groups.
	- **Styling:** Applying the **Decorator Pattern** using **Modifiers** to handle padding, size, and background.
	- **State Hoisting:** Decoupling UI elements from control logic by exposing events via Kotlin lambdas.