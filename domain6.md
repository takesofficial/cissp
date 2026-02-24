# <p align=center>Domain 6 - Security Assessment and Testing</p>

## 🚨 Elevator Pitch  
Trust nothing without evidence.  
Domain 6 is about **verifying** that security controls exist, work as intended, and continue to work over time.  
You assess, test, audit, and measure security to prove risk is actually being reduced.

Think: **Are the controls there? Do they work? Can you prove it?**

---

## 🧠 Assessment Mindset  

This domain is about **validation**, not design.

- Design controls > Domains 1-3  
- Operate controls > Domain 7  
- **Verify controls > Domain 6**

Management wants assurance, not guesses.

---

## 🔍 Assessment vs Testing vs Audit
These are **not the same**.
**Audits check compliance. Tests check reality.**

- **Assessment**
  - Broad evaluation of security posture
  - Policies, processes, coverage
  - Answers: *What do we have?*

- **Testing**
  - Hands-on validation
  - Proves controls actually work
  - Answers: *Can it fail?*

- **Audit**
  - Compliance-focused
  - Verifies adherence to standards or contracts
  - Answers: *Did we follow the rules?*

---

## 🧱 Control Effectiveness

A control can exist on paper and still fail in reality.

Controls are evaluated on **two dimensions**:

- **Design effectiveness**
  - Is the control designed correctly?
  - Would it work *if used properly*?

- **Operating effectiveness**
  - Is the control used consistently?
  - Does it actually work in real life?

---

## 🧾 SOC Reports (Third-Party Assurance Artifacts)

SOC reports provide **independent assurance** about a service organization's controls.  
They are used for **vendor risk management**, not internal testing.  
They provide **assurance**, not detection or prevention.

### SOC Report Types

| Report | Focus Area | Audience | Angle |
|--------|------------|----------|-------------|
| SOC 1 | Financial reporting controls (ICFR) | Auditors, finance | Impacts financial statements |
| SOC 2 | Security, availability, processing integrity, confidentiality, privacy | Customers, partners | Most common vendor assurance |
| SOC 3 | Public summary of SOC 2 | General public | Marketing-level summary |

---

### Type 1 vs Type 2

| Type | What It Evaluates | Time Scope | Assurance Level |
|------|------------------|------------|------------------|
| Type 1 | Design effectiveness only | Point in time | Lower |
| Type 2 | Design + operating effectiveness | Over a defined period (typically 3-12 months) | Higher |

- SOC 2 **Type 2 does NOT require a prior Type 1**
- Type 2 requires evidence collected over time
- Best ongoing vendor assurance = **SOC 2 Type 2**
- Type 1 = "designed correctly"
- Type 2 = "designed correctly and working consistently"

---

## 🧪 Types of Security Testing  

### 🧫 Vulnerability Assessment  
- Identifies **known weaknesses**
- Uses scanners and tools
- No exploitation
- Safe and repeatable

Finds *what could be exploited*, not *what is exploitable*.

---

### 🧨 Penetration Testing (Vuln scan ≠ pentest.)
- Actively **exploits vulnerabilities**
- Simulates attacker behavior
- Requires authorization
- Higher risk, higher insight

---

### 🔴🔵🟣 Red Team vs Blue Team vs Purple Team

These exercises test **real-world detection and response capability**, not just theoretical control presence.

- Red team ≠ vulnerability scan  
- Goal is **realistic attack simulation**
- Success is measured by **detection and response quality**, not just breach success
- Purple team exercises produce the **highest long-term improvement**

| Team | Role | Primary Objective | Mindset | Angle |
|------|------|------------------|----------|-------------|
| 🔴 Red Team | Simulated attacker | Exploit weaknesses | Offensive | Tests detection and response, not just prevention |
| 🔵 Blue Team | Defenders | Detect and respond to attacks | Defensive | Validates monitoring, logging, and IR capability |
| 🟣 Purple Team | Collaboration between red and blue | Improve overall security posture | Cooperative | Focuses on learning and control improvement |

---

## 📋 Test Planning and Scoping  

Testing without rules is illegal.

Before testing, define:
- Scope
- Authorization
- Rules of engagement
- Timing and impact limits
- Reporting expectations

Lack of approval = unauthorized access.

---

## 🧪 Testing Knowledge Levels

Different testing levels simulate different attacker perspectives. prioritize **realism vs depth**.

| Level | Tester Knowledge | Simulates | Typical Use | Angle | Core Takeaway |
|------|------------------|-----------|-------------|------------|---------------|
| ⬛**Black box** | None | External attacker | Perimeter testing | Realistic, limited visibility | Outside-in realism |
| ⬜**White box** | Full (source code, architecture, creds) | Insider / developer | Deep technical validation | Maximum coverage, least realistic | Maximum flaw discovery |
| 🩶**Gray box** | Partial (accounts, diagrams, roles) | Authenticated user / compromised account | Most enterprise testing | Best balance of realism + depth | **Most practical  choice** |

---

## 🧬 Application Security Testing

### Static Application Security Testing (SAST)
- Reviews source code
- Finds logic and design flaws
- Early in SDLC

### Dynamic Application Security Testing (DAST)
- Tests running applications
- Finds runtime issues
- Black-box style

### Interactive Application Security Testing (IAST)
- Combines static + dynamic
- Runs inside the application

---

## 🧪 Negative vs Interface vs Fuzz Testing (Tools miss logic flaws. Humans find them.)

- **Negative testing**
  - Invalid input
  - Boundary conditions
  - Input length, format, type

- **Interface testing**
  - Missed paths between components
  - APIs, service boundaries

- **Fuzzing**
  - Random or malformed input
  - Crashes, unexpected behavior

---

## 🔍 Code Review  

Manual review finds flaws tools miss.

Focus on:
- Authentication logic  
- Authorization checks  
- Error handling  
- Input validation  
- Logging  

Peer review reduces systemic risk.

---

## 📊 Metrics and Measurements  

If you can't measure it, you can't manage it.

### Common Metrics
- Number of vulnerabilities
- Mean Time To Detect (MTTD)
- Mean Time To Respond (MTTR)
- Patch compliance rate
- Control coverage

Metrics must be:
- Relevant
- Repeatable
- Actionable

---

## 🧾 Log Review and Monitoring (Logging without review = false security.)

Logs provide accountability and detection.

Key points:
- Logs must be **reviewed**, not just collected
- Time synchronization matters
- Retention and protection are required

---

## 🧪 Environmental and Physical Testing  

Logical security fails if physical controls fail.

Includes:
- Fire suppression tests
- Power failover tests
- UPS and generator testing
- HVAC monitoring
- Badge and access testing

---

## 🔄 Continuous Monitoring (**maintains assurance over time.**)

Security is not point-in-time.

- Automated control monitoring
- Ongoing alerting
- Trend analysis
- Regular reassessment

---

## 🧾 Reporting and Remediation  

Unfixed findings = accepted risk (by management).

Reports must include:
- Findings
- Risk severity
- Evidence
- Recommendations

Remediation requires:
- Assigned owner
- Target date
- Retesting

---

## ⚖️ Independence and Objectivity  

You should not test your own work.

Assessments must be:
- Independent
- Objective
- Repeatable

---

## 🔗 Useful Links / Mind Map  
[CISSP Domain 6 Destination Certification](https://youtu.be/A-aNmhB_WjM)
