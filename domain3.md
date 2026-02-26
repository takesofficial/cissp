# <p align=center>Domain 3 - Security Architecture and Engineering</p>

## 🧠 Mind Map
[CISSP Domain 3 Destination Certification](https://destcert.com/resources/domain-3-security-architecture-and-engineering)

---

## 🚨 Elevator Pitch  
Design and build systems that stay secure under stress. Domain 3 is about security models, trusted computing, architecture principles, crypto basics, and physical protection. How to design systems so they fail secure, limit blast radius, and keep attackers from ever getting a foothold.

---

## 🧠 Secure Architecture Principles

Security architecture defines how systems are designed to reduce risk, contain failure, and enforce policy by design.

| Principle | Core Idea | Why It Matters | Pattern |
|------------|-----------|----------------|--------------------|
| 🛡️ **Defense in Depth** | Multiple independent control layers | No single control failure leads to compromise | Layered controls (firewall + IDS + segmentation) |
| 🔐 **Least Privilege** | Grant minimum rights required | Limits blast radius if compromised | RBAC, minimal service accounts |
| 👥 **Separation of Duties** | Split critical tasks across roles | Prevents fraud and abuse | Dev ≠ Prod, Admin ≠ Auditor |
| 🔒 **Fail Secure** | Default to secure state on failure | Prevents accidental exposure | Firewall fails closed, not open |
| 🌐 **Zero Trust** | Never trust implicitly | Continuous verification required | Authenticate & authorize every request |
| 🔐 **Trusted Path** | Secure communication between user and security kernel | Prevents credential interception | Secure Attention Sequence (Ctrl+Alt+Del) |
| 🔧 **Secure Defaults** | Systems start locked down | Reduces misconfiguration risk | Services disabled by default |
| 🧩 **Economy of Mechanism** | Keep design simple and small | Fewer bugs, easier to verify | Smaller TCB = easier to trust |
| 👁️ **Complete Mediation** | Check every access request | Prevents bypass after initial check | Session revalidation, API authorization |
| 🔑 **Open Design** | Security not dependent on secrecy of design | Encourages strong cryptography | Algorithms public, keys secret |
| 📉 **Least Common Mechanism** | Minimize shared components | Reduces unintended information flow | Dedicated resources, isolation |
| 🙋 **Psychological Acceptability** | Security mechanisms must be usable | Users bypass unusable controls | MFA usable, not obstructive |
| 🔄 **Compartmentalization** | Isolate systems into segments | Limits lateral movement | Network segmentation, VLANs |
| 📦 **Abstraction Layers** | Separate logical layers of control | Easier maintenance and containment | App tier ≠ DB tier |
| 🧪 **Defense Against Insider Threats** | Design assuming internal misuse | Reduces trusted-user abuse risk | Logging, dual control |
| 🧱 **Minimize Attack Surface** | Reduce exposed services and interfaces | Fewer entry points for attackers | Disable unused ports/services |

---

---

## 🏗️ System Architecture Concepts  

Security architecture must consider how systems are logically and physically structured.

### 🖥️ System Architecture Types

| Architecture | Description | Security Implication |
|--------------|------------|----------------------|
| 🏛️ **Security Domains** | Logical separation of trust levels | Supports isolation and policy enforcement |
| 🧱 **Monolithic** | All components tightly integrated | Larger attack surface; harder to isolate failures |
| 🧩 **Layered Architecture** | Separation of presentation, logic, and data layers | Supports isolation and defense in depth |
| ☁️ **Microservices** | Small independent services communicating via APIs | Strong segmentation required; API security critical |
| 🏢 **Client-Server** | Central server provides services to multiple clients | Server becomes high-value target |
| 🌐 **Distributed Systems** | Components across multiple nodes | Requires secure communication and synchronization |

---

### 🧠 Virtualization & Isolation

| Technology | Security Relevance |
|------------|-------------------|
| 🖥️ **Hypervisor (Type 1 / Type 2)** | Enforces isolation between virtual machines |
| 📦 **Containers** | Lightweight isolation; share kernel (less isolation than VMs) |
| 🧬 **Sandboxing** | Restricted execution environment for untrusted code |
| 🧪 **Air Gapping** | Physical isolation from networks |

Isolation strength:  
Hardware isolation > Virtual machine isolation > Container isolation > Process isolation

---

## 🧱 Trusted Computing & Protection Rings  

Trusted computing defines the minimal components required to enforce a system's security policy.  
The goal is to minimize what must be trusted and strictly control privilege boundaries.
Understand how hardware-enforced privilege separation supports secure system architecture.

| Concept | Definition | Key Properties | Focus |
|----------|------------|----------------|------------|
| 🏛️ **Trusted Computing Base (TCB)** | All hardware, firmware, and software that enforce the security policy | Smaller TCB = easier to verify, test, and trust | Identify what must be trusted for security enforcement |
| 👁️ **Reference Monitor** | Conceptual access control mechanism that validates every access request | ✔ Tamperproof<br>✔ Always invoked<br>✔ Small & simple | Theoretical enforcement model |
| 🧠 **Security Kernel** | Implementation of the reference monitor within the OS | Runs in most privileged mode (Ring 0) | Practical enforcement of access control |
| 🧿 **Protection Rings** | Hardware-enforced privilege levels within CPU architecture | Enforces privilege separation and fault isolation | Understand privilege hierarchy and containment |

---

### 🕵️ Covert Channels

| Concept | Definition | Types | Focus |
|----------|------------|--------|------------|
| 🕵️ **Covert Channels** | Unintended communication paths that violate security policy | Storage channel (uses shared resources)<br>Timing channel (uses system timing variations) | Breaks mandatory access control; common in multilevel secure systems |

---

### 🧿 Protection Ring Levels (Hardware Privilege Hierarchy)

The Ring Model enforces isolation by assigning execution levels with decreasing privilege.

| Ring | Privilege Level | Typical Components | Trust Level | Security Impact |
|------|-----------------|-------------------|------------|----------------|
| 🥇 **Ring 0** | Most Privileged | OS Kernel, core security functions | Highest | Full hardware & memory control. If compromised → entire system compromised. |
| 🔧 **Ring 1** | High Privilege | Device drivers, OS services | High | Direct hardware interaction. Often merged with Ring 0 in modern systems. |
| 📚 **Ring 2** | Medium Privilege | System utilities, libraries | Moderate | Controlled support services. Rarely distinct in practice. |
| 👤 **Ring 3** | Least Privileged | User applications, processes | Lowest | Restricted from direct hardware access. Malware typically executes here. |

---

### 🔐 What Rings Enforce

| Control Mechanism | Security Benefit |
|-------------------|-----------------|
| 🔒 **Privilege Separation** | Supports least privilege and limits blast radius |
| 🛡️ **Fault Isolation** | Prevents user-space compromise from affecting kernel |
| 🚫 **Hardware Mediation** | All hardware access must pass through kernel |
| 🧱 **Containment** | Compromise in lower ring does not automatically escalate |

---

## 🧬 Security Models

Security models define formal rules for access control based on confidentiality or integrity objectives.

| Model | Protects | Core Rules | Pattern Recognition |
|-------|----------|------------|--------------------------|
| 🔐 **Bell-LaPadula (BLUD)** | Confidentiality | 🚫 No Read Up ↑ 🚫 No Write Down ↓ | Military classification, clearance levels, preventing data leakage downward |
| 🧱 **Biba (BibaDU)** | Integrity | 🚫 No Read Down ↓ 🚫 No Write Up ↑ | Preventing contamination of high-integrity data |
| 🧾 **Clark-Wilson** | Integrity | ✔ Well-formed transactions ✔ Separation of duties | Commercial systems, controlled programs, no direct user data modification |
| 🏦 **Brewer-Nash (Chinese Wall)** | Confidentiality | Dynamic access based on prior access | Conflict of interest scenarios (e.g., consulting firms, banks) |

```
These are formal theoretical models - not implementation technologies.
```

---

## 🗄️ Database Security Concepts  

Databases must enforce confidentiality, integrity, and separation of duties at the data layer.

| Concept | Purpose | Anchor |
|----------|---------|------------|
| 🔐 **Views** | Restrict data exposure | Limit access to specific rows/columns |
| 🧱 **Stored Procedures** | Controlled transactions | Prevent direct user table modification |
| 🧾 **Inference Control** | Prevent deduction of sensitive data from aggregates | Aggregation risk |
| 🧬 **Polyinstantiation** | Prevent inference in multilevel secure systems | Multiple rows with same key but different classification |
| 🛡️ **Data Masking** | Obfuscate sensitive data | Used in testing environments |

---

## ♻️ Resilience & Fault Tolerance  

Systems must continue operating under stress or partial failure.

| Concept | Description | Security Benefit |
|----------|------------|-----------------|
| 🔁 **Redundancy** | Duplicate components | Prevent single point of failure |
| ⚖️ **Load Balancing** | Distribute workload | Prevent resource exhaustion |
| 🧩 **Clustering** | Multiple systems operate as one | High availability |
| 🔄 **Failover** | Automatic switch to backup system | Maintains availability |
| 🛑 **Graceful Degradation** | Reduce functionality safely | Maintain critical services |

---

## 🧑‍💻 Secure Engineering Practices  

Architecture decisions must integrate secure development principles.

| Practice | Purpose | Angle |
|----------|----------|------------|
| 🔍 **Code Review** | Peer validation of secure implementation | Prevent logic flaws and injection risks |
| 🔎 **Threat Modeling** | Identify design weaknesses early | Prevent architectural flaws |
| 🧪 **Static Testing (SAST)** | Analyze source code | Detect coding errors before runtime |
| 🧬 **Dynamic Testing (DAST)** | Test running application | Identify runtime vulnerabilities |
| 🔐 **Secure SDLC Integration** | Embed security into development lifecycle | Prevent security as afterthought |

---

## 🏛️ Evaluation & Assurance Frameworks

These frameworks measure how much trust and assurance we can place in a system’s security design and implementation.

---

### 📚 TCSEC (Orange Book)

TCSEC, also known as the Orange Book, was a U.S. Department of Defense standard developed to evaluate the security of computer systems. It was heavily focused on confidentiality, drawing directly from the Bell-LaPadula model, and emphasized labeled security, mandatory access control, and increasing assurance through structured design and formal verification. TCSEC was U.S.-centric and has since been superseded by the international Common Criteria standard.

| Level | Meaning | Focus | Recognition |
|--------|--------|--------|------------------|
| 🔹 **D** | Minimal Protection | Failed evaluation | Rarely secure |
| 🔹 **C1** | Discretionary Security | Basic DAC controls | Weak user-level controls |
| 🔹 **C2** | Controlled Access | Stronger DAC + auditing | Commercial OS baseline |
| 🔹 **B1** | Labeled Security | Mandatory Access Control (MAC) | Data classification labels |
| 🔹 **B2** | Structured Protection | Formal security policy model | Increased TCB scrutiny |
| 🔹 **B3** | Security Domains | Strong isolation & minimal TCB | High assurance systems |
| 🔴 **A1** | Verified Design | Formally verified design | Mathematical proof of security |

---

### 🌍 Common Criteria (ISO/IEC 15408)

Common Criteria is the international standard successor to TCSEC and provides a standardized framework for evaluating the **security assurance** of IT products. It measures how rigorously a system has been designed, tested, reviewed, and formally verified through Evaluation Assurance Levels (EALs).  

Higher EAL levels do **not** mean stronger security features, they reflect increased confidence in the correctness of the design and the depth of evaluation evidence. 

EAL 4 is the most common commercial level. EAL 7 requires formal mathematical verification and is extremely rare, typically realistic only for small, highly constrained, security-critical systems, not large general-purpose operating systems or complex enterprise platforms.

| EAL Level | Meaning | Assurance Level | Recognition |
|------------|----------|----------------|-----------------------------|
| 🟢 **EAL 1** | Functionally tested | Basic testing | Simple |
| 🟢 **EAL 2** | Structurally tested | Basic design review | Simple |
| 🟡 **EAL 3** | Methodically tested & checked | Moderate assurance | Methodically tested |
| 🟡 **EAL 4** | Methodically designed, tested & reviewed | Commercial baseline (**most common**) | Methodically tested |
| 🟠 **EAL 5** | Semi-formally designed & tested | High assurance | Semi-formally designed |
| 🟠 **EAL 6** | Semi-formally verified design & tested | Very high assurance | Semi-formally designed |
| 🔴 **EAL 7** | Formally verified design & tested | Extremely high assurance | Formally designed & tested |

---

## 🔐 Crypto Fundamentals

Goal: recognize **what to use when** - not calculate key schedules.

---

### 🔑 Symmetric Cryptography (Bulk Data Encryption - Fast & Efficient)

Symmetric encryption uses a single shared key for both encryption and decryption and is optimized for high-speed data protection.

| Characteristic | Description | Security / Operational Impact |
|----------------|------------|-------------------------------|
| 🔁 **Shared Key** | Same key encrypts and decrypts | Requires secure key exchange |
| ⚡ **Performance** | Very fast and computationally efficient | Ideal for bulk data encryption |
| 🚨 **Main Weakness** | Key distribution & scalability challenges | Secure key management is critical |

| Algorithm | Primary Use | Notes |
|------------|------------|-------|
| 🔥 **AES (Advanced Encryption Standard)** | Disk encryption, VPNs, TLS session encryption | Most widely used symmetric cipher |
| ⚡ **ChaCha20** | Mobile devices, high-performance environments | Modern stream cipher; efficient without hardware acceleration |

| Common Use Cases | Why Symmetric Is Used |
|------------------|----------------------|
| 💾 **Disk Encryption** | Efficient full-volume data protection |
| 🌐 **VPNs** | High-speed encrypted tunnels |
| 🔐 **TLS Session Encryption** | Bulk encryption after asymmetric key exchange |


### 🔲 Block Ciphers (Symmetric Encryption - Fixed-Size Blocks)

Block ciphers encrypt data in fixed-size chunks and require a mode of operation to securely process larger data.

| Mode | Core Behavior | Security Properties | Notes |
|------|--------------|--------------------|------------|
| 📕 **ECB (Electronic Codebook)** | No IV; identical plaintext blocks produce identical ciphertext | ❌ Confidentiality weakness (pattern leakage) | Avoid; only acceptable for very short, non-sensitive data |
| 🔄 **CBC (Cipher Block Chaining)** | Uses IV; each block chained to previous ciphertext | ✅ Confidentiality only | Older mode; no built-in integrity protection |
| 🏎️ **CTR (Counter Mode)** | Uses counter + nonce; behaves like a stream cipher | ✅ Confidentiality only | Fast; parallelizable; must not reuse nonce |
| 🥇 **GCM (Galois/Counter Mode)** | CTR + authentication tag | ✅ Confidentiality + Integrity (AEAD) | Golden standard for modern encryption |
| 💾 **XTS (XEX-based Tweaked CodeBook with CipherText Stealing)** | Designed for storage encryption | ✅ Confidentiality (disk-level) | Used for full disk encryption; not for general data transport |

### 🌊 Stream Ciphers (Symmetric Encryption - Bit-by-Bit)

Never reuse a **nonce or keystream** with the same key | Reuse causes keystream duplication, allowing attackers to recover plaintext and compromise confidentiality

| Characteristic | Description | Security / Operational Impact |
|----------------|------------|-------------------------------|
| 🔁 **Keystream Generation** | Produces a continuous pseudorandom keystream | Combined with plaintext to produce ciphertext |
| 🔀 **Encryption Method** | Plaintext ⊕ Keystream (XOR operation) | Simple and efficient transformation |
| ⚡ **Performance** | Very fast, low latency | Suitable for real-time environments |

### ⚙️ Logical Operations (Relevant Concepts)

Logical operations underpin cryptography and access control decisions. Understand where logical operations are used, not perform binary math.

| Operation | Relevant Use |
|------------|-------------------|
| 🔀 **XOR** | Core operation in stream ciphers (plaintext ⊕ keystream). Reapplying XOR with same key restores original data. |
| 🔗 **AND / OR** | Used in permission masking and access control logic (combining or restricting flags). |

---

### 🔓 Asymmetric Cryptography (Public / Private Key)

| Characteristic | Description | Security Implication |
|----------------|------------|----------------------|
| 🐢 **Performance** | Slower than symmetric cryptography | Not used for bulk data encryption |
| 🔐 **Key Pair** | Public key + Private key | Enables secure communication without pre-shared secret |

| Algorithm | Primary Use | Notes |
|------------|------------|-------|
| 🔥 **RSA** | ✍️ Digital signatures, 🔑 key exchange | Most widely recognized asymmetric algorithm |
| ⚡ **ECC (Elliptic Curve Cryptography)** | ✍️ Digital signatures, 🔑 key exchange | Smaller keys, efficient for 📱 mobile / IoT |
| 🤝 **Diffie-Hellman (DH)** | 🔑 Secure key exchange | Establishes shared secret over insecure channel; not encryption itself |

---

| Used For | Purpose |
|-----------|---------|
| 🔑 **Key Exchange** | Securely establish symmetric session keys |
| ✍️ **Digital Signatures** | Provide authenticity and non-repudiation |
| 🪪 **Identity & Authentication** | Validate identity using certificates and public keys |

---

### 🧾 Hash Functions (Integrity)

| Property | Description | Security Benefit |
|-----------|------------|------------------|
| 🔥 **Common Algorithm** | **SHA-256** | Widely trusted modern cryptographic hash function |
| 🔁 **One-Way Function** | Cannot reverse hash to obtain original input | Protects sensitive data (e.g., passwords) |
| 📏 **Fixed-Size Output** | Produces constant-length digest regardless of input size | Predictable, consistent hash values |

| Used For | Purpose |
|-----------|---------|
| ✅ **Integrity Checks** | Detect unauthorized modification of data |
| 🔑 **Password Storage** | Store hashed passwords instead of plaintext |
| ✍️ **Digital Signatures** | Hash message before signing to ensure integrity |

---

## 🔐 HMAC (Keyed Hash for Integrity + Authentication)

HMAC (Hash-based Message Authentication Code) is a cryptographic construction that combines a secure hash function (such as SHA-256) with a shared secret key. Unlike a plain hash, which only provides integrity, HMAC ensures both integrity and authentication by proving that the sender possesses the secret key.  

It is widely used in modern protocols because it is efficient, resistant to known hash extension attacks, and suitable for high-volume secure communications.

| Property | Description | Security Impact |
|-----------|------------|----------------|
| 🔑 **Keyed Construction** | Combines secret key + hash function (e.g., HMAC-SHA256) | Prevents forgery without knowledge of key |
| 🔒 **Integrity Protection** | Detects any modification of transmitted data | Ensures message has not been altered |
| 🪪 **Authentication** | Verifies sender knows the shared secret | Confirms message origin |
| 🚫 **No Non-Repudiation** | Uses symmetric shared key | Both parties could generate valid HMAC |
| 🛡️ **Length-Extension Resistant** | Designed to prevent hash extension attacks | More secure than plain hashing |
| ⚡ **Efficient** | Faster than digital signatures | Suitable for high-throughput systems |

---

## ✍️ Digital Signatures & PKI  

| Concept | Core Principle | How It Works | Security Property |
|----------|---------------|--------------|-------------------|
| 🔐 **Digital Signature** | Sign with **private key** | Sender signs data using their private key | 🧾 Authenticity + Integrity + Non-repudiation |
| 🔓 **Signature Verification** | Verify with **public key** | Receiver validates signature using sender's public key | ✅ Confirms signer identity and data integrity |

---

### 🌐 PKI (Public Key Infrastructure)

| Component | Role | Purpose |
|------------|------|---------|
| 🏢 **CA (Certificate Authority)** | Issues & digitally signs certificates | Establishes trust in public keys |
| 📜 **CRL (Certificate Revocation List)** | Published list of revoked certificates | Allows systems to check invalidated certs |
| 🌐 **OCSP (Online Certificate Status Protocol)** | Real-time certificate status validation | Provides live revocation status without downloading full CRL |
---

### 🔓 Crypto Attacks  

| Attack Type | Core Idea | How It Works | Primary Target / Weakness |
|-------------|-----------|--------------|----------------------------|
| 🔁 **Brute Force** | Try everything until something works | Attacker systematically attempts every possible password or key until one is accepted | 🔑 Weak passwords / small key space |
| 🎂 **Birthday Attack** | Exploit hash collision probability | Attacker generates many inputs until two produce the same hash (collision) | 🧾 Hash functions (integrity failure, collisions in weak hashes) |
| ⏱️ **Side Channel** | Observe system behavior instead of attacking algorithm directly | Learns secrets by measuring timing, power usage, electromagnetic leaks, or sound | ⚡ Implementation leakage (timing, power, TEMPEST-style signals) |
| 📤 **Chosen Plaintext (CPA)** | Control what gets encrypted | Attacker submits chosen plaintexts and analyzes resulting ciphertexts | 🔐 Encryption behavior analysis |
| 📥 **Chosen Ciphertext (CCA)** | Control what gets decrypted | Attacker submits chosen ciphertexts and studies decrypted output | 🔓 Decryption oracle / key recovery weaknesses |
| 🔍 **Known Plaintext Attack (KPA)** | Attacker has both plaintext and matching ciphertext | Analyzes patterns to derive key material | Weak encryption implementations |

---

## 💻 Trusted Hardware and Secure Boot  

| Component | Core Purpose | How It Works | Typical Use / Security Benefit |
|------------|-------------|--------------|--------------------------------|
| 🔒 **TPM (Trusted Platform Module)** | Hardware-based root of trust | Dedicated chip stores cryptographic keys, performs integrity measurements, supports attestation | 💽 Enables disk encryption (e.g., BitLocker), secure boot validation, platform integrity verification |
| 🏦 **HSM (Hardware Security Module)** | Protect high-value cryptographic keys | Dedicated tamper-resistant appliance performs secure key storage and crypto operations | 💳 Used by banks, CAs, payment systems for high-assurance cryptography |
| 🚀 **Secure Boot** | Prevent unauthorized firmware/OS loading | Verifies digital signatures before executing boot components | 🛑 Blocks tampered boot loaders and rootkits |
| 📏 **Measured Boot** | Detect boot-time tampering | Records cryptographic measurements of boot components for later attestation | 🔍 Enables integrity verification and remote attestation |

---

## 🧪 Memory and Process Protection  

Goal: isolate processes so one compromise does not own the whole system.

| Mechanism | Core Purpose | How It Works | Security Benefit |
|------------|-------------|--------------|------------------|
| 🧩 **Process Isolation** | Separate processes from each other | Each process runs in its own protected address space | Prevents one compromised process from affecting others |
| 🗂️ **Memory Segmentation / Paging** | Enforce memory boundaries | Hardware (MMU) restricts memory access between processes | Stops unauthorized memory reads/writes |
| 🔐 **ACLs & Capabilities** | Control subject-object access | Define which subjects (users/processes) can access which objects (files, memory, devices) | Enforces least privilege and access control |
| ⚙️ **Execution States** | Separate privilege levels | 🧑‍💻 User Mode (restricted) vs 🧠 Kernel Mode (full access) | Limits damage if user-space process is compromised |

---

## 🦠 Malware Basics  

| Type | Core Behavior | How It Spreads / Operates | Key Variants |
|------|--------------|----------------------------|----------------------|
| 🧬 **Virus** | Requires a host file; attaches and infects legitimate files | Spreads when infected file is executed or shared | 📄 **Macro virus** - abuses Office macros<br>💽 **Boot sector virus** - infects boot loader / MBR<br>🕵️ **Stealth / Polymorphic** - hides or mutates to evade AV<br>🧩 **Multipartite** - multiple infection vectors |
| 🪱 **Worm** | Self-contained malicious program | Spreads automatically over networks without user action | 🌐 Network-based propagation; no host file required |
| 🎭 **Trojan** | Disguised as legitimate software | User installs it believing it is useful | 🚪 Often delivers backdoors, payloads, or additional malware |
| 🔐 **Ransomware** | Encrypts data and demands payment | Delivered via phishing, exploits, or trojans | 💰 Goal: financial extortion |
| 👁️ **Spyware** | Secretly monitors user activity | Installed via trojans or malicious downloads | 📊 Goal: data collection / surveillance |
| 🧱 **Rootkit** | Hides presence of malware or attacker | Modifies OS or kernel-level components | 🕳️ Goal: persistence and stealth |

---

## 🚨 Fire Detection Types

| Detection Type     | What It Detects                            | Purpose                                | Typical Use Case              | Anchor |
|--------------------|-------------------------------------------|----------------------------------------|-------------------------------|--------------|
| 🌡️ Fixed Temperature | Reaches preset heat threshold              | Triggers at specific temperature       | General rooms                 | Specific heat reached |
| 🚀 Rate-of-Rise      | Rapid temperature increase                 | Detects sudden heat changes            | Data centers, network closets | Sudden temperature spike |
| ☢️ Ionization        | Small smoke particles (fast flaming fires)| Fast response to active flames         | Older smoke detectors         | Fast-burning smoke |
| 💨 Photoelectric     | Large smoke particles (smoldering fires)  | Better for slow-burning fires          | Offices, commercial spaces    | Smoldering smoke |
| 🚀 Aspirating (VESDA)| Airborne combustion particles (very early)| Very early smoke detection             | Server rooms                  | Early warning smoke |

---

## 🔥 Fire Classes and Suppression  

| Class | Memory Anchor | Fire Type | Typical Environment |
|--------|---------------|------------|--------------------------------|
| **Class A** | 📦 **Ash** | Ordinary combustibles | 📃 Paper, 🪑 furniture, 🧃 plastics |
| **Class B** | 🧪 **Boil** | Flammable liquids & gases | ⛽ Fuel, 🧪 solvents, 🛢️ oils |
| **Class C** | 🔌 **Current** | Energized electrical equipment | 💻 Servers, 🔌 power panels, 📡 live equipment |
| **Class D** | ⚙️ **Dent** | Combustible metals | 🧲 Magnesium, 🔩 titanium, 🌫 metal dust |
| **Class K** | 👨‍🍳 **Kitchen** | Cooking oils & fats | 🍟 Deep fryers, 🫕 grease, 🍳 stovetops |

### 🚿 Suppression Systems  

| System Type | Mechanism | Trigger Logic | Typical Use Case |
|-------------|------------|---------------|---------------------------|
| 💧 **Wet Pipe** | Pipes are constantly filled with water | Heat activates sprinkler head > water releases immediately | Simple design, fastest response; common in office buildings |
| ❄️ **Dry Pipe** | Pipes filled with pressurized air; water held back | Heat activates head > air released > valve opens > water flows | Used in cold environments where pipes could freeze |
| 🌊 **Deluge** | Open sprinkler heads; pipes empty until activation | Detection system triggers > all heads discharge simultaneously | High-hazard industrial areas; not suitable for server rooms |
| 🚨💧 **Preaction** | Pipes empty until detection event | Detection system fills pipes > second trigger (heat) releases water | Best for data centers and areas with people & computers; reduces accidental discharge risk |
| 🧯 **Clean Agent (FM-200 / Inert Gas)** | Displaces oxygen or absorbs heat without residue | Detection-triggered | Data centers; safe for electronics |


---

## 🏢 Physical and Environmental Security  

| Layer / Category | Controls / Examples | Primary Control Function | Purpose |
|------------------|--------------------|--------------------------|----------|
| 🚧 **Perimeter** | Fences, gates, guards, lighting, CCTV | Deterrent / Preventive / Detective | Deter and detect unauthorized entry before reaching the facility |
| 🏢 **Building** | Mantraps, turnstiles, badges, locks, reception | Preventive / Detective | Control and monitor building access points |
| 🔐 **Interior** | Locked server rooms, rack locks, safes, cable protection | Preventive | Protect critical assets from internal unauthorized access |
| 🌡️ **Environmental** | HVAC, temperature & humidity control, power conditioning, UPS, generators | Preventive / Corrective / Recovery | Maintain stable operating conditions and ensure availability |
| 📡 **Emanations** | Shielding, TEMPEST controls, Faraday cages | Preventive | Reduce electromagnetic signal leakage and data interception risk |
| 🎥 **CCTV (Design Basics)** | Camera placement, coverage zones, blind spots, lighting, monitoring, retention policies | Detective / Deterrent | Detect, record, and discourage physical security incidents |

---

## 📱 Embedded & Mobile System Security  

Specialized systems require constrained and hardened security design.

| System Type | Security Focus |
|--------------|----------------|
| 📱 **Mobile Devices** | Secure boot, sandboxing, app signing, MDM |
| 🤖 **Embedded Systems** | Minimal OS, limited patching capability |
| 🛰️ **IoT Devices** | Hardcoded credentials risk, firmware security, update integrity |
| 🚗 **Safety-Critical Systems** | Availability and human safety prioritized |

---

## 🏭 ICS / Operational Technology (SCADA / DCS / PLC)

| System | Stands For | Scope | Typical Environment / Examples | Primary Role |
|--------|------------|-------|--------------------------------|--------------|
| 🌍 **SCADA** | **S**upervisory **C**ontrol **A**nd **D**ata **A**cquisition | Wide-area, geographically dispersed systems | ⚡ Power grids, 💧 water utilities, 🛢 pipelines | Centralized monitoring and supervisory control over remote sites |
| 🏭 **DCS** | **D**istributed **C**ontrol **S**ystem | Single facility, tightly integrated processes | 🛢 Refinery, 🧪 chemical plant, 🏭 manufacturing plant | Continuous process control within one industrial site |
| 🤖 **PLC** | **P**rogrammable **L**ogic **C**ontroller | Device-level / machine-level control | 🛠 Individual machines, 🔧 assembly lines | Real-time control of specific equipment or processes |
