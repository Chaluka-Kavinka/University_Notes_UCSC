>Next Topic : [[Kotlin Programming]]

# What is Mobile Computing?

- **Definition:** A technology that facilitates the **processing and transmission of data** via a computer or wireless-enabled device without being stationed or connected to a fixed physical link.
- **Core Utility:** It allows users to access information from **portable devices** in both **connected and disconnected modes**.
- **Connectivity:** While primarily wireless, some mobile devices still support physical (wired) network connectivity.
# The Three Main Ingredients

Mobile computing is composed of three essential pillars:

1. **Mobile Communication:** The infrastructure and protocols for data exchange.
2. **Mobile Hardware:** The physical devices and internal components.
3. **Mobile Software:** The operating systems and applications that run on the hardware.

# Mobile Communication & Network Progress

- **Services:** Includes mobile data/voice, Wi-Fi, Infrared (IR), Bluetooth, RFID, and GPS.
- **Evolution of Speed:**
    - **3G (2001):** 384 Kbps. A 2-hour movie download would take **26 hours**.
    - **4G (2009):** 100 Mbps. The same movie download takes **6 minutes**.
    - **5G (2020):** 10 Gbps. The download completes in just **3.6 seconds**.

# Mobile Hardware & Sensors

- **Computing Power:** Modern mobile phones are no longer just communication tools; they provide **high-performance processors, GPUs**, and large flash memory (typically around 100GB).
- **Sensors:** An average smartphone has at least **10 sensors**, including the Accelerometer, Gyroscope, Magnetometer, Proximity sensor, and Thermometer.
- **Market Share (Global):** As of March 2026, **Apple (27.55%)** and **Samsung (21.27%)** lead the vendor market. In the smartwatch market, Apple dominates with **30% of global shipments**.

# Mobile Software & App Development

- **Operating Systems:** Globally, **Android (~71%)** holds the majority share over **iOS (~28%)**. However, in the **USA**, iOS leads with **~58.7%**.
- **Development Philosophy:** Developers often choose Android first because the **Google Play Store has fewer restrictions** than Apple. Conversely, iOS is favored for **higher user retention** and fewer devices to support.
- **Types of Applications:**
    - **Native Apps:** Built for specific platforms (Java/Kotlin for Android, Swift for iOS). They offer the **best performance** and full device feature access but are **expensive to maintain**.
    - **Web Apps:** Built with HTML5/CSS/JS. They are **easier to maintain** and work on all devices but require an internet connection and have limited hardware integration.
    - **Hybrid Apps:** A middle ground between Native and Web.

# Android Platform Architecture

The Android system is organized into a specific hierarchy:

1. **Linux Kernel:** The foundation that handles low-level memory management, threading, and hardware drivers (Audio, Display, Bluetooth, etc.).
2. **Hardware Abstraction Layer (HAL):** Provides standard interfaces that allow the Java API framework to communicate with specific hardware modules without knowing the underlying driver details.
3. **Android Runtime (ART) & Native Libraries:** ART executes **DEX files** (bytecode) using **Ahead-of-Time (AOT)** and **Just-in-Time (JIT)** compilation. Native C/C++ libraries (like Webkit or OpenGL) support core system functions.
4. **Java API Framework:** The "bread and butter" for developers, providing the **View System**, **Resource Manager**, and **Activity Manager** needed to build apps.
5. **System Apps:** Core applications (Dialer, Email, Camera) that sit at the top of the stack and use the same framework APIs available to independent developers.