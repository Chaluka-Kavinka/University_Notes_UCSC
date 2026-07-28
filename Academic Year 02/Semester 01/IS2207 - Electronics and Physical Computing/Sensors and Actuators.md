This topic explores the critical components that allow a physical computing system to interact with the world. While sensors allow a system to **sense** or perceive its environment, actuators enable it to **act** or perform physical tasks based on those perceptions.

# 1. The Physical Computing Interaction Loop

A physical computing system typically follows a "Sense-Process-Act" cycle:

- **Input (Sensing):** Sensors gather data from the environment.
- **Processing:** A microcontroller (like an Arduino or ESP32) receives this data, applies logic, and makes decisions.
- **Output (Acting):** Actuators perform a physical action, such as turning on a light, moving a motor, or displaying a message.

# 2. Sensors: Perceiving the Environment

Sensors convert a physical phenomenon (like heat, light, or pressure) into an electrical signal that a microcontroller can understand.

## Classification of Sensors

- **Based on Energy Source:**
    - **Active Sensors (Self-generating):** These generate electrical signals without needing an external power source (e.g., Thermocouples, Piezoelectric sensors).
    - **Passive Sensors:** These require an external voltage or current source to operate. Most sensors used with Arduino/ESP32, such as LDRs or thermistors, are passive.
- **Based on Output Signal:**
    - **Analog Sensors:** Produce a continuous voltage signal proportional to the measurement (e.g., LM35 temperature sensor, LDR light sensor, Potentiometers).
    - **Digital Sensors:** Produce binary outputs (0 or 1) or transmit data via communication protocols (e.g., DHT22 for humidity, PIR for motion detection).
- **Based on Contact:**
    - **Contact Sensors:** Require physical contact with the object being measured (e.g., Push buttons, strain gauges).
    - **Non-contact Sensors:** Detect objects or phenomena from a distance (e.g., HC-SR04 Ultrasonic sensors, Infrared sensors).

## Key Sensor Examples and Applications

- **Temperature & Humidity:** Sensors like the **DHT22** or **LM35** are used for environmental monitoring.
- **Distance/Proximity:** The **HC-SR04** uses "Time-of-Flight" sensing by emitting ultrasonic waves to measure distance.
- **Motion:** **PIR (Passive Infrared)** sensors trigger alarms or lights when they detect movement.
- **IMU (Inertial Measurement Units):** Devices like the **MPU6050** combine accelerometers and gyroscopes to track orientation and movement in 3D space.

# 3. Actuators: Performing Physical Actions

Actuators take electrical signals from the microcontroller and convert them into physical action, such as motion, sound, or light.

## Classification of Actuators

- **Based on Motion:**
    - **Rotary:** Produce rotational movement (e.g., DC motors, Servo motors, Stepper motors).
    - **Linear:** Produce straight-line motion (e.g., Solenoids, linear actuators).
- **Based on Function:**
    - **Visual:** Provide feedback via light or displays (e.g., LEDs, LCDs, OLEDs).
    - **Audio:** Generate sound (e.g., Buzzers, speakers).
    - **Switching:** Control high-power circuits (e.g., Relays, Solid State Relays).

# Key Actuator Examples

- **Servo Motors (e.g., SG90):** These allow for precise **position control** using Pulse Width Modulation (PWM), often used in robotics for steering or arm movement.
- **DC Motors:** Used for continuous rotation where speed and direction control are needed, often requiring a **motor driver** (like the L298N) because microcontrollers cannot provide enough current directly.
- **Relay Modules:** Act as electrically operated switches, allowing a low-power microcontroller signal to control high-voltage appliances like lamps or heaters.
- **Solenoids:** Electromechanical devices that produce linear motion, commonly used for electronic door locks.

# 4. Interfacing Considerations

When connecting these devices to an Arduino or ESP32, several technical factors must be addressed:

- **Signal Conditioning:** Raw sensor signals may need to be amplified or filtered before being read.
- **Communication Interfaces:** Devices talk to the microcontroller using various protocols:
    - **Analog:** Read via an Analog-to-Digital Converter (ADC).
    - **I²C / SPI:** Used for digital sensors and displays to share data over a bus.
    - **UART:** Serial communication for GPS or wireless modules.
- **Driver Circuits:** High-power actuators (motors, solenoids) require separate power supplies and driver circuits to prevent damage to the microcontroller.
- **PWM (Pulse Width Modulation):** A technique used to control the average power delivered to an actuator, such as dimming an LED or setting a servo's angle.