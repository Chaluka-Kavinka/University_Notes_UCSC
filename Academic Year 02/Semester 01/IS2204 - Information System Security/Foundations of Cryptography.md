# 1. Introduction to Cryptography

Cryptography is the **art or science of secret writing**. Its primary purpose is to protect sensitive information by storing and transmitting it in a form that allows it to be revealed only to those intended. A **cryptosystem** is the set of protocols and algorithms that accomplish this.

## 1.1. Core Terminology

- **Plaintext (Cleartext):** The original, intelligible data.
- **Ciphertext:** The scrambled, unreadable version of the data.
- **Encipher (Encryption):** The process of converting plaintext to ciphertext using a secret key.
- **Decipher (Decryption):** The process of converting ciphertext back to plaintext.
- **Key:** A secret sequence that governs the encryption and decryption processes.

## 1.2. Business Goals and Objectives

A modern cryptosystem aims to provide four essential security services:

- **Confidentiality:** Ensures unauthorized parties cannot access the data.
- **Authenticity:** Ensures the source or sender of the data is identifiable.
- **Integrity:** Ensures data was not modified during transmission.
- **Non-repudiation:** Ensures that a party cannot deny sending or receiving the data.

## 1.3. Historical Evolution and Principles

- **Kamasutra (4th Century BC):** Contains one of the earliest descriptions of encryption by substitution.
- **Caesar Cipher:** An ancient substitution cipher where each letter in the plaintext is shifted by 3 positions (Ci​=Pi​+3).
- **Enigma:** A machine used by Germany in WWII; the activities at Bletchley Park to break this code remain a seminal moment in security history.
- **Kerckhoff’s Principle:** A fundamental rule stating that the security of an encryption scheme must depend **only on the secrecy of the key**, not on the secrecy of the algorithm.

## 1.4. Hash Functions: The "Fingerprint"

A hash function h=H(M) condenses a message of any length into a **fixed-sized fingerprint**. Unlike encryption, hash functions are usually public and not keyed.

### Essential Properties of Secure Hashes:

1. **Efficiency:** It is easy and fast to compute the hash for any message.
2. **One-way Property:** Given a hash h, it is computationally infeasible to find the original message x.
3. **Weak Collision Resistance:** Given a message x, it is infeasible to find another message y that produces the same hash.
4. **Strong Collision Resistance:** It is infeasible to find _any_ two distinct messages that result in the same hash.

## 1.5. Hash Algorithms: Old vs. Modern

- **MD5:** Designed by Ronald Rivest, it produces a 128-bit hash. While once widely used, it is now considered **vulnerable** as researchers have successfully demonstrated collisions.
- **SHA-256:** A standard, secure function that generates a 256-bit output. It is commonly used for digital signatures and password storage.
- **Argon2:** The winner of the 2015 Password Hashing Competition (PHC), specifically designed to resist **brute-force and side-channel attacks**.
- **Yescrypt:** A **memory-hard** algorithm designed to resist attacks from specialized hardware like ASICs.

## 1.6. Applications of Hashing

Hashing is used across nearly every domain of information security:

- **Password Storage:** Storing hashes instead of actual passwords ensures that even if a server is compromised, the original passwords are not immediately visible.
- **Message Authentication:** Verifying that a message has not been altered.
- **Blockchain Technology:** Hashing is the critical component used for secure, decentralized record-keeping.
- **Data Deduplication:** Identifying and removing duplicate files in large storage systems.
- **Chain of Custody (CoC):** Tracking the chronological history and integrity of digital evidence.

## 1.7. User Challenges: Weak Passwords

Despite technical protections, security often fails because users choose passwords from a very small set (e.g., "123456" appeared in 0.90% of a 32-million password sample). These are easily broken via **dictionary attacks**, though systems can defend against this by doubling response times after failed attempts.

---
# 2. Symmetric Key Cryptography

## 2.1. Definition and Core Concept

**Symmetric Key Cryptography**, also known as traditional, secret-key, or single-key cryptography, is a method where a **single key** is used for both the encryption of plaintext and the decryption of ciphertext.

The fundamental requirement for this system to work is that the **secret key must be shared** by both the sender and the receiver before any secure communication can take place.

# 2.2. Security Implications

The security of a symmetric cryptosystem relies entirely on the secrecy of the key. Your sources highlight several critical considerations:

- **Key Compromise:** If the shared key is disclosed to an unauthorized party, all communications using that key are completely compromised.
- **Equality of Parties:** In a symmetric system, both parties are "equal" because they possess the same key.
- **Lack of Non-Repudiation:** Because both parties have the same key, a receiver could technically forge a message and claim it was sent by the original sender. This makes it difficult to prove the origin of a message with absolute certainty using only symmetric methods.

## 2.3. Classification of Symmetric Ciphers

Symmetric cryptography is categorized into two main eras: **Classical** and **Modern**.

### Classical Cryptography

These are historical methods that typically operate on individual letters or small groups of letters:

- **Substitution Cipher:** A method where each element in the plaintext (such as a letter) is replaced by another element to create the ciphertext.
- **Transposition Cipher:** A method where the elements of the plaintext are not replaced but are instead **reordered** or rearranged according to a specific logical pattern.

### Modern Cryptography

Modern symmetric algorithms are designed for computer processing and are divided based on how they handle data:

- **Stream Ciphers:** These algorithms encrypt digits or bytes of a data stream **one at a time**.
- **Block Ciphers:** These algorithms process the plaintext in **fixed-size blocks** (e.g., 64-bit or 128-bit blocks), applying the encryption algorithm to the entire block at once.

## 2.4. Summary of Characteristics

|Feature|Description|
|---|---|
|**Key Count**|One single secret key.|
|**Key Distribution**|Must be shared securely between sender and receiver.|
|**Speed**|Generally very fast (ideal for bulk data encryption).|
|**Major Challenge**|Securely distributing the key to all authorized parties.|

---

# 3. Asymmetric Key Cryptography (Public-Key)

## 3.1. Introduction and Core Purpose

**Asymmetric Key Cryptography**, also known as **Public-Key Cryptography (PKC)**, was developed to address two critical limitations of symmetric systems:

- **Key Distribution:** The challenge of securely sharing a secret key between parties who have no prior relationship without needing a trusted third party for every interaction.
- **Digital Signatures:** The need for a method to verify that a message remains intact and truly originated from the claimed sender (ensuring **authenticity** and **non-repudiation**).

The fundamental concept was introduced by **Whitfield Diffie and Martin Hellman in 1976**.

## 3.2. The Mechanics: A Key Pair

Unlike symmetric systems that use one shared secret, asymmetric systems use a **Key Pair**:

1. **Public Key:** Made available to everyone; used for encryption or verifying signatures.
2. **Private Key:** Kept strictly secret by the owner; used for decryption or creating signatures.

A complete PKC scheme involves **six ingredients**: plaintext, an encryption algorithm, the public/private key pair, ciphertext, and a decryption algorithm.

## 3.3. Comparison with Symmetric Cryptography

|Feature|Symmetric (Private Key)|Asymmetric (Public Key)|
|---|---|---|
|**Key Count**|One single shared secret.|Two mathematically related keys.|
|**Speed**|Very fast; ideal for bulk data.|Much slower (computationally intensive).|
|**Primary Use**|Bulk encryption/decryption.|Key exchange and digital signatures.|
|**Security Foundation**|Secrecy of the shared key.|Mathematical "hard problems".|

## 3.4. Major Asymmetric Algorithms

Your sources highlight three primary pillars of modern asymmetric cryptography:

### A. Diffie-Hellman (DH) Key Agreement

- **Purpose:** Allows two parties to agree on a shared secret key over an insecure channel.
- **Mathematical Basis:** The difficulty of calculating **discrete logarithms** in a finite field.
- **Advantage:** Achieves **Forward Secrecy**, meaning past messages remain secure even if a long-term private key is compromised later.

### B. RSA (Rivest-Shamir-Adleman)

- **Purpose:** The most widely implemented system for both encryption and digital signatures.
- **Mathematical Basis:** The difficulty of **factoring the product of two very large prime numbers**.
- **Legacy:** Invented in 1977, it remains a foundation of internet security.

### C. Elliptic Curve Cryptography (ECC)

- **Purpose:** Provides a more efficient alternative to RSA and DH.
- **Advantage:** Offers **greater security with smaller key sizes**, making it ideal for mobile systems and high-security requirements.
- **Mathematical Basis:** Complex properties of elliptic curve point addition and doubling.

## 3.5. Digital Signatures and PKI

PKC enables **Digital Signatures**, which are more secure than simple "electronic signatures" because they use encryption and certificates to verify identity and document integrity.

To manage these keys, a **Public Key Infrastructure (PKI)** is used:

- **Certificate Authority (CA):** A trusted third party that validates an individual's identity and issues a **Digital Certificate** (like the X.509 standard).
- **Trust Models:** Trust can be established through a central hierarchy or a **Web of Trust** (common in PGP), where users vouch for one another.

## 3.6. The Quantum Threat and the Future

The security of RSA and ECC relies on problems that are "too hard" for classical computers, but this promise is expected to be broken by **Quantum Computing**.

- **Shor’s Algorithm:** Can theoretically factor large prime products in seconds, rendering RSA unsafe once large-scale quantum computers are built.
- **Post-Quantum Cryptography (PQC):** New algorithms (like **CRYSTALS-Kyber** for key exchange and **CRYSTALS-Dilithium** for signatures) are being developed to be mathematically resistant to quantum attacks while still running on classical computers.

---

# 4. Hashing

Hashing is the process of using a mathematical function to condense a message or data of any size into a **fixed-size "fingerprint"** or value. In the context of information security, hash functions are primarily used to ensure **data integrity** by detecting any unauthorized changes to a message.

## 4.1. Essential Properties of Secure Hashing

For a hash function to be considered cryptographically secure, it must meet several requirements:

- **Efficiency:** It must be easy and fast to compute the hash H(x) for any given input x.
- **One-Way Property (Pre-image Resistance):** Given a hash value h, it must be computationally infeasible to find the original message x that produced it.
- **Weak Collision Resistance (Second Pre-image Resistance):** Given a message x, it must be infeasible to find a different message y such that both have the same hash value (H(x)=H(y)).
- **Strong Collision Resistance:** It must be infeasible to find _any_ two distinct messages that result in the same hash value.

## 4.2. Common Hashing Algorithms

Your sources highlight several modern and historical algorithms:

- **MD5:** Designed by Ronald Rivest, it produces a 128-bit hash. While once the most widely used, it is now considered **vulnerable** because researchers have successfully demonstrated collision attacks.
- **SHA-256:** A widely implemented and secure 256-bit hash function used for digital signatures and ensuring data authenticity.
- **Argon2:** The winner of the 2015 Password Hashing Competition (PHC), specifically designed to resist **brute-force and side-channel attacks**.
- **Yescrypt:** A **memory-hard** algorithm that is resistant to specialized hardware attacks (like ASICs).

## 4.3. Key Applications of Hashing

Hashing is a versatile tool used across many security domains:

- **Secure Password Storage:** Systems should **never store passwords in cleartext**. Instead, they store hashes. To prevent "dictionary attacks" where hackers compare pre-computed hashes, systems use a **"Salt"**—a random string added to the password before hashing to make the resulting hash unique.
- **Digital Signatures:** Hashing is used to verify that a digital document has not been altered and to establish non-repudiation.
- **Blockchain and Bitcoin:** Hashing is the core of **"Proof of Work."** Miners compete to find a specific hash value (using a random number called a "nonce") that is lower than a set threshold T.
- **Message Authentication Codes (HMAC):** These are **keyed hash functions** that include a secret key along with the message. They are often faster than block ciphers and provide assurance that a message is both unaltered and from a legitimate sender.
- **Data Deduplication:** Identifying and removing duplicate files in storage systems by comparing their hash values.
- **Malware Analysis:** Static analysis uses hashes to identify known malicious files without having to run them.

## 4.4. Important Distinction: Hashing vs. Encryption

Unlike encryption, hashing is generally **not meant to be reversible**. While encryption is used to hide information so it can be read later by an authorized party, hashing is used to create a permanent, unique identifier for a piece of data to prove it hasn't been tampered with.