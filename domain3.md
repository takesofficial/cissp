# <p align=center>Domain 3 - Security Architecture and Engineering</p>

## 🚨 Elevator Pitch  
Design and build systems that stay secure under stress. Domain 3 is about security models, trusted computing, architecture principles, crypto basics, and physical protection. How to design systems so they fail secure, limit blast radius, and keep attackers from ever getting a foothold.

---

## 🧠 Architecture Mindset  

High level, manager brain first, engineer brain second.

- **Defense in depth** - Multiple independent layers of controls, not one big firewall.
- **Least privilege** - Give every component the minimum rights needed.
- **Separation of duties** - No single role should be able to cause unreviewed damage.
- **Fail secure** - On failure, default to secure state, not convenient state.
- **Zero trust** - Never automatically trust network location, user, or device.
- **Secure defaults** - Start locked down; users can request access, not the other way around.
- **Economy of mechanism** - Design should be simple and small to reduce bugs.
- **Complete mediation** - Every access to an object is checked, not just the first time.
- **Open design** - Rely on key secrecy, not algorithm secrecy.

---

## 🧱 Trusted Computing Concepts  

### Core Pieces  

- **Trusted Computing Base (TCB)**  
  - All hardware, firmware, and software that enforces the security policy.  
  - Smaller TCB = easier to test and trust.

- **Reference Monitor**  
  - Conceptual access control engine that checks every access.  
  - Must be: **tamperproof, always invoked, small and simple**.

- **Security Kernel**  
  - The implementation of the reference monitor inside the OS.  
  - Runs in most privileged mode.

- **Protection Rings**  
  - Ring 0 - Kernel, most trusted.  
  - Ring 1/2 - OS services, drivers.  
  - Ring 3 - User space, least trusted.  

---

## 🧬 Security Models (just enough to recognize)  

Focus on what each model protects and the simple rule you see in questions.

- **Bell-LaPadula** BL(UD) - Confidentiality  
  - "No read up" - subject cannot read higher classification.  
  - "No write down" - subject cannot write to lower classification.
- **Biba(DU)** - Integrity  
  - "No read down" - subject cannot read lower integrity data.  
  - "No write up" - subject cannot write to higher integrity level.
- **Clark-Wilson** - Integrity 
  - Well-formed transactions + separation of duties.  
  - Users cannot touch data directly, only through controlled programs.
- **Brewer-Nash (Chinese Wall)** - Confidentiality  
  - Avoid conflicts of interest.  
  - Access decisions depend on what you already accessed (e.g. only one bank in a sector).

Other names (Goguen-Meseguer, Sutherland, information flow models, lattice)  
- Know they are **formal models of access and information flow**, not implementation details.

---

## 🔐 Crypto Fundamentals

Goal: recognize **what to use when** - not calculate key schedules.

---

### 🔑 Symmetric Cryptography (disk encryption, VPNs, TLS session encryption) ⚡ Fast - used for **bulk data encryption**  
- 🔥 Most common: **AES** - encrypt data
- ⚡ Efficient modern option: **ChaCha20** (mobile devices - high performance)  

- 🔁 One shared key - same key encrypts & decrypts
- 🚨 Main weakness: **key distribution & scalability**
- 🌊 Modern stream option: ChaCha20  

### 🔲 Block Ciphers (type of symmetric encryption)
Operate on fixed-size blocks  

- Require a **mode of operation**:
- 📕 **ECB** - no I.V. - ment for short messages - identical plaintext > identical ciphertext (weak, **avoid** ❌)
- 🔄 **CBC** - chains, uses IV, hides patterns (older mode, no built-in integrity) - confidentiality

- 🏎️ **CTR** - counter (turns a block cipher into stream-like behavior) - confidentiality
 - 🥇 **GCM** - encryption + authentication (**Golden** Standard) -confidentiality + integrity 
 
 - 💾 **XTS** - disk encryption (e**XT**ra for s**T**orage) - confidentiality


### 🌊 Stream Ciphers (encrypts bit by bit. type of symmetric encryption)
- Generate a continuous **keystream**
- 🔀 Encrypt by XORing keystream with plaintext
- ⚡ Very fast, low latency
- 📡 Ideal for:
  - 📞 Real-time communication (VoIP, video, wireless)
  - 🔗 Error-sensitive links (bit errors don’t corrupt entire blocks)
- 🚨 Critical: Never reuse a nonce/keystream (breaks security)

---

### 🔓 Asymmetric Cryptography (Public/Private Key) 🐢 Slower - not used for bulk encryption  
- 🔥 Most common: **RSA**  - commonly used for digital signatures (and key exchange)
- ⚡ Efficient modern option: **ECC** (mobile/IoT - smaller keys)  
- 🤝 Diffie-Hellman: Secure 🔑Key Exchange; agree on a shared secret over an insecure channel; not encryption itself.

- 🔐 Key pair: public + private  

- Used for:
  - 🔑 Key exchange  
  - ✍️ Digital signatures  
  - 🪪 Identity & authentication  

---

### 🧾 Hash Functions (Integrity)
- 🔥 Most common: **SHA-256**

- 🔁 One-way function  
- 📏 Fixed-size output  
- Used for:
  - Integrity checks  
  - Password storage  
  - Digital signatures  

**Security properties:**
- 🚫 Preimage resistance  
- 🚫 Second preimage resistance  
- 🚫 Collision resistance  

---

## ✍️ Digital Signatures & PKI

- 🔐 Sign with **private key**  
- 🔓 Verify with **public key**  

**PKI (Public Key Infrastructure) - trust in public keys Components:**
- 🏢 CA (Certificate Authority) - issues & signs certificates  
- 📜 CRL - certificate revocation / 🌐 OCSP - real time status check

---





### Crypto Attacks

- **Brute force** - attacker keeps trying every possible password or key one by one until the system finally accepts one and lets them in.
- **Birthday attack** - attacker keeps trying different messages until 2 of them accidentally get the same hash, just like two people sharing a birthday by chance. targets (old) hash weakness, integrity failure and collisions.
- **Side channel** -  attacker doesn't attack the system itself, but instead learns secrets by watching how it behaves, like how long it takes, how much power it uses, or what sounds it makes.
- **Chosen plaintext** -  attacker can deliberately send messages of their own choosing to be encrypted, then studies the encrypted results to learn how the encryption behaves.
- **Chosen ciphertext** - attacker decides encrypted messages to decrypt and uses the results to figure out the secret key or how decryption works.

---

## 💻 Trusted Hardware and Secure Boot  

- **TPM (Trusted Platform Module)**  
  - Hardware chip for secure key storage, measurements, and attestation.  
  - Supports disk encryption (e.g. BitLocker), secure boot.

- **HSM (Hardware Security Module)**  
  - Dedicated appliance for high-value keys and crypto operations.  
  - Used by banks, CAs, payment systems.

- **Secure boot / measured boot**  
  - Verify signatures on firmware and OS before loading.  
  - Block tampered boot loaders and rootkits.

---

## 🧪 Memory and Process Protection  

Goal: isolate processes so one compromise does not own the whole system.

- **Process isolation** - each process runs in its own address space.  
- **Memory segmentation / paging** - hardware prevents a process from reading another's memory.  
- **ACLs and capabilities** - define which subjects can access which objects.  
- **Execution states** - user mode vs kernel mode.

---

## 🦠 Malware Basics  

You only need to recognize types and rough behavior.

- **Virus** - needs a host file, spreads via infection.  
  - Macro virus - abuses office macros.  
  - Boot sector virus - infects boot loader.  
  - Stealth / polymorphic - try to evade AV by hiding or changing signature.  
  - Multipartite - uses multiple infection vectors.

- **Worm** - self contained, spreads over the network.  
- **Trojan** - looks useful, hides malicious behavior.  
- **Ransomware / spyware / rootkit** - know the names and intent.

---

## ⚙️ Logical Operations (used in crypto and access decisions)  

- **NOT** - flip bit: 1 becomes 0, 0 becomes 1.  
- **AND** - 1 if both bits are 1.  
- **OR** - 1 if at least one bit is 1.  
- **XOR** - 1 if bits are different. Used heavily in stream ciphers and checksums.

You do not need truth tables, just the basic behavior and that XOR "cancels" with itself.

---

## 🔥 Fire Classes and Suppression  

### Fire Classes  

- **Class A** - 📦 **A**sh - ordinary combustibles (environment: 📃 paper, 🪑 furniture, 🧃 plastics)
- **Class B** - 🧪 **B**oil - flammable liquids/gases (environment: ⛽ fuel, 🧪 solvents, 🛢️ oils)
- **Class C** - 🔌 **C**urrent - energized electrical (environment: 💻 servers, 🔌 power panels, 📡 live equipment)
- **Class D** - ⚙️ **D**ent - combustible metals (environment: 🧲 magnesium, 🔩 titanium, 🌫 metal dust)
- **Class K** - 👨‍🍳 **K**itchen - cooking oils/fats (environment: 🍟 deep fryers, 🫕 grease, 🍳 stovetops)

### Suppression Systems  

- 💧 **Wet pipe** - water in pipes, released immediately. Simple, fastest.  
- ❄️ **Dry pipe** - air in pipes, water admitted when triggered. For cold areas.  
- 🌊 **Deluge** - open heads, huge water volume. Industrial, not for server rooms.  
- 🚨💧 **Preaction** - combination: detection fills pipes, second trigger opens heads, water. > Best for areas with people and computers.

---

## 🏢 Physical and Environmental Security  
Big picture: stop easy physical attacks that make all logical controls useless.

- 🚧 **Perimeter** - fences, gates, guards, lighting, CCTV.  
- 🏢**Building** - mantraps, turnstiles, badges, locks, reception.  
- 🔐**Interior** - locked server rooms, racks, safes, cable protection.  
- 🌡️ **Environmental** - HVAC, temperature and humidity control, power conditioning, UPS, generators.  
- 📡 **Emanations** - shielding, TEMPEST, Faraday cages to reduce signal leakage.  
- 🎥 **CCTV basics** - camera placement, coverage zones, blind spots, lighting, monitoring, retention policies.

---

## 🏭 ICS / Operational Technology (SCADA / DCS / PLC)

Industrial Control Systems (ICS) control **real world physical processes** (⚡ grid / 💧 water / 🛢 refinery / 🏭 plant).

- 🌍  **SCADA** (**S**upervisory **C**ontrol **A**nd **D**ata **A**cquisition)
  - Wide-area control of **geographically dispersed sites** (🛠️ utilities, 🛢 pipelines, 🔌 power grids)
  
- 🏭  **DCS** (**D**istributed **C**ontrol **S**ystem)
  - Tightly integrated control within a **single facility** (🛢 refinery, 🧪 chemical plant, 🏭 manufacturing plant)
  
- 🤖  **PLC** (**P**rogrammable **L**ogic **C**ontroller)
  - Device-level controller (🛠 individual machines, 🔧 assembly lines)

---
## 🔗 Useful Links / Mind Map  
[CISSP Domain 3 Destination Certification](https://youtu.be/TreDxg9Y3yo)
