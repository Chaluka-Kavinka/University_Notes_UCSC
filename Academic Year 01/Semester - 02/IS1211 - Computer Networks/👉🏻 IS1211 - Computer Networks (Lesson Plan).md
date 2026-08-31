- **Course Code** : IS 1211
- **Course Name** : Computer Networks
- **Lecture** : Mr. Tharindu Wijethilake & Dr. Chamath Keppitiyagama

#Lesson-Plan

> [!INFO] Overview
> The primary goal of the module is to enable students to explain layered architectures, describe the functionality of various network hardware and software components, and apply IP networking concepts to solve design problems, such as IP sub-netting.
> 
> Evaluation consists of **Continuous Assessment (40%)**, which includes weekly assignments and labs, and a **Final Paper (60%)**.
> 
>Students engage in several practical laboratories, including:
>- Configuring networking in both **Windows** and **Linux (Ubuntu)** environments.
>- Setting up hardware such as **unmanageable switches** and configuring **routing** between multiple computers.
>- Performing protocol analysis using **Wireshark** to examine TCP streams and .pcap dumps.

This course provides a comprehensive foundation in the principles and practical applications of computer networking, primarily organized around the layered system architecture.

---
# Learning Objectives

The learning objectives (or outcomes) for the **IS1211 (Computer Networks)** module are focused on understanding network architecture, components, and practical application. According to the course materials, students should be able to:

- **Explain the principles** underlying layered systems architectures and how they are applied to computer networks.
- **Describe the functionality** and specific roles of various hardware and software components used within networks.
- **Apply core IP networking concepts** to solve basic network design problems, such as calculating IP sub-netting.
---
# Topics Covered

The module covers the following key areas based on the course contents and lecture notes:

1. [[Core Networking Concepts]]
	- **Layered Models:** Detailed study of the **OSI Reference Model** (7 layers) and the **TCP/IP suite** (4 layers).
	- **Data Communication Fundamentals:** Symbols, protocols, baud rate vs. bit rate, and bandwidth.
	- **Network Topologies:** Point-to-point, mesh, star, and bus topologies.
	- **Switching:** Differences between **Circuit switching** (dedicated paths) and **Packet switching** (store-and-forward).

2. [[Physical Layer]]
	- **Transmission Media:** Wired connections (UTP, STP, Coaxial, and Fiber Optic) and wireless media (Radio, Microwave, Infrared, and Li-Fi).
	- **Signals and Encoding:** Analog vs. digital signals, sine waves (amplitude, frequency, phase), and **Manchester encoding**.
	- **Theoretical Limits:** Nyquist’s Theorem for noiseless channels and Shannon’s Law for noisy channels.

3. [[Data-link Layer]]
	- **Services:** Framing, link access, reliable delivery, and error detection/correction mechanisms like **Parity** and checksums.
	- **Ethernet:** Frame structure, MTU (Maximum Transmission Unit), and the difference between classic and switched Ethernet.
	- **Multiple Access Protocols:** Random access protocols including **Aloha**, **CSMA**, and **CSMA/CD** (Collision Detection).
	- **Multiplexing:** Time Division (TDM), Frequency Division (FDM), and Code Division (CDM/CDMA).

4. [[Network Layer]]
	- **IP Addressing:** Binary representation, dotted decimal notation, and octets.
	- **Routing:** Routing tables, next-hop selection, and routing protocols.
	- **Subnetting:** Network masks, **CIDR notation** (e.g., /24), and calculating broadcast addresses.
	- **Address Resolution Protocol (ARP):** Identifying hardware addresses from IP addresses.

5. [[Transport Layer]]
	- **Protocols:** In-depth look at **TCP** (connection-oriented, flow control, congestion control) and **UDP**.
	- **Port Numbers:** Understanding well-known ports for services like HTTP (80), HTTPS (443), and DNS (53).

6. [[Application Layer & Services]]
	- **World Wide Web:** The Client-Server model, URL structures, and **HTTP/1.0 vs. HTTP/1.1** (persistent vs. non-persistent connections).
	- **HTTP Syntax:** Request methods (GET, POST, etc.), status codes (200, 404), and headers.
	- **Domain Name System (DNS):** The hierarchical structure of domain resolution.
	- **Additional Services:** Email, DHCP, and FTP.

7. [[Specialized Topics]]
	- **Network Security:** Wireless security standards (**WPA/WPA2**) and concepts of public key encryption.
	- **Internet Access Technologies:** Public Switched Telephone Network (PSTN), DSL (ADSL/SDSL), and Fiber-to-the-X (**FTTX/FTTH**) architectures.
	- **Mobile Systems:** The evolution from **1G to 5G** mobile technology.
	- **Modern Trends:** Introduction to **Software Defined Networks (SDN)**.