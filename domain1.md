# <p align=center>Domain 1 - Security and Risk Management</p>

## 🚨 Elevator Pitch
Risk cannot be eliminated. Only reduced, transferred, or accepted by senior management. Domain 1 defines governance, policy, ethics, risk analysis, legal requirements, personnel security, investigations, business continuity, and supply-chain risk.

## ⚖️ ISC2 Code of Ethics
- Protect society and the common good.
- Act honorably and legally.
- Provide competent service.
- Advance the profession.

## 🏛️ Governance
Ensure security directly supports business mission, goals, and risk appetite.

Security must support mission, goals, and risk appetite.
Documentation hierarchy: Policies → Standards → Baselines → Guidelines → Procedures.
Frameworks: ISO 27001, NIST CSF, COBIT, CIS Controls, RMF, ISO 31000.

## 👥 Roles & Responsibilities
Assign ownership, accountability, and operational duties for protecting assets.

**Senior Management**: accountable; accepts residual risk.  
**Owner**: classifies data; defines access.  
**Custodian**: implements/maintains controls.  
**User**: follows policy.  
**Auditor**: verifies; never accepts risk.

## 🔺 CIA Triad
Three core security outcomes every control must support.

**Confidentiality**: prevent unauthorized disclosure.  
**Integrity**: prevent unauthorized modification; ensure authenticity.  
**Availability**: ensure timely, reliable access for authorized subjects.

## 🔐 AAA
The lifecycle for verifying identity, controlling access, and tracking actions.

Identification (stating your identity).  
Authentication (proving your identity).  
Authorization (what you may access).  
Accountability (trace actions to subjects).  
Auditing (record and review events).

## 📉 Risk Management
Identify threats, evaluate vulnerabilities, calculate business impact, and select proper responses.

Risk = Threat × Vulnerability.
SLE = AV × EF  
ALE = SLE × ARO  
Safeguard Value = ALE1 - ALE2 - cost.
Responses: mitigate, transfer, avoid, accept, deter.
Residual risk owned by senior management.

## 🧱 Control Types
How controls behave before, during, and after incidents.

**Administrative**: Policies + processes that guide people.  
**Technical**: Technology that enforces security.  
**Physical**: Real-world barriers that protect assets.  

## 📈 Maturity Models (CMM / RMM)
Measure how consistent, repeatable, and well-governed an organization's security and risk processes are.

### **CMM - Capability Maturity Model (5 Levels)**
1. **Initial** - ad hoc, undocumented, reactive.  
2. **Repeatable** - basic processes exist and can be repeated.  
3. **Defined** - standardized, documented organization-wide processes.  
4. **Managed** - processes measured with metrics and performance controls.  
5. **Optimizing** - continuous improvement based on feedback and lessons learned.

### **RMM - Risk Maturity Model**
Assesses how systematically an organization handles risk.

- **Ad Hoc** - chaotic; no consistent risk approach.  
- **Preliminary** - inconsistent, varies by department.  
- **Defined** - organization-wide risk framework exists.  
- **Integrated** - risk integrated into business processes; metrics used.  
- **Optimized** - strategic, proactive, continuously improving.

## ⚙️ Control Functions (when/why applied)
**Preventive**: Stop an incident before it happens.  
**Detective**: Reveal an incident as it happens or after.  
**Corrective** Fix damage after detection.  
**Recovery**: Restore full operations after major failure.  
**Compensating**: Alternate control when the primary isn't possible.  
**Directive**: Tell people what to do (rules, guidance).  
**Deterrent**: Discourage attacks through visibility and pressure.  

## 📜 Law Types
Different legal consequences, authorities, and evidentiary standards.

**Civil**: disputes; compensation; preponderance of evidence.  
**Criminal**: prosecution by government; punishment; beyond reasonable doubt.  
**Administrative**: regulatory agency rules; fines/sanctions.

## 📝 Major Regulations
The legal obligations for protecting specific categories of data or systems.

**SOX**: accuracy of financial reporting.  
**HIPAA**: medical data privacy and security.  
**GLBA**: financial customer data protection.  
**PCI-DSS**: credit card security (contractual).  
**GDPR**: EU personal data rights; 72h breach notice.  
**CCPA**: California consumer privacy rights.  
**CFAA**: anti-hacking law.  
**ECPA**: protects electronic communications.  
**DMCA**: digital copyright/DRM.  
**FISMA**: federal agency security programs.

## 📑 Privacy Principles
Rules for how organizations must collect, store, use, and protect personal data.

**Minimization**: collect only what is necessary.  
**Purpose Limitation**: use data only for stated purposes.  
**Transparency**: inform subjects how data is used.  
**Storage Limitation**: keep data only as long as needed.  
**Integrity/Confidentiality**: protect data from alteration and disclosure.  
**Accountability**: organization must prove compliance.

## 💥 DAD 
The forms of harm that occur when CIA is violated.

**Disclosure** - data becomes visible to unauthorized parties (loss of confidentiality).  
**Alteration** - data is changed, corrupted, or tampered with (loss of integrity).  
**Destruction** - data is deleted, damaged, or made unusable (loss of availability).

## 🧭 Due Care vs Due Diligence
Define planning (Diligence) vs execution (Care) responsibilities for maintaining defensible security.

**Due Diligence** (do): plan, assess risk, define controls.  
**Due Care** (choose): execute and maintain those controls.

## 🧑‍💼 Personnel Security  
Reduce risk from people by controlling trust, access, and behavior throughout the employment lifecycle.

**Screening** - verify identity, background, qualifications before hiring.  
**NDAs** - legally bind employees to protect confidential information.  
**AUP** - defines acceptable use of company systems and resources.  
**Separation of duties** - no single person controls all steps of a critical process.  
**Job rotation** - periodically switch roles to expose fraud and reduce dependency.  
**Least privilege** - employees receive only the minimum access needed for their role.

### Employment Lifecycle  
**Onboarding** - create accounts, assign least-privilege access, complete training.  
**Transfer** - adjust access rights to match new role; remove old permissions.  
**Termination** - immediately revoke access; collect assets; escort if necessary.

## 🔍 Investigations  
Apply the correct legal and procedural approach depending on who is investigating and why.

**Administrative** - internal HR or management inquiry; goal is policy enforcement.  
**Civil** - dispute between private parties; focuses on financial or contractual damages.  
**Criminal** - law enforcement investigates alleged crimes; highest evidentiary standard.  
**Regulatory** - government agency verifies compliance with industry rules (SEC, FINRA, HHS).  
**Industry Standards** - checks whether the organization meets best-practice frameworks (PCI, ISO).

**Key Forensics Rules**  
**Chain of custody** - document every handoff of evidence.  
**Order of volatility** - collect the most fragile data first (RAM → disk → logs).  
**Admissibility** - evidence must be legally obtained, reliable, and unaltered.

## 🕒 Business Continuity  
Ensure critical business operations continue or quickly resume during and after disruptions, with people and safety always first.  

**Business Continuity Plan (BCP) Phases**  
Scope & Planning → BIA (identify impacts) → Continuity Strategy (mitigation + recovery) → Approval, Training, Testing, Maintenance.

### BIA Outputs  
- **RTO** (Recovery Time Objective - how fast to restore),  
- **RPO** (Recovery Point Objective - how much data loss is tolerable),  
- **MTD** (Maximum Tolerable Downtime - maximum downtime before the business fails).  

### **COOP** 
**Continuity of Operations Plan**: How the organization keeps its most essential functions running during long-term disruptions.

## 🔗 Supply Chain Risk  
Ensure external vendors, hardware, software, and services do not introduce vulnerabilities, backdoors, counterfeit components, or operational weaknesses.  

**Key Activities**: Vendor due diligence, third-party risk assessments, on-site reviews, documentation audits, minimum security requirements.  
**Contracts**: SLAs (service levels), BPAs (business partner agreements), security addendums.  
**Focus Areas**: Component provenance, integrity of updates, tampering risk, dependency mapping, continuous monitoring of suppliers.

## 🎯 Threat Modeling  
Identify what can go wrong in a system, how attackers could exploit it, and where to place controls to prevent or limit damage.  

**Methods**: STRIDE (categorize threats), DREAD (prioritize impact), PASTA (risk-based stages), VAST (agile/scalable), Trike (risk auditing).  
**Approaches**: Adversarial (simulate attacker behavior) vs. Defensive (design-in security early).  
**Focus Areas**: Trust boundaries, data flows, entry points, privileged operations, attack vectors.

## Useful links
- [Inside Cloud and Security - Domain 1](https://www.youtube.com/watch?v=iArcmcGPp7k)
- [Security Controls](https://www.f5.com/labs/articles/education/what-are-security-controls#:~:text=Corrective%20controls%20include%20any%20measures,process%2C%20or%20rebooting%20a%20system.)
