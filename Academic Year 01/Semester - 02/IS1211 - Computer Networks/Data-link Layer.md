> [!TIP] Overview
> **Data-link Layer**, is the second layer in the OSI reference model and the first layer in the TCP/IP Network Interface layer. Its primary responsibility is to **move a datagram from one node to an adjacent node** over a single communication link.

---
# 1. Services Provided

The Datalink Layer provides several essential services to ensure data is moved efficiently and accurately across a link:

- **Framing:** Encapsulating network-layer datagrams into a "Data Frame" by adding a header and a trailer.
- **Link Access:** Managing how a node gains access to the medium to transmit data.
- **Reliable Delivery:** Ensuring the frame arrives at the next node without error.
- **Error Detection and Correction:** Mechanisms to identify bit-level errors caused by signal attenuation or noise. Common methods include:
	- **Parity Bits:** Adding a bit to make the total number of 1s even or odd. Single parity can detect one error but **cannot detect two errors** occurring simultaneously.
	- **Error Detecting Codes:** Using bit patterns (like 0⇒00 and 1⇒11) to reduce the probability of wrong decoding.
# 2. Link-Layer Channels

Communication links at this layer are generally classified into two types:

- **Point-to-Point Links:** A direct connection between two specific nodes or terminals.
- **Broadcast Channels:** Multiple nodes are connected to a single shared communication medium (like a **Bus topology**) where they must coordinate access.
# 3. Multiple Access (MAC) Protocols

When nodes share a broadcast channel, they use MAC protocols to avoid collisions:

- **Aloha:** A simple "just transmit" approach. If a collision occurs, the node waits a **random amount of time** before attempting to retransmit.
- **CSMA (Carrier Sense Multiple Access):** The node **listens before transmitting**. If the channel is sensed as free, it transmits; otherwise, it waits.
- **CSMA/CD (Collision Detection):** The node listens while transmitting and **stops immediately** if a collision is detected, then waits a random time to retry.
# 4. Multiplexing (Channel Partitioning)

To allow multiple users to share a medium simultaneously, the layer uses partitioning protocols:

- **TDM (Time Division Multiplexing):** Nodes are assigned specific **time slots** to transmit.
- **FDM (Frequency Division Multiplexing):** The total bandwidth is divided into different **frequency bands** for each user.
- **CDMA (Code Division Multiple Access):** Each node is assigned a unique **code**, and transmitted bits are multiplied by this code to distinguish them from other signals.
# 5. Ethernet Standards

Ethernet is the most common technology for wired LANs. The sources differentiate between **Classic Ethernet** and **Switched Ethernet**.

- **Properties:** Ethernet is **connectionless and unreliable**, meaning it does not use handshakes or acknowledgments at this layer.
- **Frame Structure:**
	- **Preamble (8 bytes):** For synchronization.
	- **Hardware Addresses (6 bytes each):** Source and Destination MAC addresses.
	- **Type (2 bytes):** Indicates the network-layer protocol.
	- **Data (Payload):** Ranges from a minimum of **46 bytes** to a maximum of **1500 bytes (MTU)**.
	- **FCS/Checksum (4 bytes):** Used for error detection.
# 6. Network Hardware and PDUs

- **Protocol Data Unit (PDU):** The PDU at this layer is called a **Data Frame**.
- **Devices:** The **Unmanageable Switch** is a key hardware component that operates at the Datalink Layer. In practical labs, students use switches to connect Linux computers and check connectivity via the `ping` command.
- **ARP (Address Resolution Protocol):** This protocol is used to map an IP address to its corresponding hardware (MAC) address to facilitate delivery across the link.