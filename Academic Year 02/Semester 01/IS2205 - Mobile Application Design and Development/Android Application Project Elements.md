# Essential Development Tools

To build and test Android applications, you primarily use:
- **Android Studio IDE:** The primary environment for writing and managing your app's code.
- **Android Virtual Device (AVD) Manager:** A tool within Android Studio that allows you to create and manage emulators to run your app on a virtual phone or tablet directly on your computer.
- **API Level Selection:** When starting a project, you must define:
    - **Minimum SDK:** The lowest Android version required to install the app.
    - **Target SDK:** The highest version you have tested your app against.
    - **Compile SDK:** The version of the Android OS libraries used to compile your code.
    - **Rule:** Always ensure that `minSdkVersion <= targetSdkVersion <= compileSdkVersion`.
# Project Directory Structure

An Android project is organized into several key directories and files:

- **app/** **Folder:** The core directory containing your source code, the Android Manifest, and resources.
- **res/** **(Resources):** This folder stores static content used by your code:
    - **drawable/****:** Images and graphical assets.
    - **layout/****:** XML files that define your app's user interface.
    - **mipmap/****:** App launcher icons tailored for different screen densities.
    - **values/****:** Collections of strings (for easy localization), colors, and styles.
- **Gradle Scripts:** Files like `build.gradle.kts` that define your app's dependencies, plugins, and build configurations.
# UI Building Blocks: Views and View-groups

The user interface is built using a hierarchy of components defined in XML:

- **Views:** Standalone UI elements like **Text-view** (text display), **Image-view** (images), and **Buttons**.
- **View-groups:** Containers that act as "parents" to determine how "child" views are arranged on the screen. Common types include:
    - **Linear-layout:** Aligns children in a single row or column.
    - **Frame-layout:** Typically used to hold a single child view or stack overlapping views.
    - **Constraint-layout:** A flexible container that aligns views relative to each other or the screen borders, preferred for reducing complex nested layouts.
- **Resource IDs:** You assign unique IDs to views in XML (e.g., `android:id="@+id/my_button"`) so you can reference and control them in your Kotlin code via the auto-generated **R.java** class.
# The Core Component: Activities

- **Definition:** An **Activity** is a component that provides a screen for users to interact with to accomplish a specific task.
- **Functionality:** Unlike desktop windows that are often resizable or side-by-side, Android activities are typically full-screen and operate on a "stack".
- **Inflation:** In your **MainActivity.kt**, the system calls the `onCreate()` method, which uses `setContentView()` to "inflate" your XML layout and render it on the screen.
# Build Automation with Gradle

Gradle handles the heavy lifting of turning your code into a runnable app:

- **Build Cycle:** It automates compiling sources, running tests, and installing the app on a device.
- **Dependencies:** It manages third-party libraries and project-specific settings.
- **Variants:** By default, the IDE configures a **debug** variant for development and a **release** variant for final deployment.