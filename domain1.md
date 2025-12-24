# <p align=center>Domain 1 - Security and Risk Management</p>

## 🚨 Elevator Pitch  
Risk cannot be eliminated. Only reduced, transferred, or accepted by senior management. Domain 1 defines governance, policy, ethics, risk analysis, legal requirements, personnel security, investigations, business continuity, and supply-chain risk.

---

## ⚖️ ISC2 Code of Ethics  
- Protect society and the common good.  
- Act honorably, legally, and responsibly.  
- Provide diligent and competent service.  
- Advance and protect the profession.  

---

## 🏛️ Governance  
Ensure security directly supports the business mission, goals, and risk appetite.

**Documentation hierarchy:**  
**Policies → Standards → Baselines → Guidelines → Procedures**

### 📚 Documentation Types
- **Policy** - High-level direction from senior management; mandatory.  
- **Standard** - Mandatory, uniform requirements (config, tech, process).  
- **Baseline** - Minimum acceptable security level.  
- **Guideline** - Optional recommendations; flexible.  
- **Procedure** - Step-by-step instructions for performing tasks.

**Frameworks:** ISO 27001, NIST CSF, COBIT, CIS Controls, RMF, ISO 31000.  
**Security governance goal:** Align security with business value, risk, and objectives.

---

## 👥 Roles & Responsibilities  
Assign ownership, accountability, and operational duties.

- **Senior Management** - Ultimately accountable; accepts residual risk.  
- **Owner** - Classifies data; defines access; decides on controls.  
- **Custodian** - Implements and maintains controls (backups, access).  
- **User** - Follows policy; uses resources securely.  
- **Auditor** - Reviews compliance; never accepts risk.  

---

## 🔺 CIA Triad  
Three core security outcomes.

- **Confidentiality** - Prevent unauthorized disclosure.  
- **Integrity** - Prevent unauthorized modification; ensure authenticity.  
- **Availability** - Ensure timely, reliable access for authorized users.

---

## 🔐 AAA  
The lifecycle of identity, access, and accountability.

- **Identification** - Claiming an identity ("I am Nick").  
- **Authentication** - Proving identity (password, token, biometric).  
- **Authorization** - What you’re allowed to access.  
- **Accountability** - Tying actions to subjects.  
- **Auditing** - Recording and reviewing events.

---

## 📉 Risk Management  
Identify threats, evaluate vulnerabilities, calculate business impact, and select proper responses.

### 🔢 Risk Equation Variants  
Some sources express risk differently. All mean the same thing:

- **Risk = Likelihood × Impact**  
- **Risk = Threat × Vulnerability × Asset Value**  
These show up in explanation-style questions but do not replace SLE/ALE.

### 🔍 Qualitative  
Used when numbers are impossible or unnecessary.

- Brainstorming - group discussion to identify threats.  
- Delphi Method - anonymous expert rounds until consensus.  
- Heat Maps - visual likelihood vs impact.  
- Subjective Ranking - high/medium/low scoring based on expert judgment.

### 🔢 Quantitative  
**Think of this as "security math for babies."
Everything you calculate here tells you HOW MUCH MONEY the company will lose.  
If you know the money, you know the risk.**

---

#### 🧩 Step 1 - SLE
**SLE = AV × EF**

- **Single Loss Expectancy (SLE)** = “How much money we lose from ONE bad event.”  
  Example: €100,000 × 0.40 = **€40,000 loss** each time it happens.

- **Asset Value (AV)** = “How much money this thing is worth.”  
  Example: A server worth **€100,000**.

- **Exposure Factor (EF)** = “How much % of the thing is destroyed when bad stuff happens.”  
  Example: A fire damages **40%** → EF = **0.40**.

---

#### 🧮 Step 2 - ALE
**ALE = SLE × ARO**

- **Annualized Loss Expectancy (ALE)** = “How much money we lose PER YEAR from this threat.”  
  Example: €40,000 × 0.2 = **€8,000 per year**.

- **Annualized Rate of Occurrence (ARO)** = “How many times per year this bad thing happens.”  
  Example: Fire happens **once every 5 years** → ARO = **0.2**.

This tells management:  
**“If we do nothing, we lose €8,000 per year from this threat.”**

---

#### 💰 Step 3
**Safeguard Value = ALE₁ - ALE₂ - Cost**

If the result is **positive**, the control is **worth it**.  
If **negative**, the control **costs more than the damage**, so don’t buy it.
**This is how you justify buying security tools without getting fired.**

- **ALE₁** = “Money we lose per year BEFORE the control.”  
- **ALE₂** = “Money we lose per year AFTER the control.”  
- **Cost** = price of the control.

---

#### 🧠 Summary (caveman mode)
1.
- **SLE** = Money lost each time bad thing happens.  
- **AV** = How much thing is worth.  
- **EF** = How much % breaks when bad thing happens.

2.
- **ALE** = Money lost per year from bad thing.    
- **ARO** = How often bad thing happens each year.  

3.
- **Safeguard Value** = Is the control worth buying?

This is the only math Domain 1 cares about. This is what CISSP wants you to recognize instantly.

### 🧭 Risk responses  
- **Mitigate** - Add controls.  
- **Transfer** - Insurance/outsourcing.  
- **Avoid** - Stop activity entirely.  
- **Accept** - Management formally accepts risk.  
- **Deter** - Discourage attacks.

**Residual risk** is ALWAYS owned by **senior management**.
**Compliance is an administrative control.**

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
- **Ad Hoc → Preliminary → Defined → Integrated → Optimized**

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

## 📜 Law Types  
Different legal consequences and standards.

- **Civil** - Disputes; compensation; preponderance of evidence.  
- **Criminal** - Prosecuted by government; punishment; beyond reasonable doubt.  
- **Administrative** - Agency rules; fines, sanctions.

---

## 📝 Major Regulations  
What each protects.

- **SOX** - Financial reporting integrity.  
- **HIPAA** - Medical data privacy/security (PHI).  
- **GLBA** - Customer financial data protection.  
- **PCI-DSS** - Credit card security (contractual).  
- **GDPR** - EU personal data rights; 72h breach notification.  
- **CCPA** - California consumer privacy rights.  
- **CFAA** - Anti-hacking law.  
- **ECPA** - Protects electronic communications (in transit + stored).  
- **DMCA** - Digital copyright & DRM protection.  
- **FISMA** - Federal agency security program requirements.

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

- **Due Diligence** - Investigation: risk assessments, documentation, policies. (Research and find out what to do.)
- **Due Care** - Execution: following and enforcing those controls. (Do it and prove you did it.)

---

## 🧑‍💼 Personnel Security  
Reduce human risk through controls and lifecycle management.

- **Screening** - Criminal history, employment verification, references.  
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

### 🧪 Key Forensics Rules  
- **Chain of custody** - Track every handoff of evidence.  
- **Order of volatility** - RAM → disk → logs → archival data.  
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

## 🎯 Threat Modeling  
Identify how attackers can exploit systems and where to apply defenses.

### **Methods**  
- **STRIDE** - Categorize threats.  
- **DREAD** - Prioritize impact.  
- **PASTA** - 7-stage risk-based modeling.  
- **VAST** - Scalable, Agile-friendly.  
- **Trike** - Risk auditing.  

### **Focus Areas**  
- Trust boundaries  
- Data flows  
- Entry points  
- Privileged operations  
- Attack vectors  

---

## 🧠 Exam Priorities Recap

Recognize and apply quickly:  
- Governance stack: policies → standards → baselines → guidelines → procedures (who writes what, what is mandatory).  
- Roles: senior management vs owner vs custodian vs user vs auditor, and who accepts residual risk (always senior management).  
- CIA vs DAD: what each violation looks like in a scenario-style question.  
- AAA: identification, authentication, authorization, accountability, auditing.  
- Risk math: AV, EF, SLE, ARO, ALE, safeguard value, and which variable a question is really asking for.  
- Qualitative vs quantitative risk: when to use which and typical qualitative techniques (Delphi, heat maps, rankings).  
- Risk responses: mitigate, transfer, avoid, accept, deter - and which one a scenario is pointing at.  
- Control types (administrative / technical / physical) vs control functions (preventive, detective, corrective, recovery, compensating, directive, deterrent).  
- Due diligence (investigation) vs due care (execution): research vs doing.
- High-level legal buckets: civil vs criminal vs administrative and why it matters in investigations.  
- Anchor regulations: SOX, HIPAA, GLBA, PCI-DSS, GDPR/CCPA, CFAA, ECPA, DMCA, FISMA (know what they broadly protect).  
- Privacy principles: minimization, purpose limitation, transparency, storage limitation, integrity/confidentiality, accountability.  
- Personnel controls: separation of duties, job rotation, least privilege, onboarding/transfer/termination access handling.  
- Investigation and forensics anchors: chain of custody, order of volatility, admissibility.  
- BCP/BIA core outputs: RTO, RPO, MTD and where they appear in lifecycle questions.  
- Third-party governance and supply chain: right-to-audit clauses, minimum security requirements, continuous monitoring.

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)  
- Full legal history and international privacy laws  
- Deep PCI-DSS configuration details  
- Full NIST 800-53 / 800-171 control catalogs  
- ITIL, COSO, SABSA deep dives  
- M&A processes, divestiture complexities  
- AI/crypto/blockchain training requirements  
- STIX, TAXII, CAPEC intel formats  
- Expanded intellectual property law (patents, trademarks, copyrights)  
- Complete BCP/DR project-management theory  
- All US-specific case law and legislative nuance

--- 

## 🧠 Mind Map 
[CISSP Domain 1 Destination Certification](https://www.youtube.com/watch?v=hf5NwUSEkwA)
