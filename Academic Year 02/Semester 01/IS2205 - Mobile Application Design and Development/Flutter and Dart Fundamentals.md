# 1. Introduction to Flutter

- **Definition:** Flutter is an **open-source UI toolkit** created by Google for building natively compiled applications for mobile, web, and desktop from a **single codebase**.
- **Core Philosophy:** It aims to provide high performance and UI consistency across different platforms.
- **Architecture:** The system is built on a layered architecture consisting of the **Framework** (Widgets), the **Engine** (C++ core), and the **Embedder** (platform-specific integration).

# 2. Getting Started with a Project

You can create a new Flutter project in two primary ways within your development environment:

- **VS Code Command Palette:** Use the command **>flutter new** to initiate a project through the interface.
- **Terminal/Command Line:** Execute the command **flutter create <project_name>** (e.g., `flutter create flutter1`).
- **Running the App:** Once created, you can launch the application by typing **flutter run** in the terminal or by using the VS Code "Run" interface.

# 3. Flutter Project Structure

Understanding the directory hierarchy is essential for managing your code and assets:

- **lib/** **Folder:** This is the most important directory for developers, as it contains the **source code** for the application.
    - **main.dart****:** The entry point of your Flutter application.
- **android/** **Folder:** Contains files parallel to a **native Android application**, allowing for platform-specific configurations.
- **ios/** **Folder:** Contains files similar to an **Xcode project** for iOS-specific settings.
- **test/** **Folder:** Dedicated space for writing and running **developer tests**.
- **pubspec.yaml****:** The central configuration file used to manage **app dependencies**, versions, and metadata.
- **analysis_options.yaml****:** Used to configure how static code analysis tools evaluate the project.
- **.gitignore****:** Essential for source management to exclude specific files from version control.

# 4. Dart Programming Fundamentals

Flutter applications are written in **Dart**, a language designed for fast-performing apps on any platform.

- **Nature:** Dart is **strongly-typed yet flexible**, providing a balance between safety and developer productivity.
- **Features:** It includes modern language features such as **null safety** and the ability to compile directly to native ARM code or JavaScript.
- **Entry Point:** Every Flutter app begins execution at the **main()** function, typically found in `lib/main.dart`.

# 5. The "Single Activity" Model

A key difference between native Android and Flutter is how they handle screen containers:

- **FlutterActivity****:** Unlike native development where every screen might be a new Activity, a Flutter app typically runs inside a **single native container** called `FlutterActivity`.
- **Internal Routing:** The Flutter framework manages its own **routing, state, and rendering** entirely within that one native window.