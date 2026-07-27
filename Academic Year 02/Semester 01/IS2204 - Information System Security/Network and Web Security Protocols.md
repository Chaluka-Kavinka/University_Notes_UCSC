# 1. Web Security vs. Network Security

A fundamental distinction is made between these two domains:

- **Web Security:** Typically focuses on protecting a single application—the web browser—talking to a server (e.g., using **TLS/HTTPS**).
- **Network Security:** Protects everything below the application layer, including routing, name resolution, and the raw connection itself, often through protocols that are transparent to the user.

# 2. Transport Layer Security (TLS)

TLS, formerly known as **SSL (Secure Sockets Layer)**, is the protocol layer that provides privacy, integrity, and authentication for internet applications.

- **Evolution:** Originally developed by Netscape as SSL (1994), it evolved into the IETF standard TLS 1.0 in 1999. TLS 1.2 is currently a dominant version.
- **The Handshake Protocol:** This initial phase allows the client and server to:
    1. Agree on cryptographic algorithms.
    2. Authenticate the server (and optionally the client) using digital certificates.
    3. Establish a shared secret (using **RSA** or **Diffie-Hellman**) to derive symmetric keys for data encryption.
- **Protections Provided:**
    - **Privacy:** Encrypts almost all communication, including the URL, document contents, form data, and cookies.
    - **Integrity:** Uses **Message Authentication Codes (MAC)** to ensure data has not been altered.
- **Limitations:** TLS does **not** provide non-repudiation. It is also vulnerable to **Man-in-the-Middle (MITM)** attacks if users are tricked into accepting invalid certificates.

# 3. Securing Name Resolution: DNSSEC

DNS translates symbolic hostnames into numeric IP addresses. Standard DNS is vulnerable because it has no mechanism to verify the authenticity of a response.

- **DNSSEC** addresses this by using digital signatures.
- A zone owner signs their records with a **private key**, and resolvers verify the authenticity using a corresponding **public key**.

# 4. Secure Remote Login: SSH

**SSH (Secure Shell)** was developed specifically to defend against password-sniffing attacks.

- It provides a secure channel for remote login and other services over untrusted networks.
- It guarantees **confidentiality**, **integrity**, and **server authentication**.
- **Authentication:** Supports both passwords and **key-based authentication**, where a client proves possession of a private key.

# 5. Network Layer Protection: IPSec

Unlike TLS, which secures specific applications, **IPSec** operates at the **Network Layer**, making it transparent to applications.

- **Security Association (SA):** Endpoints must agree on security parameters before traffic flows. An SA is a **one-way** relationship; bidirectional communication requires two SAs.
- **Modes of Operation:**
    - **Transport Mode:** Protects only the payload; the original IP header remains visible.
    - **Tunnel Mode:** Protects the entire packet and wraps it in a new outer IP header, hiding the original sender and recipient.
- **Core Protocols:**
    - **AH (Authentication Header):** Provides integrity and authenticity but **no encryption**.
    - **ESP (Encapsulating Security Payload):** Provides confidentiality (encryption) and can optionally provide authentication.
- **IKE (Internet Key Exchange):** A protocol used to automate the negotiation of SAs and keys between endpoints.

# 6. Enhancing Web Trust: HSTS

To prevent protocol downgrade attacks (forcing a connection from HTTPS to insecure HTTP), web servers use **HSTS (HTTP Strict Transport Security)**. This policy instructs browsers to interact with the site **only** via HTTPS.