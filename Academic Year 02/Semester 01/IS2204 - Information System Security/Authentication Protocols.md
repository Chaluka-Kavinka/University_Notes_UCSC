# 1. Foundations of Identity

Authentication is part of a three-step process used to manage access to systems, which are often mistakenly conflated in casual conversation:

- **Identification:** Answering "Who does this user claim to be?".
- **Authentication:** Answering "Can they prove who they claim to be?".
- **Authorization:** Answering "Given that identity, what are they allowed to do?".

# 2. The Three Factors of Authentication

Users can prove their identity through three primary categories:

- **Something you KNOW:** Passwords, PINs, or secret answers.
- **Something you HAVE:** Smart cards, hardware tokens, or mobile phones.
- **Something you ARE:** Biometrics like fingerprints, iris patterns, or facial recognition.

**Multi-Factor Authentication (MFA)** is meaningfully stronger because it combines factors from different categories (e.g., a password plus an OTP sent to a phone). While 2FA typically uses two factors, MFA can span all three, though it adds friction and makes account recovery more complex.

# 3. Authentication Mechanisms

There are four primary ways to prove knowledge of a secret:

- **Direct Presentation:** The user reveals the secret itself (e.g., typing a password). The **Password Authentication Protocol (PAP)** is a "direct" method that is insecure because it transmits credentials as plain text.
- **Challenge-Response:** The verifier issues a random **nonce** (challenge), and the user computes a response derived from both the secret and the challenge. The secret itself is never transmitted over the network.
- **Implicit (Cryptographic):** Proving possession of a private key through a cryptographic operation without needing a shared secret.
- **Zero-Knowledge Proofs:** Proving knowledge of a secret while revealing absolutely nothing about the secret itself.

# 4. Classical Protocols

- **Passwords:** Early systems incorrectly stored passwords in cleartext, meaning a server compromise exposed everything. Modern systems store **one-way hashes** of passwords; if a user provides the correct password, its hash will match the stored value.
- **One-Time Passwords (OTP):** These address the weakness of static passwords by using a code that is used once and never again. Mechanisms include **S/Key** (repeated hashing), **SecurID** (hardware tokens generating codes at fixed intervals), and **Mobile OTP** (SMS/app codes).
- **Kerberos:** A trusted third-party service used in distributed environments like **Microsoft Active Directory**. It issues time-limited **tickets** so users do not have to re-authenticate to every individual service. It requires synchronized system clocks and relies on a central **Key Distribution Center (KDC)**.

# 5. Federated Identity

Federation allows a single login to be used across many independent services.

- **SAML (Security Assertion Markup Language):** An XML-based standard common in legacy enterprise and institutional systems. An Identity Provider (IdP) sends a **cryptographically signed assertion** to a Service Provider (SP) to confirm a user's identity.
- **OAuth and OpenID Connect (OIDC):** OAuth is an **authorization** framework, while OIDC is an **authentication** layer built on top of it. "Sign in with Google" buttons specifically utilize OIDC to confirm who a user is.

# 6. The Passwordless Future: Passkeys

The industry is moving toward removing typed secrets entirely to eliminate phishing risks and the impact of server breaches.

- **WebAuthn:** A standard that replaces passwords with **public/private key pairs**.
- **Passkeys:** Unlike passwords, the **private key never leaves the device**. The server only stores a public key, which has no value to an attacker if stolen. Passkeys are bound to specific domains, making it impossible to type them into a fake phishing site.

# 7. Emerging and Human Verification

- **CAPTCHA:** Designed to answer "Are you human at all?" rather than "Who are you?". Modern versions use passive behavioral analysis instead of visual puzzles.
- **Decentralized Identity (DID):** A user-owned, cryptographically verifiable identifier that requires no central issuing authority. This forms the basis of **"self-sovereign identity,"** where credentials can be checked by any verifier without contacting the original issuer.