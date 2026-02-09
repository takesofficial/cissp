# <p align=center>Domain 3 - Security Architecture and Engineering</p>

## 🚨 Elevator Pitch  
Design and build systems that stay secure under stress.  
Domain 3 is about security models, trusted computing, architecture principles, crypto basics, and physical protection.  
Think: how to design systems so they fail secure, limit blast radius, and keep attackers from ever getting a foothold.

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

## 🔐 Crypto Fundamentals (Domain 3 level)  

Goal: recognize what to use where, not calculate key schedules.

### Types  

- **Symmetric crypto**  
  - One shared key, fast, used for bulk encryption.  
  - Examples: AES, 3DES, ChaCha20.  
  - Problems: key distribution and scale.

- **Asymmetric crypto**  
  - Public/private key pair.  
  - Used for key exchange, digital signatures, identity.  
  - Examples: RSA, ECC, Diffie-Hellman (for key agreement).

- **Hash functions**  
  - One way, fixed size output.  
  - Used for integrity checks, password storage, digital signatures.  
  - Examples: SHA-256, SHA-3.  
  - Properties: preimage resistance, second preimage resistance, collision resistance.

### Digital Signatures and PKI  

- Sign with **private key**, verify with **public key**.  
- Provides: **integrity + authentication + non-repudiation**.  
- **PKI**: CAs issue and sign certificates, CRLs/OCSP revoke, key management is the real problem.

### Block vs Stream  

- **Block ciphers** - operate on fixed-size blocks. Need a mode of operation (CBC, GCM, etc).  
- **Stream ciphers** - generate a keystream and XOR with data. Great for real-time and error-sensitive links.

Know high level:  
- **ECB** - identical blocks produce identical ciphertext. Weak, avoid.  
- **CBC / GCM / CTR** - use IV/counter, hide patterns, commonly used.

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

- **Class A** - Fire Extinguisher / A = Ash  
- **Class B** - Combustile / B = Boil
- **Class C** - Liquid / C = Current
- **Class D** - Metal / D = Dent
- **Class K** - Oil/Fat / K = Kitchen

### Suppression Systems  

- **Wet pipe** - water in pipes, released immediately. Simple, fastest.  
- **Dry pipe** - air in pipes, water admitted when triggered. For cold areas.  
- **Deluge** - open heads, huge water volume. Industrial, not for server rooms.  
- **Preaction** - combination: detection fills pipes, second trigger opens heads.  
  - Best answer for areas with people and computers.

---

## 🏢 Physical and Environmental Security  

Big picture: stop easy physical attacks that make all logical controls useless.

- **Perimeter** - fences, gates, guards, lighting, CCTV.  
- **Building** - mantraps, turnstiles, badges, locks, reception.  
- **Interior** - locked server rooms, racks, safes, cable protection.  
- **Environmental** - HVAC, temperature and humidity control, power conditioning, UPS, generators.  
- **Emanations** - shielding, TEMPEST, Faraday cages to reduce signal leakage.  
- **CCTV basics** - placement, coverage, retention.

---

## 🏭 ICS / OT (SCADA)
Industrial Control Systems (ICS) run physical processes (OT). Expect **safety + availability first**.
**If it controls the real world** (power grid / water plant / refinery / manufacturing line) → think **ICS/SCADA**

### Types (recognize)
- **SCADA** - wide-area supervision + data acquisition (utilities, pipelines)
- **DCS** - local, process/state-driven control (plants)
- **PLC** - device-level controller (machines)

## 🎯 Exam Priorities Recap  

Recognize and apply quickly:

- TCB, reference monitor, security kernel, protection rings.  
- Which security model maps to **confidentiality** (Bell-LaPadula, Brewer–Nash/Chinese Wall) vs **integrity** (Biba, Clark–Wilson).
- Basic crypto decisions: symmetric vs asymmetric, hashing, digital signatures, PKI role of CA.  
- ECB vs CBC/GCM at a high level, and why ECB is weak.  
- What TPM/HSM do, and why HSM is used for high-value keys.  
- Difference between virus, worm, trojan, ransomware, macro virus, boot sector virus.  
- Logical operations especially XOR in the context of crypto.  
- Physical security layers and which fire suppression type fits a data center.  
- OSI layers enough to place controls and troubleshoot where a problem sits.

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)  

- Full formal proofs of all security models.  
- Detailed DES/3DES internals and full mode diagrams.  
- Exact key lengths and parameter choices for every algorithm revision.  
- Deep TPM command sets, UEFI internals, and vendor specific secure boot flows.  
- Complete malware taxonomy and every historical worm.  
- Full NFPA fire code details and building regulations.  
- All TEMPEST classification levels and measurement techniques.  
- Exhaustive OS hardening checklists and kernel tuning parameters.

---
## 🔗 Useful Links / Mind Map  
[CISSP Domain 3 Destination Certification](https://youtu.be/TreDxg9Y3yo)
