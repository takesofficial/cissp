# <p align=center>Domain 1 - Security and Risk Management</p>

## 🚨 Elevator Pitch  
Risk cannot be eliminated - only identified, analyzed, and managed.

Domain 1 establishes the governance foundation of security: aligning risk decisions with business objectives, defining policy and accountability, understanding legal and ethical obligations, managing personnel risk, overseeing third parties, conducting investigations, and ensuring continuity of operations.

---

## ⚖️ ISC2 Code of Ethics  
- Protect society and the common good.  
- Act honorably, legally, and responsibly.  
- Provide diligent and competent service.  
- Advance and protect the profession.  

### Ethics Complaint Rules
Who can file complaints
- **Canon I & II** - Anyone (including the public)
- **Canon III** - Only employer or contractual client
- **Canon IV** - Any certified professional bound by ethics

If public harm is involved, think Canon I.

---

## 🏛️ Governance  
Ensure security directly supports the business mission, goals, and risk appetite.

## 🎯 Strategic vs Tactical vs Operational Planning

| Level | Focus | Time Horizon | Owned By |
|-------|--------|--------------|----------|
| **Strategic** | Long-term direction, mission alignment | 3–5 years | Executive leadership |
| **Tactical** | Program implementation | 1 year | Senior / middle management |
| **Operational** | Day-to-day execution | Quarterly / ongoing | Operational managers |

Security strategy must align to business strategy.

---

## 🏛️ Governance Committee

Responsible for:

- Strategic oversight
- Policy approval
- Risk monitoring
- Compliance enforcement
- Role assignment
- Performance metrics review

Governance sets direction. Management executes.

---

### 📚 Documentation Hierarchy

**Policies > Standards > Baselines > Guidelines > Procedures**

- **Policy** - High-level direction from senior management; mandatory.  
- **Standard** - Mandatory, uniform requirements (config, tech, process).  
- **Baseline** - Minimum acceptable security level.  
- **Guideline** - Optional recommendations; flexible.  
- **Procedure** - Step-by-step instructions for performing tasks.

**Frameworks:** ISO 27001, NIST CSF, COBIT, CIS Controls, RMF, ISO 31000.  
**Security governance goal:** Align security with business value, risk, and objectives.

---

## 🧩 Scoping vs Tailoring (Control Selection)
Used in RMF and governance-level control decisions.

| Term | Meaning |
|------|----------|
| **Scoping** | Selecting which controls apply to a system |
| **Tailoring** | Adjusting baseline controls based on risk |

---

## 🧪 Security Control Assessment (SCA)

Formal evaluation of controls against a defined baseline.

Purpose:
- Implemented correctly?
- Operating as intended?
- Producing desired outcomes?

Often paired with **ST&E (Security Test & Evaluation)**.  
SCA is governance validation, not penetration testing.

Output:
- Formal assessment report
- Control gaps
- Remediation plan

## 👥 Roles & Responsibilities  
Assign ownership, accountability, and operational duties.
Residual risk is ALWAYS owned by senior management.

- **Senior Management** - Ultimately accountable; accepts residual risk.  
- **Owner** - Classifies data; defines access; decides on controls.  
- **Custodian** - Implements and maintains controls (backups, access).  
- **User** - Follows policy; uses resources securely.  
- **Auditor** - Reviews compliance; never accepts risk.  

---

## 🔺 CIA Triad  
Over time, the CIA model was expanded to include **Authenticity** and **Non-repudiation**, forming the **Five Pillars of Information Security**.
These pillars represent core security objectives. On the exam, questions often use synonymous wording instead of the pillar names directly.

| Pillar | Description | Key Terms | If It Fails (DAD / Equivalent) |
|--------|------------|-----------|--------------------------------|
| **Confidentiality** | Ensures an asset is accessible only to authorized users. Protects against unauthorized disclosure. | Concealment, Discretion, Sensitivity, Secrecy | **Disclosure** |
| **Integrity** | Ensures an asset is not modified or deleted in an unauthorized manner. Maintains accuracy and completeness. | Accuracy, Validity, Veracity, Authenticity | **Alteration** |
| **Availability** | Ensures authorized users can access an asset when needed. Focuses on reliability and uptime. | Accessibility, Usability, Redundancy, Resiliency | **Destruction** |
| **Authenticity** | Ensures a user, system, or data source is genuine and truly who/what it claims to be. | Genuineness, Legitimacy, Trustworthiness, Verifiability | Impersonation / Forgery |
| **Non-repudiation** | Ensures a user cannot deny performing an action or transaction. Provides proof of origin and delivery. | Irrefutability, Indisputability, Undeniability, Unquestionability | Repudiation |

---

## 🔐 AAA  
The lifecycle of identity, access, and accountability.

| Component | What It Answers | Purpose | Example |
|------------|----------------|----------|----------|
| **Identification** | Who are you? | User claims an identity. | Username: `nick.admin` |
| **Authentication** | Can you prove it? | Verifies the claimed identity. | Password, MFA token, biometric |
| **Authorization** | What are you allowed to do? | Grants or denies access based on permissions. | Access to HR database: Approved |
| **Accountability** | Who performed this action? | Links actions to a specific subject. | User ID tied to activity |
| **Auditing** | What happened? | Records and reviews events for compliance and investigation. | Log review, SIEM report |

---

## 🏷️ Identity Assurance Levels (NIST 800-63)

### Identity Assurance Level (IAL)

| Level | Description |
|-------|-------------|
| **IAL1** | Self-asserted identity |
| **IAL2** | Verified identity |
| **IAL3** | In-person verified identity |

### Authenticator Assurance Level (AAL)

| Level | Description |
|-------|-------------|
| **AAL1** | Single-factor authentication |
| **AAL2** | Multi-factor authentication |
| **AAL3** | Hardware-based MFA with cryptographic binding |

---

## 📉 Risk Management  
Risk is never eliminated - only managed.

Identify threats, evaluate vulnerabilities, calculate business impact, and select proper responses.

---

## 🎚️ Risk Appetite Model
Defined by senior management.

| Term | Meaning |
|------|----------|
| **Risk Appetite** | Amount of risk organization is willing to pursue |
| **Risk Tolerance** | Acceptable variation from objectives |
| **Risk Capacity** | Maximum risk organization can survive |

---

## Risk Formula Variations

| Expression | Meaning |
|------------|----------|
| **Risk = Likelihood × Impact** | Probability of event × Business damage |
| **Risk = Threat × Vulnerability × Asset Value** | Threat exploiting weakness affecting asset |

Both expressions represent the same concept:  
**Risk = probability combined with consequence.**

---

## Quantitative Risk Analysis

Used when numerical data is available.

| Characteristic | Description |
|---------------|------------|
| Measurement | Financial impact |
| Output | Monetary value (e.g., ALE) |
| Purpose | Cost justification and budgeting |

---

## Qualitative Risk Analysis

Used when reliable numerical data is unavailable.

| Method | Description |
|--------|------------|
| **Delphi Method** | Anonymous expert consensus rounds |
| **Brainstorming** | Group threat identification |
| **Heat Maps** | Visual likelihood vs impact matrix |
| **Subjective Ranking** | High / Medium / Low scoring |

---

## 📉 Quantitative Risk Analysis

---

## Step 1 - SLE

```
SLE = AV × EF
```

| Term | Meaning |
|------|--------|
| **AV (Asset Value)** | Total value of asset |
| **EF (Exposure Factor)** | % of loss per incident |
| **SLE (Single Loss Expectancy)** | Loss per single event |

---

## Step 2 - ALE

```
ALE = SLE × ARO
```

| Term | Meaning |
|------|--------|
| **ARO (Annualized Rate of Occurrence)** | Frequency per year |
| **ALE (Annualized Loss Expectancy)** | Expected yearly loss |

---

## Step 3 - Safeguard Value

```
Safeguard Value = ALE₁ − ALE₂ − Cost
```

| Result | Decision |
|--------|----------|
| Positive | Implement control |
| Negative | Do not implement |

---

## Formula Flow

| Step | Formula | Output |
|------|---------|--------|
| 1 | AV × EF | SLE |
| 2 | SLE × ARO | ALE |
| 3 | ALE₁ − ALE₂ − Cost | Control decision |

---

## Risk Responses

| Response | Meaning |
|----------|--------|
| **Mitigate** | Reduce risk |
| **Transfer** | Shift risk |
| **Avoid** | Eliminate activity |
| **Accept** | Management approval |
| **Deter** | Discourage threat |

---

**Residual risk = Senior management.**
---

## 📊 Risk Register  
Tracks identified risks, severity, mitigation, and status.

---

## 🧱 Control Types  
How controls are implemented.

### 1️⃣ **Administrative (Managerial)**  
Policies, training, background checks, risk management.

### 2️⃣ **Technical (Logical)**  
Firewalls, encryption, MFA, SIEM, access controls.

### 3️⃣ **Physical**  
Locks, guards, cameras, fences.

---

## ⚙️ Control Functions  
How controls behave before, during, and after incidents.

- **Preventive** - Stop incidents before they happen.  
- **Detective** - Discover events during/after occurrence.  
- **Corrective** - Fix damage after detection.  
- **Recovery** - Restore full operations after major failure.  
- **Compensating** - Alternative when the primary control is unavailable.  
- **Directive** - Guide actions (signage, rules, banners).  
- **Deterrent** - Discourage attempts (visible cameras, warnings).

---

## 📈 Maturity Models (CMM / RMM)  
Measure how consistent, repeatable, and well-governed security processes are.

### **CMM - Capability Maturity Model**
1. **Initial** - Ad hoc; chaotic.  
2. **Repeatable** - Some process consistency.  
3. **Defined** - Standardized organization-wide.  
4. **Managed** - Measured with metrics.  
5. **Optimizing** - Continuous improvement.

### **RMM - Risk Maturity Model**
- **Ad Hoc > Preliminary > Defined > Integrated > Optimized**

Higher maturity = fewer failures, more predictable outcomes.

---

## 🔗 Third-Party Governance  
Oversight of vendors, partners, and contractors.

- **On-site assessments** - Physical and operational review.  
- **Document exchange & review** - Policies, architecture, procedures.  
- **Process/policy evaluation** - Validate controls and compliance.  
- **Right-to-audit clauses** - Legal authority to inspect.  
- **Minimum security requirements** - Contractual security baselines.  
- **Continuous monitoring** - Ongoing vendor risk evaluation.

---

## 🔍 Audit the Auditor

Organizations remain accountable for:

- Vendor security posture
- Accuracy of third-party audits
- Effectiveness of external assessors

Outsourcing does not transfer accountability.

---

## 🔐 Supply Chain Risk  

Risks:
- Counterfeit hardware
- Malicious implants
- Tampered firmware
- Compromised libraries

Mitigations:
- Vendor due diligence
- Security SLAs
- Monitoring

### Technical Anchors
- Silicon Root of Trust  
- PUF (Physically Unclonable Function)  
- SBOM (Software Bill of Materials)  

---

## 📜 Law Types  
Different legal consequences and standards.

- **Civil** - Disputes; compensation; preponderance of evidence.  
- **Criminal** - Prosecuted by government; punishment; beyond reasonable doubt.  
- **Administrative** - Agency rules; fines, sanctions.

---

## 🌐 RFC 1087 - Unethical Internet Activity  

Unethical if it:
- Gains unauthorized access
- Disrupts intended use
- Wastes resources
- Destroys integrity
- Compromises privacy

---

## 🏛️ Legal & Regulatory Awareness
CISSP tests laws at two levels:
1. **U.S. or EU-based** > know it well
2. **Non-U.S./EU** > recognize it and apply general privacy principles

**👮 FedRAMP concepts:**
- 3PAO
- ATO
- Impact levels
- Continuous monitoring

**🔴 Must Know Well (High Exam Weight)** Laws you must understand and reason about
- 🌍 **GDPR** - EU personal data protection; data subject rights and breach notification  
- 🩺 **HIPAA** - Protection of medical data (PHI); healthcare privacy and security  
- 💰 **SOX** - Financial reporting integrity and executive accountability (Sarbanes–Oxley Act)
- 💵 **GLBA** - Protection of customer financial data held by financial institutions  
- 💳 **PCI DSS** - Protection of cardholder data; contractual industry security standard  
- 🏛️ **FISMA** - Security program requirements for U.S. federal agencies and contractors  
- 🌴 **CCPA** - California consumer personal data privacy rights  
- 👮 **CFAA** - Criminal law addressing unauthorized access to computer systems  
- 📡 **ECPA** - Protection of electronic communications privacy (in transit and stored)  
- ©️ **DMCA** - Digital copyright protection and anti-circumvention rules  

**🟡 Recognize & Classify (Lower Exam Weight)** Laws you only need to recognize and classify by region and intent
You only need to know **what region they belong to** and **that they are privacy/data protection laws**.

- 🍁 **PIPEDA (Canada)** - Canadian personal data protection law.
- 🏯 **APPI (Japan)** - Japanese personal data protection law.
- 👲 **PIPL (China)** - Chinese personal information protection law.
- 🦁 **POPIA (South Africa)** - South African personal data protection law.
- 🌅 **LGPD (Brazil)** - Brazilian personal data protection law.

---

## 🌍 OECD Privacy Principles  

1. Collection limitation  
2. Data quality  
3. Purpose specification  
4. Use limitation  
5. Security safeguards  
6. Openness  
7. Individual participation  
8. Accountability  

Fallback when GDPR is not the answer.

---

## 🔐 Privacy vs Cybersecurity

| Privacy | Cybersecurity |
|----------|--------------|
| Protects individual rights | Protects systems and data |
| Focused on lawful data use | Focused on technical safeguards |
| Driven by regulation | Driven by risk management |

Privacy violations may occur without cybersecurity failure.

---

## 📑 Privacy Principles  
Rules for handling personal data.

- **Minimization** - Collect only what is needed.  
- **Purpose Limitation** - Use data for the stated purpose only.  
- **Transparency** - Tell subjects what data is collected & why.  
- **Storage Limitation** - Keep data only as long as required.  
- **Integrity/Confidentiality** - Protect against alteration/disclosure.  
- **Accountability** - Organization must prove compliance.

---

## 💥 DAD  
What happens when CIA fails.

- **Disclosure** - Unauthorized exposure (loss of confidentiality).  
- **Alteration** - Unauthorized changes (loss of integrity).  
- **Destruction** - Damage or deletion (loss of availability).

---

## 🧭 Due Care vs Due Diligence  
Legal and defensive security responsibilities.

- **Due Diligence** - Investigate, design, document (Research and find out what to do.)
- **Due Care** - Implement, enforce, prove (Do it and prove you did it.)

---

## 🧑‍💼 Personnel Security  
Reduce human risk through controls and lifecycle management.

- **Background Check** - Criminal history, employment verification, references.  
- **NDAs** - Protect confidential info.  
- **AUP** - Defines acceptable behavior.  
- **Separation of duties** - No one person controls a full process.  
- **Job rotation** - Detect fraud; reduce dependency.  
- **Least privilege** - Minimum access required.

### 🔄 Employment Lifecycle  
- **Onboarding** - Accounts, training, access provisioning.  
- **Transfer** - Adjust access to match new role.  
- **Termination** - Immediate access removal; collect assets.

---

## 🔍 Investigations  
Apply correct legal and procedural rules.

- **Administrative** - HR or management; policy violations.  
- **Civil** - Private disputes; financial damages.  
- **Criminal** - Law enforcement; crimes; highest standard.  
- **Regulatory** - Agencies enforcing industry rules.  
- **Industry Standards** - PCI, ISO, SOC audits.

## 📊 Service Organization Controls (SOC)

**SOC = what kind of controls?**
- **SOC 1** > Money / financial reporting
- **SOC 2** > Security and system controls
- **SOC 3** > Public, marketing-safe summary of SOC 2

**Type = how deep is it?**
- **Type 1** > Looks good on paper  
  (control **design assessed by an independent auditor**, point in time)
- **Type 2** > Proved it works  
  (control **design and operating effectiveness tested by an independent auditor** over time)


### 🧪 Key Forensics Rules  
- **Chain of custody** - Track every handoff of evidence.  
- **Order of volatility** - RAM > disk > logs > archival data.  
- **Admissibility** - Evidence must be legal, reliable, unaltered.

---

## 🕒 Business Continuity  
Ensure critical operations survive incidents and resume quickly.

### **BCP Phases**  
1. Scope & Planning  
2. **BIA** - Identify impacts  
3. Continuity Strategy (mitigation + recovery)  
4. Approval, Training, Testing, Maintenance  

### **BIA Outputs**  
- **RTO** - How fast to restore.  
- **RPO** - How much data loss is acceptable.  
- **MTD** - Max downtime before business fails.

### **COOP**  
Continuity of Operations Plan - Long-term functionality of essential services.

---

## 🔗 Supply Chain Risk  
Ensure vendors do not introduce vulnerabilities or tampered components.

- Vendor due diligence  
- Third-party risk assessments  
- SLAs, BPAs, and security addendums  
- Component provenance  
- Tampering and counterfeit risk  
- Continuous monitoring  

---

## 🔄 Mergers, Acquisitions, Divestitures Risk

| Scenario | Risk |
|-----------|------|
| **Acquisition** | Unknown inherited vulnerabilities |
| **Merger** | Control misalignment and integration gaps |
| **Divestiture** | Data leakage and residual access |

Security must assess risk during business transitions.

---

## 🎯 Threat Modeling  
Identify how attackers can exploit systems and where to apply defenses.

### **Methods**  
Ⓜ️ **STRIDE** - Categorize threats.
STRIDE is a threat-focused methodology that's less strategic and thorough than PASTA. It is an acronym of:
 - Spoofing
 - Tampering
 - Repudiation
 - Information disclosure
 - Denial-of-service
 - Elevation of privilege

🍝**PASTA** - 7-stage risk-based modeling.
Process for Attack Simulation and Threat Analysis (PASTA), contrary to STRIDE, is an attacker-focused, risk-centric methodology. It is much more detailed than STRIDE and performs threat analysis from a strategic perspective.

 - Define objectives
 - Define technical scope
 - Application decomposition
 - Threat analysis
 - Vulnerability and weakness analysis
 - Attack modeling
 - Risk and impact analysis

💀 **DREAD** - Prioritize impact.
DREAD is a threat model primarily used to measure and rank the severity of threats. DREAD is often used in combination with the STRIDE model, where STRIDE identifies the threats, and DREAD is then used to rank the severity of threats. The acronym means:
 - Damage
 - Reproducibility
 - Exploitability
 - Affected users
 - Discoverabilit

- **VAST** - Scalable, Agile-friendly.  
- **Trike** - Risk auditing.  

### 🎯 Focus Areas in Threat Modeling
When analyzing a system for security risk, concentrate on the areas attackers are most likely to exploit:

- **Trust Boundaries**  
  Points where data or access moves between different trust levels (e.g., user → app, app → database, external → internal network). These transitions introduce risk and require strong controls.
- **Data Flows**  
  How information moves through the system - including storage, transmission, and processing. Evaluate confidentiality, integrity, and validation at each stage.
- **Entry Points**  
  All interfaces where an external or internal actor can interact with the system (APIs, login forms, open ports, admin panels). These define the attack surface.
- **Privileged Operations**  
  Actions that modify system state or grant elevated access (e.g., account creation, permission changes, configuration updates). These have high impact if compromised.
- **Attack Vectors**  
  The paths or techniques an attacker may use to exploit weaknesses (e.g., phishing, injection attacks, credential theft, misconfiguration).

---

## 🧠 Exam Priorities Recap (Domain 1)

### Governance & Authority
- Documentation hierarchy: **Policy > Standard > Baseline > Guideline > Procedure**
- Governance sets direction; management executes.
- Strategic vs Tactical vs Operational planning layers.
- **Senior management accepts residual risk.**

---

### Risk Foundations
- Risk expressions:
  - Risk = Likelihood × Impact
  - Risk = Threat × Vulnerability × Asset Value
- Quantitative: AV, EF, SLE, ARO, ALE, Safeguard Value.
- Qualitative: Delphi, heat maps, expert ranking.
- Risk responses: Mitigate, Transfer, Avoid, Accept, Deter.
- Risk appetite vs tolerance vs capacity.

---

### Security Objectives
- CIA vs DAD failure states.
- Authenticity and Non-repudiation as additional pillars.
- Recognize synonyms used in exam questions.

---

### Identity & Accountability
- Identification → Authentication → Authorization → Accountability → Auditing.
- Assurance levels (IAL / AAL).
- Traceability and evidence integrity.

---

### Control Structure
- Control types: Administrative / Technical / Physical.
- Control functions: Preventive / Detective / Corrective / Recovery / Compensating / Directive / Deterrent.
- Compliance is an administrative control, not risk elimination.

---

### Legal & Compliance
- Law types: Civil vs Criminal vs Administrative.
- Due care (execute) vs Due diligence (investigate).
- Core regulations: GDPR, HIPAA, SOX, GLBA, PCI DSS, FISMA, CCPA, CFAA, ECPA, DMCA.
- OECD and core privacy principles.

---

### Personnel & Investigations
- Separation of duties, least privilege, job rotation.
- Employment lifecycle controls.
- Chain of custody, order of volatility, admissibility.

---

### Business Continuity
- BCP lifecycle.
- BIA outputs: RTO, RPO, MTD.
- Continuity strategy selection.

---

### Third-Party & Supply Chain
- Right-to-audit clauses.
- Minimum security requirements.
- Continuous monitoring.
- Vendor accountability remains internal responsibility.

---

## 📦 Out of Scope / Low ROI

- Full NIST 800-53 control catalog detail.
- Deep ITIL / COSO / SABSA operational mapping.
- Vendor-specific PCI implementation steps.
- Historical legal timelines.
- Detailed M&A execution mechanics.
- Advanced AI / blockchain governance.
- Court precedent analysis.
- Project management–level BCP detail.

Focus on governance reasoning, risk decisions, and executive accountability.

--- 

## 🧠 Mind Map 
[CISSP Domain 1 Destination Certification](https://www.youtube.com/watch?v=hf5NwUSEkwA)
