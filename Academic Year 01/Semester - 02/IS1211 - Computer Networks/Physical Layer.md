> [!TIP] Overview
> **Physical Layer**, is the lowest layer in the network architecture and is responsible for moving individual **bits** from one node to the next over a physical communication link.

---
# 1. Signals and Wave-forms

Data is transmitted through physical media using signals, which can be either **analog** (continuous) or **digital** (discrete).

- **Sine Waves:** The sources describe the sine wave (sinusoid) as a fundamental periodic signal characterized by:
    - **Amplitude:** The peak strength of the signal.
    - **Frequency $(f)$:** The number of cycles per second, measured in Hertz (Hz). It is the inverse of the Period $(T)$, so $f=1/T$.
    - **Phase:** The position of the waveform relative to time zero.
    - **Wavelength $(λ)$:** The physical distance a wave occupies in one cycle, calculated as $λ=c/f$ (where c is the propagation speed).
- **Signal Impairments:** Signals can be affected by **attenuation** (loss of strength), **delay**, and **noise** (interference).

# 2. Theoretical Limits on Data Rate

The sources highlight two critical mathematical laws that determine how fast data can be sent over a channel:

- **Nyquist’s Theorem:** For a **noiseless** channel, the maximum data rate (R) is determined by the bandwidth $(H)$ and the number of signal levels $(L)$: $$R=2H\log_2​L$$
- **Shannon’s Law:** For a **noisy** channel, the capacity is limited by the signal-to-noise ratio $(S/N)$: $$R=H\log_2​(1+S/N)$$

# 3. Transmission Media

The Physical Layer utilizes various types of "guided" (wired) and "unguided" (wireless) media:

## Wired Connections

- **Unshielded Twisted-Pair (UTP):** The most common copper cable. It uses **cancellation** (twisting wires) to reduce interference. It is categorized into levels (e.g., **Cat 5, Cat 6, Cat 8**) based on bandwidth capacity.
    - **Connectors:** Uses **RJ45** jacks.
    - **Wiring:** Can be **straight-through** (standard) or **crossover** (connecting similar devices).
- **Shielded Twisted-Pair (STP):** Includes extra shielding for better protection against interference.
- **Coaxial Cable:** Uses a central conductor and a shield; common connectors include **BNC** and **F-type**.
- **Fiber Optic:** Transmits data as light pulses through glass or plastic fibers.
    - **Types:** **Single-mode** (long distance, laser-based) and **Multi-mode** (shorter distance, LED-based).
    - **Advantages:** It is completely **immune to EMI** (Electromagnetic Interference) and provides much higher bandwidth than copper.

## Wireless Connections

- **Radio:** Omnidirectional, travels long distances, and penetrates buildings easily.
- **Microwave:** Travels in straight lines and requires **accurate alignment** between antennas; it does not pass through buildings.
- **Infrared:** Short-range communication that cannot pass through solid objects (e.g., TV remotes).
- **Light Transmission (Li-Fi):** Uses LED lamps and visible light for wireless communication.

# 4. Encoding and Synchronization

To ensure a receiver can correctly interpret bits, the Physical Layer uses **Encoding**:

- **The Synchronization Problem:** If the sender's and receiver's clocks are even slightly different, they will eventually lose track of the bits.
- **Manchester Encoding:** Solves this by ensuring a **transition occurs at the middle of every bit period**. This allows the receiver to stay synchronized with the sender's clock.

# 5. Hardware and Standards

- **Network Interface Card (NIC):** The physical hardware (like an Ethernet or Wi-Fi card) that connects a computer to the transmission medium.
- **Standardization:** Organizations like **ISO** and **IEEE** (e.g., IEEE 802.11 for Wi-Fi) define the electrical and mechanical specifications of the Physical Layer to ensure different devices can communicate.