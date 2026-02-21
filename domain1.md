# <p align=center>Domain 1 - Security and Risk Management</p>

## 🚨 Elevator Pitch  
Risk cannot be eliminated. Only reduced, transferred, or accepted by senior management. Domain 1 defines governance, policy, ethics, risk analysis, legal requirements, personnel security, investigations, business continuity, and supply-chain risk.

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

**Documentation hierarchy:**  
**Policies > Standards > Baselines > Guidelines > Procedures**

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
Three core security outcomes.

- **Confidentiality** - Prevent unauthorized disclosure.  
- **Integrity** - Prevent unauthorized modification; ensure authenticity.  
- **Availability** - Ensure timely, reliable access for authorized users.

### 💥 DAD (When CIA Fails)
- **Disclosure**
- **Alteration**
- **Destruction**


Non-repudiation and accountability are services built on top of it.

---

## 🔐 AAA  
The lifecycle of identity, access, and accountability.

- **Identification** - Claim identity ("I am Nick").  
- **Authentication** - Prove identity (password, token, biometric).  
- **Authorization** - What you can access.
- **Accountability** - Tying actions to subjects.  
- **Auditing** - Recording and reviewing events.

---

## 📉 Risk Management  
Identify threats, evaluate vulnerabilities, calculate business impact, and select proper responses.

### 🔢 Core Expressions
Some sources express risk differently. All mean the same thing;
- **Risk = Likelihood × Impact**  
- **Risk = Threat × Vulnerability × Asset Value**  

### 🔢 Quantitative  
**Think of this as "security math for babies."
Everything you calculate here tells you HOW MUCH MONEY the company will lose.  
If you know the money, you know the risk.**

### 🔍 Qualitative  
Used when numbers are impractical.

- Delphi Method - anonymous expert rounds until consensus.  
- Brainstorming - group discussion to identify threats.  
- Heat Maps - visual likelihood vs impact.  
- Subjective Ranking - high/medium/low scoring based on expert judgment.

---

#### 🧩 Step 1 - SLE (Money lost each time bad thing happens.)
**SLE = AV × EF**

- **Single Loss Expectancy (SLE)** = “How much money we lose from ONE bad event.”  
  Example: €100,000 × 0.40 = **€40,000 loss** each time it happens.

- **Asset Value (AV)** = “How much money this thing is worth.”  
  Example: A server worth **€100,000**.

- **Exposure Factor (EF)** = “How much % of the thing is destroyed when bad stuff happens.”  
  Example: A fire damages **40%** > EF = **0.40**.

---

#### 🧮 Step 2 - ALE (Money lost per year from bad thing.)
**ALE = SLE × ARO**

- **Annualized Loss Expectancy (ALE)** = “How much money we lose PER YEAR from this threat.”  
  Example: €40,000 × 0.2 = **€8,000 per year**.

- **Annualized Rate of Occurrence (ARO)** = “How many times per year this bad thing happens.”  
  Example: Fire happens **once every 5 years** > ARO = **0.2**.

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

#### 🧠 Summary
1.
- **SLE** = Money lost each time bad thing happens. (SLE = AV × EF)
- **AV** = How much thing is worth.  
- **EF** = How much % breaks when bad thing happens.

2.
- **ALE** = Money lost per year from bad thing. (SLE × ARO)
- **ARO** = How often bad thing happens each year.  

3.
- **Safeguard Value** = Is the control worth buying?

This is the only math Domain 1 cares about. This is what CISSP wants you to recognize instantly.

### 🧭 Risk responses  
Never ignore or deny risk.

- **Mitigate** - Add controls.  
- **Transfer** - Insurance/outsourcing.  
- **Avoid** - Stop activity entirely.  
- **Accept** - Management formally accepts risk.  
- **Deter** - Discourage attacks.

**Residual risk** is ALWAYS owned by **senior management**.
**Compliance is an administrative control.**

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
- Governance stack: policies > standards > baselines > guidelines > procedures (who writes what, what is mandatory).  
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

## 📦 What Was Intentionally Excluded (Out of CISSP Exam Scope / Low ROI)

- Detailed historical timelines of global privacy legislation  
- Vendor-specific PCI-DSS implementation steps  
- Full NIST 800-53 / 800-171 control-by-control catalogs  
- Deep operational frameworks (ITIL, COSO, SABSA architecture layers)  
- Mergers & acquisitions execution playbooks  
- Divestiture infrastructure separation strategies  
- AI / crypto / blockchain governance deep dives  
- Expanded intellectual property law (patents, trademarks, copyrights)  
- Full BCP/DR project management methodology (Gantt-level detail)  
- US-specific court precedents and legislative edge cases

--- 

## 🧠 Mind Map 
[CISSP Domain 1 Destination Certification](https://www.youtube.com/watch?v=hf5NwUSEkwA)
