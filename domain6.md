# <p align=center>Domain 6 - Security Assessment and Testing</p>

## 🚨 Elevator Pitch  
Trust nothing without evidence.  
Domain 6 is about **verifying** that security controls exist, work as intended, and continue to work over time.  
You assess, test, audit, and measure security to prove risk is actually being reduced.

Think: **Are the controls there? Do they work? Can you prove it?**

---

## 🧠 Assessment Mindset  

This domain is about **validation**, not design.

- Design controls → Domains 1–3  
- Operate controls → Domain 7  
- **Verify controls → Domain 6**

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

Controls are evaluated on **two dimensions**:

- **Design effectiveness**
  - Is the control designed correctly?
  - Would it work *if used properly*?

- **Operating effectiveness**
  - Is the control used consistently?
  - Does it actually work in real life?

Exam trap: Design ≠ operation.

---

## 🧾 SOC Reports (assurance artifacts)
Used for **third-party assurance**, not internal testing.

- **SOC 1**
  - Financial reporting controls (ICFR)

- **SOC 2**
  - Security, availability, confidentiality, integrity, privacy

- **SOC 3**
  - Public summary of SOC 2

### Report Types
- **Type 1**
  - Design only
  - Point in time

- **Type 2**
  - Design + operating effectiveness
  - Tested over time

**Best ongoing vendor assurance = SOC 2 Type 2**

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

### 🔴 Red Team / 🔵 Blue Team / 🟣 Purple Team  

- **Red team** - Attacker simulation  
- **Blue team** - Defenders  
- **Purple team** - Collaboration and learning  

Goal: improve detection and response, not just break in.

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

- **Black-box**
  - No internal knowledge
  - External attacker view

- **White-box**
  - Full knowledge
  - Source code, architecture

- **Gray-box** (Often provides best value.)
  - Partial knowledge
  - Most realistic

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

If you can’t measure it, you can’t manage it.

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

Reports must include:
- Findings
- Risk severity
- Evidence
- Recommendations

Remediation requires:
- Assigned owner
- Target date
- Retesting

Unfixed findings = accepted risk (by management).

---

## ⚖️ Independence and Objectivity  

Assessments must be:
- Independent
- Objective
- Repeatable

You should not test your own work.

---

## 🧠 Exam Priorities Recap  

Recognize and apply quickly:

- Assessment vs testing vs audit  
- Design vs operating effectiveness  
- SOC 2 Type 2 purpose  
- Vulnerability scan vs penetration test  
- Black-box vs white-box vs gray-box  
- Negative vs interface vs fuzz testing  
- Log review importance  
- Metrics (MTTD, MTTR)  
- Continuous monitoring concept  
- Authorization before testing  

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)
- Tool-specific command syntax  
- Vendor scan score calculations  
- Deep exploit development  
- Full red team playbooks  
- Regulatory audit checklists  
- Custom SIEM rule writing  
- Advanced threat hunting  

---

## 🔗 Useful Links / Mind Map  
[CISSP Domain 6 Destination Certification](https://youtu.be/A-aNmhB_WjM)
