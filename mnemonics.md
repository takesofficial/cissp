# MNEMONICS

---

## Chapter 1 - Security Governance Through Principles and Policies


- **GRC > TCP**  
  **G**overnance → **R**isk → **C**ompliance → then technical controls.
  
- **Policy Stack: PSPG**  
  **P**olicy (why) → **S**tandard (what) → **P**rocedure (how) → **G**uideline (optional tips)
  
- **AAA** = **A**uthentication, **A**uthorization, **A**ccounting
<p align="center">
<img width="512" height="768" alt="Image" src="https://github.com/user-attachments/assets/137b47b5-5e56-42db-beee-0d6767bf4cd9" />
</p>
---

## Chapter 2 - Personnel Security and Risk Management Concepts

<p align="center">
<img width="615" height="590" alt="Image" src="https://github.com/user-attachments/assets/40cf06e8-4bce-4134-90b6-d1ae3c8e8f0f" />

<img width="515" height="490" alt="Image" src="https://github.com/user-attachments/assets/4d93b4d2-c618-4ba2-bc2c-c26db77fe9d8" />
</p>


- **Risk Responses: ATMA**  
  **A**void / **T**ransfer / **M**itigate / **A**ccept (document and own it)
  
- **Care vs Diligence**  
  **Care = DO** reasonable controls  
  **Diligence = PROVE** (evaluate/monitor/verify)

---

## Chapter 3 - Business Continuity Planning


- **RTO vs RPO: "T = Time, P = Point"**  
  **RTO** = Recovery Time Objective (time to restore service)
  **RPO** = Recovery Point Objective (point-in-time data loss allowed)
  
- **Business Impact Analysis. (BIA) outputs: "R³"**  
  **R**TO / **R**PO / **R**esource priorities

### DR exercise order (least → most disruptive)
- **C-T-P-F** = **C**hecklist → **T**abletop → **P**arallel → **F**ull interruption

### RAID
- **RAID 0:** **"0 = 0 redundancy"** (striping; performance; any disk loss = data loss)
- **RAID 1:** **"1 = 1 mirror"** (mirroring; availability)
- ~~**RAID 2** and **RAID 3**~~ (effectively not used / rare)
- **RAID 5:** (striping + distributed parity; balanced; tolerates 1 disk failure; write penalty)
- **RAID 6:** (like RAID 5 but dual parity; tolerates 2 disk failures; more write penalty)
- **RAID 10 (1+0):** (mirroring + striping; performance + redundancy; higher cost)

---

## Chapter 4 - Laws, Regulations, and Compliance


- **Criminal vs Civil: "Jail vs Jail-not"**  
  Criminal = state prosecutes / jail possible  
  Civil = private dispute / money/injunction
  
- **IP: "PaCT"**  
  **P**atent (invention)  
  **C**opyright (expression)  
  **T**rademark (brand)  
  **Trade secret** (protect by secrecy)

---

## Chapter 5 - Protecting Security of Assets


- **Data states: R-U-T**  
  **R**est / **U**se / **T**ransit
  
- **Data roles: "Owner decides, Custodian applies"**  
  Owner = classification + access approval  
  Custodian = implements safeguards

---

## Chapter 6 - Cryptography and Symmetric Key Algorithms


**EHI:**  
- **E**ncrypt → confidentiality → **AES**  
  (Use modes **GCM** or **CBC**; do not use **ECB** - Eek! Clear Blocks)
- **H**ash → integrity → **SHA** family  
    → integrity + message authentication → **HMAC-SHA**
- **I**dentify/Sign → nonrepudiation → **digital signatures**

---

## Chapter 7 - PKI and Cryptographic Applications


- **PKI chain: "Leaf → Branch → Root"**  
  End-entity cert → Intermediate CA → Root CA (trust anchor)
  
- **Revocation: "CRL = list, OCSP = ask"**  
  CRL = download list  
  OCSP = query status
---

## Chapter 8 - Principles of Security Models, Design, and Capabilities

<p align="center">
 <img width="572" height="562" alt="Image" src="https://github.com/user-attachments/assets/a616215f-c09f-4d17-a3ef-26e72e407001" />
</p>

<p align="center">
  <a href="https://github.com/user-attachments/assets/223410a9-095a-469f-a931-743dbce25b32">
    CLICK HERE FOR A MORE DETAILED EXPLANATION
  </a>
</p>

### Security models

#### BELL-LAPADULA = BL(UD)
Read the letters **U D**.
- **NO READ UP**
- **NO WRITE DOWN**

#### BIBA = BIBA(DU)
Read the letters **D U**.
- **NO READ DOWN**
- **NO WRITE UP**

#### CLARK-WILSON
Not directional.

#### BREWER-NASH (CHINESE WALL)
Not directional.

#### HACKS
- **Government** → Bell-LaPadula → Confidentiality  
- **Financial Systems** → Biba → Integrity  
- **Accounting** → Clark-Wilson → Business Integrity  
- **Ethics** → Brewer-Nash → Conflict of interest

### Platform trust concepts
- **TCB** = "trusted stuff" (if it fails, security fails)
- **Reference Monitor: "ATT"**  
  **A**lways invoked, **T**amperproof, **T**iny (small/verifiable)

---

## Chapter 9 - Security Vulnerabilities, Threats, and Countermeasures

- **Threat/Vuln/Risk: "T + V = R"**  
  Threat + Vulnerability → Risk (likelihood × impact)
- **Malware quick ID: "WVT"**  
  **W**orm = self-spreads  
  **V**irus = needs host/user action  
  **T**rojan = looks legit, does bad

---

## Chapter 10 - Physical Security Requirements


- **Physical goals: DDDR**  
  **D**eter → **D**etect → **D**elay → **R**espond
- **Priority:** Life safety > everything else

---
## Chapter 11 - Secure Network Architecture and Components


<p align="center">
<img width="334" height="343" alt="Image" src="https://github.com/user-attachments/assets/f0bf42e9-1379-415a-b589-14b222340ab1" />
</p>

- **Segmentation goal: "Blast Radius"**  
OSI helps decide where to place controls. If one system is hacked, the attacker cannot move sideways to others.
This is mainly done at Layer 2 and Layer 3 (VLANs, subnets, routing rules).

---

## Chapter 12 - Secure Communications and Network Attacks


- **TLS idea:** certificates for identity + symmetric crypto for bulk protection in transit

- **IPsec: "AH = Authenticity, ESP = Privacy"**  
  AH = integrity/auth (no encryption)  
  ESP = encryption + can provide integrity
---

## Chapter 13 - Managing Identity and Authentication

- **Auth factors: K-H-A**  
  Something you **K**now / **H**ave / **A**re
  
- **Kerberos: "TGT → TGS → Service"**  
  Get TGT, trade for service ticket, use service ticket

---

## Chapter 14 - Controlling and Monitoring Access


- **Access models: "DMRA"**  
  **D**AC (owner decides)  
  **M**AC (labels)  
  **R**BAC (roles)  
  **A**BAC (attributes/context)
  
- **Privilege hygiene: "LSS"**  
  **L**east privilege  
  **S**eparation of duties  
  **S**ingle accountability (unique IDs)

---

## Chapter 15 - Security Assessment and Testing

<p align="center">
<img width="405" height="304" alt="Image" src="https://github.com/user-attachments/assets/062e3b5c-9a7e-4e35-be22-785fa0a5fd8f" />
</p>

- **Box testing: W-G-B**  
  **W**hite (full knowledge)  
  **G**ray (some)  
  **B**lack (none)

---

## Chapter 16 - Managing Security Operations

- **Backups: "FID"**  
  **F**ull  
  **I**ncremental  
  **D**ifferential
  
- **Logs: "TI"**  
  **T**roubleshooting + **I**nvestigation

---

## Chapter 17 - Preventing and Responding to Incidents

<p align="center">
<img width="318" height="314" alt="Image" src="https://github.com/user-attachments/assets/e8acf9cb-07e6-4a42-8514-31561d54a99e" />
</p>

---

## Chapter 18 - Disaster Recovery Planning

- **Restore priorities: "People → Building → IT"** (Safety first, then facilities, then systems)

- **Sites: "CHW"**  
  **C**old (space/utilities)  
  **W**arm (some gear)  
  **H**ot (ready now)

---

## Chapter 19 - Investigations and Ethics


- **Evidence handling: "C³"**  
  **C**hain of custody  
  **C**ontrol access  
  **C**onserve integrity
  
- **Ethics canons: "SPAP"**  
  **S**ociety/common good  
  **P**rincipals (diligent service)  
  **A**ct honorably/lawfully  
  **P**rofession (advance/protect)

---

## Chapter 20 - Software Development Security

<p align="center">
<img width="590" height="280" alt="Image" src="https://github.com/user-attachments/assets/eaf769fa-993a-4121-9372-aa9349ce7ce6" />
</p>

- **Web defense: "Validate IN, Encode OUT"**
- **Threat modeling: STRIDE**  
  Spoofing, Tampering, Repudiation, Info disclosure, DoS, Elevation

---

## Chapter 21 - Malicious Code and Application Attacks


- **Cross Site Scripting (XSS) vs Cross-site request forgery (CSRF)**
  - **XSS = Attacker puts a script in a website.**
  - **CSRF = Abuses the victim's logged-in session.**
  
- **Injection baseline**
  - Parameterize queries
  - Validate inputs
  - Least privilege for service accounts

---
