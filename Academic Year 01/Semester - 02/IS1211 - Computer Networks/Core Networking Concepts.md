> [!INFO]
> **Core Network Concepts**, provides the foundational theory required to understand how information travels through a network. Based on the provided sources, this topic covers the following key areas:

---
# 1. Data Communication Fundamentals

At its most basic level, networking is about data communication, which involves several critical concepts:

- **Symbols and Messages:** Information is represented using symbols. For example, light signals can use two different colors to represent binary states (0 and 1) to convey messages like "We won" or "We lost".
- **Bit Rate vs. Baud Rate:** Bit rate refers to the number of **bits transmitted per second**, while baud rate refers to the number of **symbols transmitted per second**.
- **Encoding:** This is the pattern used to represent digital information. A key method discussed is **Manchester Encoding**, which ensures there is a transition at the middle of each bit period to help keep sender and receiver clocks synchronized.

# 2. Protocols

Protocols are sets of rules that define how messages are transmitted over a network. They govern several aspects of communication:

- **What they define:** Message encoding, encapsulation, size, timing (flow control and response timeouts), and delivery methods.
- **Delivery Methods:** These include **Unicast** (one-to-one), **Multicast** (one-to-many), and **Broadcast** (one-to-all).
- **Types of Protocols:**
    - **Communication:** IP, TCP, HTTP.
    - **Security:** SSH, SSL, TLS.
    - **Routing:** OSPF, BGP.
    - **Service Discovery:** DHCP, DNS.

# 3. Layered Models

The module emphasizes "Layered Systems Architectures" to organize network functions. Two primary models are compared:

- **OSI Reference Model (7 Layers):** Physical, Datalink, Network, Transport, Session, Presentation, and Application.
- **TCP/IP Suite (4 Layers):** Network Interface, Internet, Transport, and Application. Layering allows different parts of a network to be designed and changed independently.

# 4. Data Encapsulation and PDUs

As data moves down through the layers of a model, it undergoes **encapsulation**, where each layer adds its own header information. This process results in different **Protocol Data Units (PDUs)** at each stage:

- **Application Layer:** Data.
- **Transport Layer:** Segment (adds Port Numbers and Sequence Numbers).
- **Network Layer:** Packet or IP Datagram (adds IP Addresses).
- **Datalink Layer:** Data Frame (adds hardware addresses and trailers).
- **Physical Layer:** Bits.

# 5. Network Topologies

Topology describes how the various nodes and terminals in a network are physically or logically connected. The core types mentioned include:

- **Point-to-Point:** A direct link between two computers or stations.
- **Mesh:** A highly interconnected network where nodes may have multiple paths to one another.
- **Star:** All nodes are connected to a single central hub.
- **Bus:** All nodes share a single communication line. In bus topologies, access is often managed through partitioning methods like **Time Division (TDMA)**, **Frequency Division (FDMA)**, or **Code Division (CDMA)**.