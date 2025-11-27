# <p align=center>Domain 2 - Asset Security</p>

## 🎯 Elevator Pitch  
Domain 2 is about protecting assets from cradle to grave. You classify what matters, assign owners, control access, protect data in every state, and destroy it correctly when its no longer needed.

---

## 🏷️ Classification Basics  
You protect what you classify. Labels drive handling, controls, and access.

### 📚 Common Classification Schemes  
**Government (example):**  
- Top Secret - Massive damage if disclosed.  
- Secret - Serious damage to national security.  
- Confidential - Damage but less severe.  
- Unclassified - Not sensitive.  

**Commercial (example):**  
- Confidential / Proprietary - Internal only, serious impact if leaked.  
- Private - Personal or financial info, high impact if exposed.  
- Sensitive - Needs strong protection, but not the highest tier.  
- Public - Safe to share externally.  

**Quick mapping idea:**  

| `Government` | `Commercial` |
|-------------:|-------------:|
| Top Secret   | Confidential |
| Secret       | Private      |
| Confidential | Sensitive    |
| Unclassified | Public       |

**Exam mindset:**  
- Classification is based on value, impact, and legal/regulatory needs.  
- Labels are defined in policy, applied consistently, and drive handling requirements.

---

## 💽 Assets, Data Types, and Memory  

### 💡 What Is An Asset  
Anything of value to the organization:  
- Data (most important)  
- Hardware, software, media  
- Intangibles: IP, reputation, brand, patents, copyrights, trademarks

### 🧠 Memory Types (for destruction and remanence questions)  
- ROM - Nonvolatile, not changed by users.  
- PROM - Programmable once.  
- EPROM / UVEPROM - Erased with ultraviolet light.  
- EEPROM - Erased electrically.  
- RAM - Volatile; loses contents when powered off.

### 📡 Emanations and TEMPEST  
- TEMPEST - Controls electromagnetic emanations so attackers cannot capture data from signals.  
- Countermeasures: Faraday cages, shielding, white noise, control zones.

---

## 🌊 Data States  

Protect data in every state, using appropriate controls.

- **Data at Rest** - Stored on disks, tapes, backups, cloud storage.  
  - Main controls: encryption, access controls, physical security, DRM.  

- **Data in Transit (in Motion)** - Moving over networks or between systems.  
  - Main controls: TLS, IPsec, VPNs, secure protocols, DLP on the wire.  

- **Data in Use** - In memory, being processed by CPUs.  
  - Main controls: hardening endpoints, patching, anti-malware, memory handling, CASB for SaaS.

Best single answer for confidentiality in any state: strong encryption.

---

## 👥 Roles and Ownership  

Clear ownership is required to protect anything properly.

- **Data Owner**  
  - Usually senior management or department head.  
  - Classifies data, defines handling, approves access.  

- **System Owner**  
  - Owns the system that processes/stores data.  
  - Responsible for system configuration, security plan, patching, and operations.  

- **Data Controller (GDPR)**  
  - Decides what personal data is collected and how it is processed.  

- **Data Processor (GDPR)**  
  - Processes personal data on behalf of the controller, per contract.  
  - Must protect data and follow controller instructions.  

- **Data Custodian**  
  - Day-to-day handling: backups, storage, archiving, technical protection.  

- **Data Steward**  
  - Business-focused: data quality, governance, metadata, compliance.  

- **Users / Subjects**  
  - Use data to perform work, must follow policies and only access what they are authorized to.  

Core principles: need-to-know and least privilege apply everywhere.

---

## 📦 Asset and Data Classification & Handling  

### 🏗️ Asset Classification  
- Assets (systems, devices, media) are classified based on the highest classification of data they handle.  
- Classification drives: where it can be stored, who can access it, and how it can be transported and destroyed.  
- Formal access approvals come from the owner, not IT.

### 📮 Handling Requirements  
Handling is always driven by classification, not media type.

Key practices:  
- Marking and labeling (human readable).  
- Labeling (machine readable: metadata, barcodes, QR, RFID, GPS tags).  
- Secure storage by classification.  
- Controlled transport and tracking.  
- Logging, chain of custody where necessary.  

Goal: no uncontrolled copy, movement, or disclosure of sensitive data.

---

## 🔐 Data Protection Methods  

### 🧰 Core Tools  
- **Encryption** - Primary method for confidentiality at rest and in transit.  
- **DRM** - Protects documents and media wherever they go; controls viewing, printing, forwarding.  
- **DLP**  
  - Network DLP - Watches outbound traffic.  
  - Endpoint DLP - Watches local files, printing, USB use.  
  - Cloud DLP - Integrated with cloud apps and storage.  
- **CASB**  
  - Sits between users and cloud services.  
  - Focus: visibility, data security, threat detection, compliance.  
  - Often bundles DLP, auth, logging, and policy enforcement for SaaS usage.

### 🧬 Privacy Techniques  
- **Anonymization**  
  - Permanently removes the link to individuals.  
  - Correctly done, it cannot be reversed.  

- **Pseudonymization**  
  - Replaces identifiers with pseudonyms; can be reversed using a separate mapping.  

- **Tokenization**  
  - Replaces sensitive data (like card numbers) with meaningless tokens.  
  - Mapping is stored in a secure vault.  

- **Randomized masking**  
  - Alters data so it is useful statistically but cannot be linked back to individuals (when properly done).  

Exam angle: know which method is reversible vs permanent.

---

## 🔄 Data Lifecycle  

Think: Create -> Store -> Use -> Share -> Archive -> Destroy.  
Security must exist at each step.

### 🧬 High-level Lifecycle  
1. **Creation / Collection** - Generate or collect data.  
2. **Classification & Storage** - Assign label, store securely according to classification.  
3. **Use / Processing** - Enforce need-to-know and least privilege, protect against exfiltration.  
4. **Sharing / Distribution** - Apply DRM, encryption, and proper marking.  
5. **Archiving** - Move to long-term storage with proper protection.  
6. **Destruction** - Permanently remove data per policy and classification.

Data collection guideline: if it has no clear purpose, do not collect it.

---

## 🧯 Data Retention, Location, and Maintenance  

### 🗂️ Retention  
- Keep data only as long as required by business, law, or regulation.  
- Define:  
  - What to retain  
  - How long to retain  
  - How and where it is stored  
- Trend: shorter retention to reduce legal exposure, especially for email.

### 📍 Data Location  
- Keep backups on-site and off-site.  
- Ensure sufficient distance between primary and backup locations to avoid common disasters.  

### 🧹 Data Maintenance  
- Ensure availability and integrity across lifecycle.  
- Enforce policies, standards, and procedures for storage, access, and archiving.  
- Maintain hardware and knowledge so old media can still be read while required.

---

## 💣 Data Remanence and Destruction  

Residual data is a favorite exam topic.

### 🧩 Key Terms  
- **Data Remanence** - Residual data after normal erase or delete.  
- **Erasing** - Standard delete. Data still recoverable.  
- **Clearing** - Overwriting to prevent recovery with normal tools.  
- **Purging** - Stronger than clearing, uses multiple passes or specialized tools to defeat advanced recovery.  
- **Degaussing** - Strong magnetic field to wipe magnetic media (tapes, HDDs). No effect on SSD or optical.  
- **Destruction** - Shredding, incinerating, pulverizing, melting, disintegration. Final and most reliable.  

### 🔐 Crypto Shredding  
- Encrypt data at rest, then destroy the keys.  
- Very effective for cloud environments and large-scale storage.  

### 🧪 Forensics Note  
- File carving and advanced tools can sometimes recover data after simple erasures.  
- For highly classified or sensitive media, physical destruction is the only acceptable answer.

Term to remember: defensible destruction - destruction that is controlled, documented, and compliant with law and policy.

---

## 🧾 Asset Inventory and Management  

You cannot protect what you do not know you have.

### 📋 Asset Inventory  
- **Tangible assets** - Hardware, devices, physical documents.  
- **Intangible assets** - Software, licenses, patents, trademarks, reputation, IP.  

Use:  
- CMDB or configuration management systems  
- Barcodes, RFID, QR codes  

### 🧭 Asset Management Goals  
- Track assets from acquisition to disposal.  
- Ensure correct classification, ownership, and controls.  
- Prevent data loss, theft, and license violations.  
- Ensure EOL and EOS assets are identified and handled.

---

## 🕰️ EOL and EOS (End of Life / End of Support)  

- **End of Life (EOL)** - Product no longer sold.  
- **End of Support / End of Service Life (EOS/EOSL)** - Vendor stops providing patches and support.  

Exam angle:  
- Unsupported systems are higher risk because they do not get security fixes.  
- They require compensating controls or retirement.

Also: retaining data is pointless if you no longer have:  
- Hardware that can read it  
- Software that can interpret it  
- People who know how to operate both

---

## ⚙️ Scoping, Tailoring, and Standards Selection  

### 🎛️ Baselines, Scoping, Tailoring  
- **Baseline** - Minimum required security configuration.  
- **Scoping** - Remove controls that clearly do not apply.  
- **Tailoring** - Adjust and refine controls to match business mission and environment, add compensating controls where needed.

### 📐 Standards and Compliance  
- Identify applicable standards and regulations (PCI DSS, GDPR, HIPAA, local laws).  
- Use community standards like NIST SP 800 series for structure, even when not mandated.  
- **Standards selection** - Objective, repeatable criteria to choose technologies and vendors that meet required controls.

---

## 🧠 Exam Priorities Recap  

Recognize and apply quickly:  
- Classification schemes and what they drive.  
- Data states and which controls fit each state.  
- Data lifecycle and correct destruction methods.  
- Roles: owner, controller, processor, custodian, steward, user.  
- Privacy techniques: anonymization vs pseudonymization vs tokenization.  
- Remanence, crypto shredding, degaussing, and physical destruction.  
- EOL/EOS risk and compensating controls.  
- DLP, DRM, CASB and where they make sense.

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)

These topics appear in full textbooks but are **not** test-critical for CISSP Domain 2 and were intentionally excluded to keep this chapter compact:

- Full government classification procedures and clearance adjudication  
- Detailed GDPR article-by-article legal analysis  
- All U.S.-specific data disposal statutes and case law  
- Deep-dive memory architecture (flip-flops, DRAM cells, SLC/MLC/TLC SSD internals)  
- Complete NIST SP 800-88 tables (clear, purge, destroy matrix)  
- Full CASB architectural variants (forward proxy, reverse proxy, API-mode internals)  
- Detailed DRM vendor feature comparisons  
- DLP tuning and rule-writing methodology (regex tuning, fingerprinting, EDM/IDM)  
- Every anonymization model (k-anonymity, l-diversity, t-closeness)  
- TEMPEST shield design standards (NSTISSAM specifics)  
- Forensics-level remanence recovery techniques  
- Complete software licensing frameworks  
- Intellectual property law structures beyond definitions (USPTO process, WIPO treaties)  
- Full asset management frameworks (ISO 19770, ITAM maturity models)  
- Extensive cloud data residency law breakdowns  
- Detailed archival formats and storage media physics  
- All vendor-specific CASB, DLP, and DRM deployment patterns  

---

## 🔗 Useful Links / Mind Map  
[Asset Classification MindMap (1 of 1) | CISSP Domain 2](https://www.youtube.com/watch?v=WBlQQ6qTlGI)
