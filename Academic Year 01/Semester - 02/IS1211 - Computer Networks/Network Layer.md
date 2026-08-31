> [!TIP] Overview
> **Network Layer**, is the third layer of the OSI model and the second layer of the TCP/IP suite (where it is called the Internet Layer). Its primary function is **internetworking**, which involves moving data across multiple networks and finding the best path from a source to a destination.

---
# 1. IP Addressing

Every device on a network requires a unique identifier.

- **Structure:** An IP address (specifically IPv4) is a **32-bit binary number**.
- **Representation:** For easier human reading, these 32 bits are divided into four **octets** (8 bits each) and expressed in **dotted decimal notation** (e.g., 192.248.16.2).
- **Network vs. Host:** An IP address is logically divided into two parts: the **Network Address** (identifying the specific network) and the **Host Address** (identifying the specific device on that network).
# 2. Routing and Forwarding

The Network Layer is responsible for determining how a packet gets from its source to its destination across an "internet" of connected LANs.

- **Routers:** These are specialized devices that connect multiple networks and have multiple IP addresses (one for each connected interface).
- **Routing Tables:** Routers maintain tables that list possible **destinations**, the **next hop** (the next router in line), and the **cost** (metric) associated with that path.
- **Routing Protocols:** These are sets of rules used by routers to communicate with each other and dynamically discover the best paths.
# 3. Sub-netting and Masks

Sub-netting allows a large network to be divided into smaller, manageable sub-networks.

- **Network Mask:** A bitmask (like 255.255.255.0) used to determine which part of an IP address is the network portion and which is the host portion.
- **CIDR Notation:** A compact way to represent a mask by counting the number of leading 1-bits (e.g., **/24** represents a mask with 24 ones).
- **Network Address:** The first address in a block, where all host bits are 0.
- **Broadcast Address:** The last address in a block, used to send data to every device on that specific sub-network, where all host bits are 1.
# 4. Supporting Protocols

Several protocols work alongside IP at this layer:

- **ARP (Address Resolution Protocol):** Used to discover the hardware (MAC) address of a node when only its IP address is known.
- **NAT (Network Address Translation):** Allows multiple devices on a private network to share a single public IP address by translating internal source addresses and ports to public ones for internet access.
# 5. Data Encapsulation (PDU)

- **Protocol Data Unit:** At this layer, data is encapsulated into an **IP Datagram** or **Packet**.
- **Encapsulation Process:** When receiving a "Segment" from the Transport Layer, the Network Layer adds an **IP Header** containing source and destination IP addresses before passing it down to the Data-link Layer.
# 6. Practical Application (Labs)

In the module's practical components, students apply these concepts by:

- **Configuring IPs:** Setting manual IP addresses on Windows and Linux machines.
- **Routing Setup:** Configuring a "middle machine" with two network interfaces to act as a router and enable **packet forwarding** between two isolated machines.
- **Connectivity Testing:** Using the `ping` command to verify end-to-end communication between different subnets.