# <p align=center>Domain 3 - Security Architecture and Engineering</p>

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

## 🧱 Trusted Computing Concepts  

Trusted computing defines the minimal components required to enforce a system's security policy.

| Concept | Definition | Key Properties | Exam Focus |
|----------|------------|----------------|------------|
| 🏛️ **Trusted Computing Base (TCB)** | All hardware, firmware, and software that enforce the security policy | Smaller TCB = easier to verify and trust | Scope of what must be trusted |
| 👁️ **Reference Monitor** | Conceptual access control engine that validates every access request | ✔ Tamperproof ✔ Always invoked ✔ Small and simple | Theoretical model of access enforcement |
| 🧠 **Security Kernel** | Implementation of the reference monitor within the OS | Runs in most privileged mode | Enforces access control in practice |
| 🧿 **Protection Rings** | Hierarchical privilege levels within CPU architecture | 🥇 Ring 0 - Kernel (most trusted) ⚙ Ring 1/2 - OS services, drivers 👤 Ring 3 - User space (least trusted) | Isolation of privileges and fault containment |

---

## 🧬 Security Models

Security models define formal rules for access control based on confidentiality or integrity objectives.

| Model | Protects | Core Rules | Exam Pattern Recognition |
|-------|----------|------------|--------------------------|
| 🔐 **Bell-LaPadula (BLUD)** | Confidentiality | 🚫 No Read Up<br>🚫 No Write Down | Military classification, clearance levels, preventing data leakage downward |
| 🧱 **Biba (BibaDU)** | Integrity | 🚫 No Read Down<br>🚫 No Write Up | Preventing contamination of high-integrity data |
| 🧾 **Clark-Wilson** | Integrity | ✔ Well-formed transactions<br>✔ Separation of duties | Commercial systems, controlled programs, no direct user data modification |
| 🏦 **Brewer-Nash (Chinese Wall)** | Confidentiality | Dynamic access based on prior access | Conflict of interest scenarios (e.g., consulting firms, banks) |

---

| Other Formal Models | What to Know |
|---------------------|------------------------|
| **Goguen-Meseguer** | Non-interference / information flow model |
| **Sutherland** | Information flow integrity |
| **Lattice Models** | Mathematical structure for ordered security levels |

```
These are formal theoretical models - not implementation technologies.
```

---

## 🏗️ Governance > Risk > Controls > Architecture > Operations (Unified Model)

Security flows from governance decisions down to operational enforcement.

| Layer | Primary Purpose | Frameworks / Standards | Core Steps / Structure | Trigger |
|--------|----------------|------------------------|------------------------|--------------------|
| 🏛️ **Governance** | Align security with business objectives & risk appetite | COBIT, ISO 27001, COSO | Evaluate > Direct > Monitor (COBIT)<br>PDCA (ISO 27001) | Board oversight, policy approval |
| 📊 **Enterprise Risk** | Identify and manage organizational risk | ISO 31000, NIST 800-30 | Identify > Analyze > Evaluate > Treat > Monitor | Risk register, enterprise risk discussion |
| 🧭 **Control Selection** | Determine required safeguards | NIST 800-53, ISO 27002, PCI DSS | Control families / Annex A / 12 PCI requirements | "Which control applies?" |
| 🏛️ **System Authorization** | Authorize systems to operate | NIST RMF (800-37), FISMA | Prepare > Categorize > Select > Implement > Assess > Authorize > Monitor | ATO, federal system lifecycle |
| ☁️ **Cloud Authorization** | Standardize federal cloud approval | FedRAMP | Categorize > 3PAO Assessment > ATO > Continuous Monitoring | 3PAO, cloud impact levels |
| 🧱 **Architecture & Engineering** | Design systems to enforce controls securely | SABSA, NIST SP 800-160 | Business requirements > Architecture layers > Secure design | Defense in depth, TCB |
| ⚙️ **Operations & Service Mgmt** | Maintain secure daily operations | ITIL | Strategy > Design > Transition > Operation > Continual Improvement | Incident, change, problem management |
| 🏥 **Regulatory Enforcement** | Mandate sector-specific compliance | HIPAA, SOX, PCI DSS | Safeguard categories / internal controls / 12 PCI controls | Industry breach scenario |
| 📈 **Internal Control & Financial Assurance** | Prevent financial fraud & reporting errors | COSO | Control environment > Risk assessment > Control activities > Info & communication > Monitoring | Financial system integrity |

---

## 🏛️ Security Frameworks, Standards & Regulations (What They're Used For)

These frameworks define governance, control selection, auditing, compliance, and system authorization requirements.

| Framework / Regulation | Type | What It's Used For | Core Structure / Steps | Anchor |
|------------------------|------|-------------------|------------------------|-------------------|
| 🌍 **ISO 27001** | International Standard (Certifiable) | Establishing and certifying an ISMS (Information Security Management System) | PDCA Cycle: Plan > Do > Check > Act | "ISMS certification", risk-based governance |
| 📘 **ISO 27002** | Control Guidance | Implementation guidance for security controls | Control domains mapped to Annex A of ISO 27001 | "How to implement controls" |
| 🇺🇸 **NIST RMF (SP 800-37)** | Risk Framework | Authorizing and managing security of federal systems | Prepare > Categorize > Select > Implement > Assess > Authorize > Monitor | ATO, federal system lifecycle |
| 🇺🇸 **NIST SP 800-53** | Control Catalog | Selecting baseline security & privacy controls | Control families (AC, IA, SC, etc.) mapped to impact level | "Which control applies?" |
| 🇺🇸 **FIPS 199** | Federal Standard | Impact categorization of systems | Low / Moderate / High impact levels | Drives 800-53 baseline selection |
| 🛡️ **FISMA** | U.S. Federal Law | Mandates federal agency security programs | Requires RMF + continuous monitoring | Federal contractor compliance |
| ☁️ **FedRAMP** | U.S. Cloud Authorization Program | Standardized security assessment for federal cloud providers | Categorize > 3PAO Assessment > ATO > Continuous Monitoring | 3PAO, reuse of ATO, cloud impact levels |
| 📊 **COBIT** | IT Governance Framework | Aligning IT controls with business objectives; auditing & governance | Governance & Management Objectives (Evaluate, Direct, Monitor) | Board-level governance, audit alignment |
| ⚙️ **ITIL** | IT Service Management | Managing IT operations & service lifecycle | Service Strategy > Design > Transition > Operation > Continual Improvement | Incident, change, problem management |
| 🏥 **HIPAA** | U.S. Regulation | Protecting healthcare data (PHI) | Administrative, Physical, Technical safeguards | Healthcare breach scenario |
| 💰 **SOX** | U.S. Regulation | Financial reporting integrity & internal controls | Internal control requirements over financial systems | Separation of duties, audit trails |
| 💳 **PCI DSS** | Industry Standard | Protecting cardholder data | 12 control requirements | Payment processing environment |
| 📈 **ISO 31000** | Risk Management Standard | Enterprise risk management | Establish Context > Identify > Analyze > Evaluate > Treat > Monitor | Enterprise risk lifecycle |

---

## 🧭 Which Framework Do I Use?

Choose the framework based on the business objective, regulatory scope, and system environment.

| Scenario | Use This | Why |
|----------|----------|-----|
| Board wants IT governance alignment | 📊 COBIT | Aligns IT objectives with business strategy; audit-focused |
| Organization wants security certification | 🌍 ISO 27001 | Certifiable ISMS standard |
| Need guidance on implementing controls | 📘 ISO 27002 | Detailed control implementation guidance |
| U.S. federal system authorization | 🏛️ NIST RMF | Required for ATO under FISMA |
| Selecting federal security controls | 🇺🇸 NIST 800-53 | Official control catalog |
| Federal cloud provider authorization | ☁️ FedRAMP | Standardized cloud ATO reuse |
| Enterprise-wide risk management | 📈 ISO 31000 | Enterprise risk lifecycle |
| Improve IT operations | ⚙️ ITIL | Service management lifecycle |
| Financial reporting controls | 💰 SOX + COSO | Internal control & audit assurance |
| Healthcare data protection | 🏥 HIPAA | PHI regulatory safeguards |
| Payment card processing | 💳 PCI DSS | 12 mandatory cardholder controls |

---

## 🧠 Managerial Security Decision Flow

Security decisions flow top-down from governance to operations.

| ❓ Question | ✅ If Yes | ➡️ If No |
|-------------|----------|----------|
| 🇺🇸 Are you a U.S. federal agency or contractor? | 🏛️ Use FISMA → 📘 RMF → 📚 800-53 → 📝 ATO | ⬇️ Continue below |
| 🌍 Do you need formal certification? | 📜 ISO 27001 (ISMS certification) | ⬇️ Continue below |
| 🏢 Is this enterprise IT governance alignment? | 📊 COBIT | ⬇️ Continue below |
| 💰 Is this financial reporting risk? | 🧾 SOX + 📈 COSO | ⬇️ Continue below |
| 🏥 Is this healthcare data (PHI)? | 🩺 HIPAA safeguards | ⬇️ Continue below |
| 💳 Is this payment card data? | 🔐 PCI DSS (12 controls) | ⬇️ Continue below |
| ☁️ Is this cloud service for U.S. government? | 🛡️ FedRAMP (3PAO → ATO → Continuous Monitoring) | ⬇️ Continue below |
| ⚙️ Is this operational service improvement? | 🔄 ITIL lifecycle | 📈 Use enterprise risk framework (ISO 31000) |

---

## 🎯 Cyber Kill Chain

The Cyber Kill Chain describes the stages of a targeted attack from initial reconnaissance to achieving objectives.

| Phase | Attacker Goal | What Happens | Defensive Focus |
|-------|--------------|--------------|-----------------|
| 🔎 **1. Reconnaissance** | Gather intelligence | Identify targets, employees, technologies, IP ranges, vulnerabilities | OSINT monitoring, attack surface reduction |
| 🛠️ **2. Weaponization** | Prepare attack payload | Combine exploit with malware (e.g., malicious document, exploit kit) | Threat intelligence, malware analysis |
| 📤 **3. Delivery** | Transmit payload to victim | Phishing email, malicious link, USB drop, drive-by download | Email security, web filtering, user awareness |
| 💥 **4. Exploitation** | Trigger vulnerability | Malicious code executes by exploiting software flaw or user action | Patch management, EDR, exploit prevention |
| 📦 **5. Installation** | Establish persistence | Malware installs backdoor, rootkit, or persistence mechanism | Application control, endpoint monitoring |
| 📡 **6. Command & Control (C2)** | Maintain remote access | Infected host communicates with attacker-controlled server | Network monitoring, IDS/IPS, egress filtering |
| 🎯 **7. Actions on Objectives** | Achieve mission goal | Data exfiltration, ransomware deployment, destruction, lateral movement | DLP, segmentation, anomaly detection |

```
Break early in the chain = prevent full compromise.
```

---

## 🔐 Crypto Fundamentals

Goal: recognize **what to use when** - not calculate key schedules.

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

| Mode | Core Behavior | Security Properties | Exam Notes |
|------|--------------|--------------------|------------|
| 📕 **ECB (Electronic Codebook)** | No IV; identical plaintext blocks produce identical ciphertext | ❌ Confidentiality weakness (pattern leakage) | Avoid; only acceptable for very short, non-sensitive data |
| 🔄 **CBC (Cipher Block Chaining)** | Uses IV; each block chained to previous ciphertext | ✅ Confidentiality only | Older mode; no built-in integrity protection |
| 🏎️ **CTR (Counter Mode)** | Uses counter + nonce; behaves like a stream cipher | ✅ Confidentiality only | Fast; parallelizable; must not reuse nonce |
| 🥇 **GCM (Galois/Counter Mode)** | CTR + authentication tag | ✅ Confidentiality + Integrity (AEAD) | Golden standard for modern encryption |
| 💾 **XTS (XEX-based Tweaked CodeBook with CipherText Stealing)** | Designed for storage encryption | ✅ Confidentiality (disk-level) | Used for full disk encryption; not for general data transport |

### 🌊 Stream Ciphers (Symmetric Encryption - Bit-by-Bit)

Never reuse a **nonce / keystream** | Reuse enables attackers to recover plaintext and break confidentiality

| Characteristic | Description | Security / Operational Impact |
|----------------|------------|-------------------------------|
| 🔁 **Keystream Generation** | Produces a continuous pseudorandom keystream | Combined with plaintext to produce ciphertext |
| 🔀 **Encryption Method** | Plaintext ⊕ Keystream (XOR operation) | Simple and efficient transformation |
| ⚡ **Performance** | Very fast, low latency | Suitable for real-time environments |

| Ideal For | Reason |
|-----------|--------|
| 📞 **Real-Time Communication** (VoIP, video, wireless) | Minimal delay during encryption |
| 🔗 **Error-Sensitive Links** | Bit errors affect only corresponding bits, not entire blocks |

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

| Security Property | Meaning |
|-------------------|---------|
| 🚫 **Preimage Resistance** | Cannot determine original input from its hash |
| 🚫 **Second Preimage Resistance** | Cannot find a different input with the same hash as a known input |
| 🚫 **Collision Resistance** | Cannot find two different inputs that produce the same hash |
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

## ⚙️ Logical Operations (Crypto & Access Decisions)

Logical operations manipulate bits and are heavily used in cryptography and access control mechanisms.

| Operation | Behavior | When Result = 1 | Security Relevance |
|------------|----------|----------------|-------------------|
| 🔄 **NOT** | Flips the bit | Input 0 > 1<br>Input 1 > 0 | Bit inversion in masking and transformations |
| 🔗 **AND** | Both bits must be 1 | 1 AND 1 | Used in masking, permission checks |
| 🔓 **OR** | At least one bit is 1 | 1 OR 0 / 1 OR 1 | Combining flags or permissions |
| 🔀 **XOR** | Bits must be different | 1 XOR 0 | Core operation in stream ciphers and checksums; XORing twice with same value restores original data |

---

## 🚨 Fire Detection Types

| Detection Type     | What It Detects                            | Purpose                                | Typical Use Case              | Anchor |
|--------------------|-------------------------------------------|----------------------------------------|-------------------------------|--------------|
| 🌡️ Fixed Temperature | Reaches preset heat threshold              | Triggers at specific temperature       | General rooms                 | Specific heat reached |
| 🚀 Rate-of-Rise      | Rapid temperature increase                 | Detects sudden heat changes            | Data centers, network closets | Sudden temperature spike |
| ☢️ Ionization        | Small smoke particles (fast flaming fires)| Fast response to active flames         | Older smoke detectors         | Fast-burning smoke |
| 💨 Photoelectric     | Large smoke particles (smoldering fires)  | Better for slow-burning fires          | Offices, commercial spaces    | Smoldering smoke |
| 🚀 Aspirating (VESDA)| Airborne combustion particles (very early)| Very early smoke detection             | Server rooms                  | Early warning smoke |
| 🏭 Infrared  | Infrared energy from flames               | Detects visible flames                 | Industrial environments       | Visible flames |

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

## 🏭 ICS / Operational Technology (SCADA / DCS / PLC)

| System | Stands For | Scope | Typical Environment / Examples | Primary Role |
|--------|------------|-------|--------------------------------|--------------|
| 🌍 **SCADA** | **S**upervisory **C**ontrol **A**nd **D**ata **A**cquisition | Wide-area, geographically dispersed systems | ⚡ Power grids, 💧 water utilities, 🛢 pipelines | Centralized monitoring and supervisory control over remote sites |
| 🏭 **DCS** | **D**istributed **C**ontrol **S**ystem | Single facility, tightly integrated processes | 🛢 Refinery, 🧪 chemical plant, 🏭 manufacturing plant | Continuous process control within one industrial site |
| 🤖 **PLC** | **P**rogrammable **L**ogic **C**ontroller | Device-level / machine-level control | 🛠 Individual machines, 🔧 assembly lines | Real-time control of specific equipment or processes |

---
## 🔗 Useful Links / Mind Map  
[CISSP Domain 3 Destination Certification](https://youtu.be/TreDxg9Y3yo)
