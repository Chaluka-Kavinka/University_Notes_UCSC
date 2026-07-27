# 1. Defining Malware and APTs

**Malware** is defined as software inserted into a system, typically covertly, with the intent to compromise its **confidentiality, integrity, or availability**. It is a broad umbrella term covering many different mechanisms and intentions.

A more sophisticated category is the **Advanced Persistent Threat (APT)**, which involves a well-resourced adversary conducting a sustained, targeted campaign against a specific organization, prioritizing stealth and persistence over speed. In these cases, malware is often just one tool used within a much longer campaign.

# 2. Classifying Malware

The sources classify malware based on two independent questions: **how it spreads (Propagation)** and **what it does (Payload)**. The same payload can travel via different propagation mechanisms.

## A. Propagation Mechanisms (How it Spreads)

- **Viruses:** Malicious code that infects existing content by inserting itself into other programs or files. They **require a human** to run the infected program before they can spread. Their lifecycle typically moves through dormant, propagation, triggering, and execution phases.
    - _Detection Evasion:_ **Polymorphic viruses** change their own form with every copy to defeat signature-based matching.
- **Worms:** Independent programs that exploit software vulnerabilities to spread. Unlike viruses, they **require no human action** and do not need to infect a host file.
- **Social Engineering:** Relies on deceiving humans to bypass their own security judgment. A common example is the **Trojan Horse**, where malicious code is hidden inside an apparently useful, non-replicating program.

## B. Payload Types (What it Does)

- **System Corruption:** Includes **logic bombs** (dormant code that triggers on specific conditions) and **rabbits/bacteria** (programs that consume all of a system resource, like disk space, to cause a crash).
- **Extortion (Ransomware):** Malware that encrypts a victim's data using a freshly generated key. The attacker then encrypts that key with their own public key, demanding a ransom for the private key needed to recover the data.
- **Attack Agents (Zombies/Bots):** Compromised machines secretly controlled to launch attacks, such as **DDoS attacks**, on the attacker's behalf. A network of these machines is called a **botnet**.
- **Information Theft:** Includes **keyloggers** (capturing keystrokes), **phishing** (deceptive communication to trick users), and **spyware** (monitoring and exfiltrating data without consent).
- **Stealthing:** **Backdoors (trapdoors)** provide secret entry points that bypass normal security, while **rootkits** are toolsets that conceal the presence of malware at the operating system level.

# 3. Defensive Technologies

Organizations use a layered approach to defend against malicious code, starting from the network perimeter and moving inward.

## A. Firewalls

A **firewall** acts as a control point between a trusted internal network and an untrusted external network.

- **Types of Firewalls:**
    - **Packet Filtering:** Inspects each packet in isolation against fixed rules (stateless).
    - **Stateful Inspection:** Tracks active connections to ensure packets belong to a legitimate, ongoing session.
    - **Application-Level Gateway (Proxy):** Has full visibility into the application protocol (like HTTP) to validate requests.
    - **Circuit-Level Gateway:** Relays TCP connections and validates them only at setup.
- **Limitations:** Firewalls generally cannot inspect **encrypted traffic** and may allow malicious content if it is riding on a service that has been permitted through the perimeter.

## B. Intrusion Detection and Prevention Systems (IDS/IPS)

While firewalls filter at the perimeter, an **IDS** monitors behavior inside the network to catch what the perimeter missed.

- **Detection Methods:** **Signature-based** detection matches known attack patterns, while **anomaly-based** detection flags deviations from a baseline of "normal" behavior.
- **Response:** An **IDS is passive**, generating alerts for humans to act upon, whereas an **IPS is active**, taking automatic actions like blocking an IP or locking an account.

## C. Decoy Systems

Defenders use deception to study attackers:

- **Honeypot:** A decoy system designed to attract and study attackers without risking genuine assets.
- **Honeytoken:** A single piece of decoy data (like a fake credential) that triggers an alert if used.
- **Honeynet:** A network of multiple honeypots simulating a realistic target environment.

# 4. Malware Analysis and Tools

Modern security involves both **static analysis** (examining a file's hashes and strings without running it) and **dynamic analysis** (executing code in an isolated **sandbox** to observe its behavior).

Your sources highlight several tools for this purpose:

- **VirusTotal:** Cross-references files against dozens of scanning engines.
- **ANY.RUN:** An interactive sandbox for real-time behavioral observation.
- **Hybrid Analysis:** A service combining both static and dynamic analysis.