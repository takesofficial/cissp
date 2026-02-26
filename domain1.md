# <p align=center>Domain 1 - Security and Risk Management</p>

## 🧠 Mind Map
[CISSP Domain 1 Destination Certification](https://destcert.com/resources/privacy-and-intellectual-property-mindmap)

## 🚨 Elevator Pitch  
Risk cannot be eliminated, only identified, analyzed, and managed. Domain 1 establishes the governance foundation of security: aligning risk decisions with business objectives, defining policy and accountability, understanding legal and ethical obligations, managing personnel risk, overseeing third parties, conducting investigations, and ensuring continuity of operations.

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

## 🏛️ Governance  
Ensure security directly supports the business mission, goals, and risk appetite. Security strategy must align to business strategy.

Governance sets direction. Management executes.

## 🏛️ Governance Committee

Responsible for:

- Strategic oversight
- Policy approval
- Risk monitoring
- Compliance enforcement
- Role assignment
- Performance metrics review

---

## 🎯 Strategic vs Tactical vs Operational Planning

| Level | Focus | Time Horizon | Owned By |
|-------|--------|--------------|----------|
| **Strategic** | Long-term direction, mission alignment | 3–5 years | Executive leadership |
| **Tactical** | Program implementation | 1 year | Senior / middle management |
| **Operational** | Day-to-day execution | Quarterly / ongoing | Operational managers |

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

## 💡 How CISSP Thinks About Controls (Read This First)

CISSP is not about fixing things after they break. It is about stopping problems before they happen, noticing them if they happen, and fixing them only when needed. This order matters.

> Always think in this sequence: **Prevent** > **Detect** > **Correct** and always think policy and process before technology.

Prevention is the strongest and cheapest control because incidents that never happen cause no damage. Detection exists because prevention is never perfect. Correction and recovery are last resorts and mean the organization already took a hit. When a question asks how to prevent something, do not choose detection or cleanup. When a question describes repeated incidents, the answer is almost never "fix the system" but "fix the process, policy, or control that should have prevented it." CISSP consistently prefers controls that are repeatable, documented, and lifecycle-based, not one-time technical fixes.

Security is risk management, not risk elimination. The best answer reduces risk enough while aligning with business goals, policies, and laws. Controls should be sustainable, cost-effective, and driven by governance, not impulse.

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

## 🧱 Control Types  
How controls are implemented.

### 1. **Administrative (Managerial)**  
Policies, training, background checks, risk management.

### 2. **Technical (Logical)**  
Firewalls, encryption, MFA, SIEM, access controls.

### 3. **Physical**  
Locks, guards, cameras, fences.

---

## 📉 Risk Management  
Risk is never eliminated - only managed. Identify threats, evaluate vulnerabilities, calculate business impact, and select proper responses.

---

## 🎚️ Risk Appetite Model
Defined by senior management.

| Term | Meaning |
|------|----------|
| **Risk Appetite** | Amount of risk organization is willing to pursue |
| **Risk Tolerance** | Acceptable variation from objectives |
| **Risk Capacity** | Maximum risk organization can survive |

---

## 🔁 Risk Management Lifecycle  
Security is a continuous management process, not a one-time calculation. Risk management never stops. Controls reduce risk, they do not eliminate it.  Residual risk remains and must be owned by senior management.

| Phase | What Happens | CISSP Terms You'll See | Output |
|--------|-------------|------------------------|--------|
| Identify | Discover assets, threats, vulnerabilities, and business context | Asset inventory, threat modeling, vulnerability assessment | Risk register entries |
| Analyze | Determine likelihood and impact (qualitative or quantitative) | Risk assessment, SLE, ALE, likelihood x impact | Risk rating / ALE / prioritization |
| Treat | Select response strategy (mitigate, transfer, avoid, accept) | Risk response, mitigation, insurance, avoidance | Implemented controls |
| Monitor | Continuously review risk posture and control effectiveness | Continuous monitoring, audits, metrics, governance review | Updated risk register |

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

## Risk Responses

| Response | Meaning |
|----------|--------|
| **Avoid** | Eliminate activity |
| **Mitigate** | Reduce risk |
| **Transfer** | Shift risk |
| **Accept** | Management approval |
| **Deter** | Discourage threat |

---

**Residual risk = Senior management.**

---

## 📊 Risk Register  
Tracks identified risks, severity, mitigation, and status.

---

## 🎯 Threat Modeling  

### **Methods**

Ⓜ️ **STRIDE**
- Spoofing  
- Tampering  
- Repudiation  
- Information Disclosure  
- Denial of Service  
- Elevation of Privilege  

🍝 **PASTA**
- Define objectives  
- Define technical scope  
- Application decomposition  
- Threat analysis  
- Vulnerability and weakness analysis  
- Attack modeling  
- Risk and impact analysis  

💀 **DREAD**
- Damage  
- Reproducibility  
- Exploitability  
- Affected users  
- Discoverability  

🧠 **VAST**
- Visual, Agile, and Simple Threat modeling  

🔺 **Trike**
- Risk-based threat modeling focused on assets and stakeholder-defined risk tolerance  

---

## 🏛️ NIST SP 800-37 Rev. 2 - Risk Management Framework (RMF) 

A structured U.S. federal approach to managing security controls at the system level.
RMF is system-focused. It operationalizes risk decisions made at the governance level.

```
Prepare → Categorize → Select → Implement → Assess → Authorize → Monitor
```

| Step        | Purpose                                                | Output                     | Primary Authority / Anchor |
|-------------|--------------------------------------------------------|----------------------------|----------------------------|
| **Prepare** | Establish risk strategy and organizational context     | Risk strategy              | NIST 800-37 Rev.2          |
| **Categorize** | Determine impact level (Low / Moderate / High)      | Security category          | **FIPS 199**               |
| **Select**  | Choose baseline security controls                      | Control baseline           | **NIST 800-53**            |
| **Implement** | Deploy and configure controls                       | Operational controls       | NIST 800-53                |
| **Assess**  | Evaluate control effectiveness                         | Assessment report          | NIST 800-53A               |
| **Authorize** | Senior official formally accepts residual risk      | Authorization decision     | **ATO (Authorization to Operate)** |
| **Monitor** | Continuous oversight of controls and risk posture     | Updated risk posture       | Continuous Monitoring      |

---

## 📈 Maturity Models (Risk Maturity Modeling)  
Measure how consistent, repeatable, and well-governed security and risk processes are.

### **Capability / Process Maturity Levels**
1. **Initial** - Ad hoc; chaotic; no repeatable process.  
2. **Managed / Repeatable** - Basic planning and tracking; processes are repeatable.  
3. **Defined** - Organization-wide standardized and documented processes.  
4. **Quantitatively Managed** - Measured and controlled using metrics.  
5. **Optimizing** - Continuous improvement and root cause analysis.

### **Risk Maturity Model (RMM)**
- **Ad Hoc → Preliminary → Defined → Integrated → Optimized**

Higher maturity = more predictable outcomes, better governance, and improved risk control effectiveness.

Maturity modeling supports continuous improvement and risk management effectiveness.
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

---

---

## 🎓 Security Awareness, Education & Training Program  

Establish and maintain a formal program that reduces human risk by improving awareness, behavior, and security culture.

Security awareness is a management responsibility. Humans are a primary attack surface.

---

### 🎯 Program Objectives  

- Reduce social engineering risk  
- Improve phishing detection and reporting  
- Reinforce policy compliance  
- Support regulatory and contractual obligations  
- Strengthen organizational security culture  

---

### 🧠 Awareness vs Training vs Education  

| Type | Focus | Audience | Goal |
|------|-------|----------|------|
| **Awareness** | Broad security concepts | All employees | Change behavior |
| **Training** | Job-specific skills | IT / security staff | Build competency |
| **Education** | Formal learning | Security professionals | Develop expertise |

Awareness = behavior  
Training = skill  
Education = depth  

---

### 🛠 Methods & Techniques  

#### Social Engineering  
- Phishing  
- Spear phishing  
- Pretexting  
- Tailgating  
- Vishing / Smishing  

Employees must recognize manipulation techniques.

---

#### Phishing Simulations  
- Controlled internal campaigns  
- Measure click rates  
- Reinforce reporting behavior  

---

#### Security Champions  
- Department-level security advocates  
- Bridge between security team and business units  
- Reinforce secure behavior locally  

---

#### Gamification  
- Quizzes  
- Rewards  
- Simulated exercises  
- Competition-based engagement  

Engagement increases retention.

---

### 🔄 Periodic Content Reviews  

Content must evolve with emerging risks:

- Cryptocurrency scams  
- Artificial Intelligence misuse  
- Deepfakes  
- Blockchain fraud  
- Cloud misuse  
- Insider threats  

---

### 📊 Program Effectiveness Evaluation  

Security awareness must be measurable.

Metrics may include:

- Phishing simulation failure rate  
- Reporting rate  
- Time to report  
- Incident reduction trends  
- Policy violation metrics  
- Audit findings  

If behavior does not improve, the program is not effective.

---

## 📜 Law Types  
Different legal consequences and standards.

- **Civil** - Disputes; compensation; preponderance of evidence.  
- **Criminal** - Prosecuted by government; punishment; beyond reasonable doubt.  
- **Administrative** - Agency rules; fines, sanctions.

---

### 🧠 Intellectual Property Types

- **Copyright** – Protects original works (software, books, music)
- **Trademark** – Protects brand names, logos, symbols
- **Patent** – Protects inventions and processes
- **Trade Secret** – Protects confidential business information

IP violations are typically civil matters but may carry criminal penalties in some cases.

---

## 🏛️ Legal & Regulatory Awareness
CISSP tests laws at two levels:
1. **U.S. or EU-based** > know it well
2. **Non-U.S./EU** > recognize it and apply general privacy principles

**🔴 Must Know Well (High Exam Weight)** Laws you must understand and reason about
- 🌍 **GDPR** - EU personal data protection; data subject rights and breach notification  
- 🩺 **HIPAA** - Protection of medical data (PHI); healthcare privacy and security  
- 💰 **SOX** - Financial reporting integrity and executive accountability (Sarbanes–Oxley Act)
- 💵 **GLBA** - Protection of customer financial data held by financial institutions  
- 💳 **PCI DSS** - Protection of cardholder data; contractual industry security standard  
- 🏛️ **FISMA** - Security program requirements for U.S. federal agencies and contractors  
- 👮 **CFAA** - Criminal law addressing unauthorized access to computer systems  
- 📡 **ECPA** - Protection of electronic communications privacy (in transit and stored)  

**🟡 Recognize & Classify (Lower Exam Weight)**

- 🌴 **CCPA** - California consumer personal data privacy rights  
- ©️ **DMCA** - Digital copyright protection and anti-circumvention rules  
- 🍁 **PIPEDA (Canada)**  
- 🏯 **APPI (Japan)**  
- 👲 **PIPL (China)**  
- 🦁 **POPIA (South Africa)**  
- 🌅 **LGPD (Brazil)**  

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

## 🧭 Due Care vs Due Diligence  

- **Due Diligence** - Investigate, design, document (Research and find out what to do.)
- **Due Care** - Implement, enforce, prove (Do it and prove you did it.)

---

## 🧑‍💼 Personnel Security  

- **Background Check**  
- **NDAs**  
- **AUP**  
- **Separation of duties**  
- **Job rotation**  
- **Least privilege**

### 🔄 Employment Lifecycle  
- **Onboarding**  
- **Transfer**  
- **Termination**

---

## 🔍 Investigations  

- **Administrative**  
- **Civil**  
- **Criminal**  
- **Regulatory**  
- **Industry Standards**

### 🧪 Key Forensics Rules  
- **Chain of custody**  
- **Order of volatility**  
- **Admissibility**

---

## 🕒 Business Continuity  

### **BCP Phases**  
1. Scope & Planning  
2. **BIA**  
3. Continuity Strategy  
4. Approval, Training, Testing, Maintenance  

### **BIA Outputs**  
- **RTO**  
- **RPO**  
- **MTD**

### **COOP**  
Continuity of Operations Plan

---

## 🔄 Mergers, Acquisitions, Divestitures Risk

| Scenario | Risk |
|-----------|------|
| **Acquisition** | Unknown inherited vulnerabilities |
| **Merger** | Control misalignment and integration gaps |
| **Divestiture** | Data leakage and residual access |
