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
- **Utilize Intents:** Master the use of **Explicit, Implicit, and Pending Intents** to facilitate communication between your app's components and other applications.
- **Implement Broadcast Receivers:** Understand the **publish-subscribe design** to receive and respond to system-wide or custom broadcast events.
- **Integrate Hardware Sensors:** Effectively use the **Android sensor framework** to access **Motion, Environmental, and Position sensors**.
- **Manage Data Persistence:** Choose and implement appropriate storage methods, including **App-specific storage**, **Shared storage**, and structured **Databases** using the **Room persistence library**.
- **Master Flutter Persistence Strategies:** Implement and compare various storage methods like SharedPreferences, SQLite, and Firebase within a Flutter application.
- **Implement Concurrent Programming in Dart:** Utilize Future, async, and await to handle time-consuming storage operations without blocking the user interface.
- **Manage App States for Data:** Effectively use the initState() method to load persisted data and configurations when a widget is first created.
- **Integrate External Cloud Services:** Successfully connect and configure a Flutter app to use Firebase for remote data persistence.
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

6. [[Intents and Broadcast Receivers]]
	- **Intent Fundamentals:** Understanding Intents as "messengers" for requesting actions from different components.
	- **Intent Types:** Differentiating between **Explicit** (defined target), **Implicit** (action-based), and **Pending** (future-use) intents.
	- **Intent Components:** Working with **Actions, Categories, Data (MIME types), Flags, and Extras**.
	- **Broadcast Receivers:** Learning the **publish-subscribe** model for events like bootup or battery state changes.

7. [[Sensors in Android]]
	- **Sensor Categories:** Exploring **Motion sensors** (accelerometers, gyroscopes), **Environmental sensors** (temperature, humidity), and **Position sensors** (magnetometers, proximity).
	- **Sensor Framework:** Using the `SensorManager` to enumerate and acquire sensor objects.
	- **Implementation:** Handling the **Sensor Coordinate System** and using **Listeners** (`SensorEventListener`) to respond to data changes.
	- **Efficiency:** Properly **registering and unregistering listeners** in activity lifecycle methods to save power.

8. [[Persistence (Data Storage)]]
	- **Storage Strategies:** Choosing between **App-specific storage** (private), **Shared storage** (media/documents), **Preferences**, and **Databases**.
	- **Shared Storage APIs:** Utilizing the `MediaStore` API and **Storage Access Framework**.
	- **SQL and SQLite:** Basic database concepts like **Tables, Rows, and Columns**, and using **SQL** for CRUD (Create, Read, Update, Delete) operations.
	- **Modern Persistence with Room:** Using the **Room library** to replace boilerplate code with **Entities**, **DAOs (Data Access Objects)**, and **Databases**.

9. [[Flutter and Dart Fundamentals]]
	- **Introduction to Flutter:** Understanding Flutter as Google’s open-source UI toolkit for building natively compiled applications for mobile (Android/iOS), web, and desktop from a **single codebase**.
	- **Flutter Layered Architecture:** Exploring the system hierarchy composed of the **Framework** (Widgets, rendering), the **Engine** (C++ core, graphics), and the **Embedder** (platform-specific integration).
	- **Introduction to Dart Programming:** Mastering a modern, object-oriented language that is **strongly typed yet flexible**, featuring null safety and efficient compilation to native ARM or JavaScript.
	- **Project Structure and Management:** Learning to create projects via terminal or IDE and managing essential files like **main.dart** for source code and **pubspec.yaml** for app dependencies and metadata.

10. [[Advanced Flutter Concepts]]
	- **The Widget System:** Building complex user interfaces by composing basic, reusable components called **Widgets** into a hierarchical **Widget Tree**.
	- **Declarative UI Paradigm:** Shifting to a modern framework where the **UI is a function of state**, and widgets automatically describe their view based on current configurations and data.
	- **Native Container Management:** Analyzing the **"Fate of Activities"** in Flutter, where the entire application typically runs inside a single native container called **FlutterActivity**.
	- **Stateless and Stateful Widgets:** Categorizing UI components into immutable **Stateless** widgets for static content and dynamic **Stateful** widgets that can change appearance over time.

11. [[Persistence with Flutter]]
	- **Storage Methods in Flutter:** Learning to choose the right tool for the job, from simple key-value pairs in **SharedPreferences** to structured local databases with **SQLite (sqflite)** and in-memory options like **Hive**.
	- **Dart Concurrency:** Understanding the "Need for Speed" by using the **async** and **await** keywords alongside the **Future** class to manage background tasks.
	- **Stateful Persistence:** Leveraging the **StatefulWidget** lifecycle to maintain state and perform initial data loads before the UI is rendered.
	- **Cloud Integration with Firebase:** Mastering the setup process, including web console configuration, managing **google-services.json**, and handling the necessary dependencies in **pubspec.yaml**.
	- **Advanced Implementation:** Working with **Enums** to create clean, manageable code for switching between different data sources.