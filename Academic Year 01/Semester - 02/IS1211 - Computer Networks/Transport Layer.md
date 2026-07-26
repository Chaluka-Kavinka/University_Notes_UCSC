> [!TIP] Overview
> **Transport Layer**, is the fourth layer in both the OSI model and the TCP/IP suite. Its primary role is to provide **process-to-process communication**, ensuring that data from a specific application on one computer reaches the correct application on another.

---
# 1. Core Responsibilities

While the Network Layer handles delivery between hosts, the Transport Layer manages the data stream between applications. Its key functions include:

- **Segmentation:** Breaking down large application data into smaller units called **Segments**.
- **Port Addressing:** Using port numbers to identify specific processes or services.
- **Reliability:** Managing connection establishment, flow control, and congestion control to ensure data is delivered accurately and efficiently.
# 2. Port Numbers

Ports act as logical "doors" for different types of network traffic. There are a total of **65,535** possible port numbers.

- **Server-Side (Well-Known Ports):** These are standardized for specific services:
    - **20 & 21:** FTP (File Transfer Protocol).
    - **22:** SSH (Secure Shell).
    - **53:** DNS (Domain Name System).
    - **80:** HTTP (Web traffic).
    - **443:** HTTPS (Secure Web traffic).
- **Client-Side Ports:** Usually assigned dynamically starting from **1024**.

# 3. Key Protocols: TCP vs. UDP

The module compares the two main protocols used at this layer:

- **Transmission Control Protocol (TCP):** A **connection-oriented** protocol that ensures reliable delivery.
    - **Header Format:** Includes Source/Destination Ports, Sequence Numbers (for reordering data), Acknowledgment Numbers, Window size (for flow control), and a Checksum.
    - **Features:** Performs a "three-way handshake" for connection establishment and manages congestion to prevent network overload.
- **User Datagram Protocol (UDP):** A **connectionless**, "best-effort" protocol.
    - **Header Format:** Much simpler, containing only Source/Destination Ports, Length, and a Checksum.
    - **Use Case:** Ideal for applications where speed is more important than perfect reliability (e.g., streaming or DNS queries).
# 4. Protocol Data Units (PDU) and Encapsulation

- The PDU at this layer is called a **Segment** (for TCP) or a **User Datagram** (for UDP).
- During encapsulation, the Transport Layer takes data from the Application Layer and adds a **Transport Header** (containing port and sequence numbers) before passing it down to the Network Layer to become an IP Datagram.
# 5. Theoretical Challenges: The Two Army Problem

The sources introduce the **Two Army Problem** to illustrate the difficulty of reaching a perfect agreement (consensus) between two nodes over an unreliable communication link. It explains why networking protocols require mechanisms like **Acknowledgments (ACKs)** and sequence numbers to handle message loss, even though a 100% "guaranteed" common state is theoretically impossible.
# 6. Practical Application (Labs)

In **Lab 05**, students use **Wireshark** to analyze transport layer traffic. This involves:

- Examining **TCP streams** to see how data is exchanged between a client and a server.
- Identifying different protocols based on their port numbers and header structures.
- Applying display filters to isolate specific source or destination addresses within a packet capture (.pcap).