>Next Topic : [[Persistence (Data Storage)]]
---
# 1. Categories of Android Sensors

Android sensors are used to add capabilities to mobile computers that desktops or servers typically lack. They are broadly categorized into three groups:

- **Motion Sensors:** Measure acceleration and rotational forces along three axes. Examples include **accelerometers**, **gravity sensors**, and **gyroscopes**.
- **Environmental Sensors:** Measure parameters like ambient air temperature, pressure, illumination, and humidity. Examples include **barometers**, **photometers**, and **thermometers**.
- **Position Sensors:** Measure the physical orientation or position of a device. Examples include **magnetometers** and **proximity sensors**.

# 2. Hardware vs. Software Sensors

- **Hardware Sensors:** These are physical components built directly into the device that measure specific parameters (e.g., an accelerometer measuring geomagnetic field strength).
- **Software (Virtual) Sensors:** These are not physical components but instead derive their data from one or more hardware sensors. Common examples are the **linear acceleration** or **gravity sensors**.

# 3. The Sensor Coordinate System

Most Android sensors use a standard **3-axis coordinate system** relative to the device's screen when held in its default orientation:

- **X-axis:** Horizontal and points to the right.
- **Y-axis:** Vertical and points up.
- **Z-axis:** Points toward the outside of the screen face (coordinates behind the screen have negative Z values).

# 4. Accessing Sensors via the Framework

To interact with sensors, developers use the **Android sensor framework**, which consists of four key classes:

- **SensorManager****:** The main entry point to create an instance of the sensor service, list available sensors, and register/unregister listeners.
- **Sensor****:** Used to create an instance of a specific sensor and identify its individual capabilities (range, power requirements, etc.).
- **SensorEvent****:** A system-generated object that provides raw sensor data, the sensor type, data accuracy, and a timestamp.
- **SensorEventListener****:** An interface used to create callback methods—`onSensorChanged()` and `onAccuracyChanged()`—to receive notifications when sensor data or accuracy changes.

# 5. Best Practices and Efficiency

Because sensors can be resource-intensive, following these practices is crucial:

- **Register/Unregister Listeners:** Always register your listener in `onResume()` and **unregister it in** **onPause()**. This prevents the sensor from draining the battery while the activity is not visible.
- **Lightweight Callbacks:** Since `onSensorChanged()` is called frequently (sometimes hundreds of times per second), do as little work as possible inside this method to avoid blocking the system.
- **Verify Sensor Existence:** Never assume a sensor exists. Always verify its availability on the device before attempting to acquire data.
- **Foreground Only:** On Android 9 (API 28) and higher, background apps have restrictions on reporting sensor events to protect user privacy.

# 6. Emulating Sensors

Android Studio’s emulator allows you to test sensor functionality without a physical device using the **Virtual Sensors Control Panel**:

- **Device Pose:** You can click and drag a 3D phone model to simulate rotating, spinning, or tilting the device.
- **GPS Movement:** The emulator allows you to mark places on an interactive map or import `.gpx` files to simulate moving along a real-world path.