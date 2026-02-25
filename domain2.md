# <p align=center>Domain 2 - Asset Security</p>

## 🚨 Elevator Pitch  

Protect assets from cradle to grave. You classify what matters, assign owners, control access, protect data in every state, and destroy it correctly when its no longer needed.

---

## 👥 Roles and Ownership  
Data integrity is a shared responsibility. No single role owns it. Owners set the rules, stewards govern, custodians implement controls, processors handle data correctly, and users follow policy. Everyone protects integrity, just in different ways.

| Role | Core Responsibility | Accountable For | Authority Level | CISSP Hook |
|------|---------------------|----------------|-----------------|-----------|
| **Data Owner** | Classifies data, defines handling, approves access | Data value, classification, access rules | Final authority over the data | **Ownership = authority** |
| **System Owner** | Maintains system security, configuration, patching | Operational availability + system protection | Authority over system only | **Owns the box, not the data** |
| **Data Controller (GDPR)** | Determines purpose + means of processing | Legal compliance of personal data use | Legal authority | **Decides why/how data is used** |
| **Data Processor (GDPR)** | Processes data for controller | Correct execution of processing | No independent authority | **Executes only, no decisions** |
| **Data Custodian** | Implements safeguards (backup, storage, access controls) | Day-to-day technical protection | No classification authority | **Implements controls, never classifies** |
| **Data Steward** | Governs data quality, integrity, and appropriate access | Consistency, integrity, governance alignment | Advisory only | **Ensures data is accurate + used correctly (governance layer)** |
| **User / Data Subject** | Uses or is represented by the data | Proper usage / personal data rights | No ownership | **Consumes data under least privilege** |

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

**Mapping**  

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

## 📊 Classification Criteria

Data classification is based on:

| Factor | Description |
|--------|------------|
| **Value** | Business or operational importance |
| **Sensitivity** | Impact if disclosed |
| **Criticality** | Impact if unavailable |
| **Legal / Regulatory Requirements** | Compliance obligations |

Classification is driven by impact - not convenience.

---

---

## 💽 Assets, Data Types, and Memory

### 💡 Asset Categories

| Asset Type | Examples | Notes |
|-------------|----------|-------|
| **Data (Primary Asset)** | Customer data, IP, financial records | Most important asset in Domain 2 |
| **Hardware** | Servers, laptops, network devices | Must follow lifecycle and destruction rules |
| **Software** | Applications, OS, licenses | Includes licensing compliance |
| **Media** | USB, tapes, backup drives | Subject to remanence risk |
| **Intangible Assets** | Reputation, brand, patents, copyrights, trademarks | Often highest long-term business impact |

Data is typically the highest-value asset.

---

## 🧠 Memory Types (Remanence-Relevant)

| Memory Type | Volatile? | Erasable? | Notes |
|--------------|------------|------------|------|
| **RAM** | Yes | Yes (power off) | Data lost when powered down |
| **ROM** | No | No | Firmware storage |
| **PROM** | No | No (one-time programmable) | Program once |
| **EPROM (UVEPROM)** | No | Yes (UV light) | Requires physical UV exposure |
| **EEPROM** | No | Yes (electrically) | Can be reprogrammed |

Volatile memory = loses contents without power.  
Nonvolatile memory = retains data after shutdown.

---

# 🌊 Data States

| State | Description | Primary Controls |
|--------|------------|-----------------|
| **Data at Rest** | Stored on disk, tape, cloud | Encryption, access control, physical security, DRM |
| **Data in Transit (Motion)** | Moving across networks | TLS, IPsec, VPN, secure protocols, network DLP |
| **Data in Use** | In memory during processing | Endpoint hardening, patching, anti-malware, memory controls |

Best single confidentiality control across states: **Strong encryption**.

---

# 🧮 Data Aggregation Risk

| Factor | Risk Impact |
|--------|------------|
| **Volume** | Larger datasets increase sensitivity |
| **Correlation** | Combined datasets reveal new intelligence |
| **Context** | Seemingly harmless data gains meaning when linked |

Low-classification data can become high-impact when aggregated.
Classification decisions must consider aggregation effects.

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

## 🏛️ Authority Model

| Role | Authority |
|------|----------|
| **Data Owner** | Classifies data and approves access |
| **Custodian** | Implements controls |
| **User** | Must comply with policy |

IT does not classify data. Owners do.

---

## 🔐 Data Protection Methods

- **Anonymization = irreversible**
- **Pseudonymization / Tokenization = reversible**
- Encryption protects confidentiality.
- DLP detects movement.
- DRM controls usage.
- CASB governs cloud data behavior.

### 🧰 Core Protection Controls

| Method | Purpose | Where It Applies | Key Point |
|--------|----------|----------------|-----------|
| **Encryption** | Protect confidentiality | Data at rest & in transit | Strongest single control for confidentiality |
| **DRM (Digital Rights Management)** | Control usage after access | Documents, media | Restricts viewing, printing, forwarding |
| **DLP (Data Loss Prevention)** | Detect and prevent data exfiltration | Network, Endpoint, Cloud | Monitors and blocks sensitive data movement |
| **CASB (Cloud Access Security Broker)** | Enforce cloud data security policies | SaaS / Cloud services | Adds visibility, DLP, auth, logging, compliance |

### DLP Types

| Type | Focus Area |
|------|------------|
| **Network DLP** | Monitors outbound traffic |
| **Endpoint DLP** | Monitors local files, USB, printing |
| **Cloud DLP** | Protects data inside cloud apps/storage |

---

## 🧬 Privacy & Data Transformation Techniques

| Method | Reversible? | Description | Use Case |
|--------|------------|-------------|----------|
| **Anonymization** | ❌ No | Permanently removes link to individual | Public data release |
| **Pseudonymization** | ✅ Yes | Replaces identifiers; mapping stored separately | GDPR risk reduction |
| **Tokenization** | ✅ Yes | Replaces sensitive data with token; vault stores mapping | Payment systems |
| **Randomized Masking** | Depends | Alters data while preserving statistical utility | Testing / analytics |

---

## ☁️ Cloud Data Responsibility

Cloud providers secure infrastructure.  
Customers remain responsible for:

- Data classification
- Encryption decisions
- Retention policy
- Access control
- Regulatory compliance

Outsourcing storage does not transfer ownership.

---

## 🔄 Data Lifecycle
Security must exist at every stage of the data lifecycle.
Data security is continuous, not a single control at a single stage.

### 📊 Lifecycle Stages

| Stage | Description | Primary Security Focus |
|--------|------------|------------------------|
| **Create** | Data is generated or gathered | Data minimization, lawful purpose |
| **Store** | Assign classification and store appropriately | Labeling, access control, encryption |
| **Use** | Data actively accessed or processed | Least privilege, need-to-know, endpoint security |
| **Share** | Data transmitted or disclosed | Encryption, DRM, secure transfer controls |
| **Archive** | Long-term retention storage | Secure storage, retention compliance |
| **Destroy** | Permanent removal per policy | Clear, purge, destroy, crypto shredding |

---

## 🧭 Lifecycle Control Principles

| Principle | Application |
|------------|-------------|
| **Need-to-Know** | Limit access during use and sharing |
| **Least Privilege** | Grant minimum required permissions |
| **Data Minimization** | Do not collect without defined purpose |
| **Retention Limitation** | Keep only as long as legally/business required |
| **Defensible Destruction** | Documented, compliant disposal |

---

## 📉 Data Minimization Principle

Collect and retain only what is necessary.

Reduces:
- Legal exposure
- Breach impact
- Storage cost
- Regulatory risk

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

## 📘 Media Sanitization Levels (NIST Alignment)

| Method | When Used |
|--------|----------|
| **Clear** | Reuse within same security domain |
| **Purge** | Strong sanitization against advanced recovery |
| **Destroy** | Final disposal or highest sensitivity |

Selection depends on classification and reuse intent.

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

## 🏷️ Asset Accountability Requirements

Asset records should include:

- Unique identifier
- Owner
- Location
- Classification
- Lifecycle status
- Disposal method

Untracked assets are unmanaged risk.

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

## 📡 Emanations & TEMPEST

| Concept | Purpose | Countermeasures |
|----------|----------|----------------|
| **TEMPEST** | Prevent interception of electromagnetic signals | Shielding, Faraday cages, control zones, white noise |
| **Emanation Risk** | Data leakage through unintended signals | Physical and architectural controls |

Focus: prevent signal-based data capture.

---

## ⚠️ Unsupported Systems Risk Handling
Options for EOL/EOS systems:

- Replace
- Isolate
- Apply compensating controls
- Accept risk (management decision)

Technical teams cannot unilaterally accept unsupported risk.

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

## 🔗 Useful Links / Mind Map  
[CISSP Domain 2 Destination Certification](https://www.youtube.com/watch?v=WBlQQ6qTlGI)
