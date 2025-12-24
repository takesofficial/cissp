# <p align=center>Domain 8 - Software Development Security</p>

## 🚨 Elevator Pitch  
Build security in from the start, not after the breach.  
Domain 8 is about **secure software lifecycle**, **secure coding**, **testing**, and **controlling change** so applications do not become your biggest attack surface.

Think: **design secure, build carefully, test aggressively, deploy safely, maintain forever.**

---

## 🧠 SDLC Mindset  

Security is cheapest **before code is written** and most expensive **after production**.

This domain focuses on:
- Preventing vulnerabilities
- Reducing attack surface
- Catching flaws early
- Managing change safely

---

## 🔁 Software Development Life Cycle (SDLC)  

Security applies to **every phase**.

### Common Phases  
1. **Requirements**  
2. **Design**  
3. **Development**  
4. **Testing**  
5. **Deployment**  
6. **Maintenance**  
7. **Disposal**

Security must exist in all phases.

---

## 🧩 Secure SDLC Models  

You do not need diagrams. Just recognize intent.

- **Waterfall** - Sequential, rigid, security added early only.  
- **Agile** - Iterative, continuous feedback, security integrated per sprint.  
- **DevOps / DevSecOps** - Security embedded into CI/CD pipelines.  
- **Spiral** - Risk-driven iterations.  
- **RAD** - Rapid prototyping, higher risk if controls are weak.

Exam mindset:  
**DevSecOps = security as code + automation + continuous testing.**

---

## 🧱 Security Requirements  

Security must be defined as a requirement, not an afterthought.

Examples:
- Authentication and authorization rules  
- Logging and auditing  
- Encryption requirements  
- Input validation  
- Error handling  

If it is not written down, it will be skipped.

---

## 🧠 Threat Modeling  

Identify threats **before** coding.

### Common Models  
- **STRIDE** - Spoofing, Tampering, Repudiation, Information disclosure, DoS, Elevation of privilege  
- **PASTA** - Risk-based, business-focused  
- **Attack surface analysis** - Reduce exposed entry points  

Threat modeling answers:
- What can go wrong?
- How?
- What is the impact?
- How do we prevent it?

---

## 🧪 Secure Coding Concepts  

You do NOT need to write code.  
You need to recognize **bad patterns**.

### Common Vulnerabilities  
- Buffer overflows  
- Injection (SQL, command, LDAP)  
- Cross-site scripting (XSS)  
- Cross-site request forgery (CSRF)  
- Insecure deserialization  
- Race conditions  
- Improper error handling  

Exam rule:  
**Never trust user input. Ever.**

---

## 🔐 Input Validation and Output Encoding  

Primary defense against injection attacks.

- Validate input length, type, range  
- Reject unexpected input  
- Encode output for its destination  

Input validation prevents exploitation.  
Output encoding prevents execution.

---

## 🧬 Memory and Resource Management  

Poor memory handling = critical vulnerabilities.

- Buffer overflows  
- Memory leaks  
- Dangling pointers  
- Race conditions  

Managed languages reduce risk but do not eliminate it.

---

## 🔑 Authentication and Authorization in Code  

Security failures often live here.

- Hardcoded credentials = instant fail  
- Strong authentication required  
- Authorization must be checked server-side  
- Least privilege applies to applications too  

Never rely on client-side enforcement.

---

## 🔐 Cryptography in Applications  

Use crypto correctly or not at all.

Key principles:
- Use proven algorithms and libraries  
- Never roll your own crypto  
- Protect keys, not just data  
- Separate encryption from access control  

Crypto mistakes are silent but catastrophic.

---

## 🧪 Software Testing  

Security testing catches flaws before attackers do.

### Testing Types  
- **Unit testing** - individual components  
- **Integration testing** - components together  
- **System testing** - full application  
- **Acceptance testing** - business requirements  

---

### Security Testing Methods  

- **Static analysis (SAST)**  
  - Source code review  
  - Finds flaws early  

- **Dynamic analysis (DAST)**  
  - Tests running application  
  - Finds runtime issues  

- **Interactive testing (IAST)**  
  - Combines static and dynamic  

- **Fuzzing**  
  - Random or malformed input  
  - Exposes crashes and logic errors  

---

## 🔍 Code Review  

Manual review finds logic flaws tools miss.

Focus on:
- Authentication logic  
- Authorization checks  
- Error handling  
- Input validation  
- Logging  

Peer review reduces risk.

---

## 📦 Third-Party Code and Libraries  

Most apps are built from reused code.

Risks:
- Vulnerable dependencies  
- Abandoned projects  
- License violations  

Controls:
- Software composition analysis (SCA)  
- Dependency scanning  
- Approved library lists  

You inherit vulnerabilities you import.

---

## 🔄 Configuration and Change Control  

Applications change constantly.

Controls:
- Version control  
- Change approval  
- Rollback capability  
- Secure defaults  

Uncontrolled change = new vulnerabilities.

---

## 🚀 Deployment and Release Management  

Secure deployment matters as much as secure code.

Key points:
- Harden environments  
- Separate dev, test, prod  
- Secure secrets (no plaintext config files)  
- Validate builds  

Production should never be a test environment.

---

## 🧯 Patch and Maintenance  

Security does not end at release.

- Monitor vulnerabilities  
- Patch dependencies  
- Retest after changes  
- Decommission safely  

Unmaintained software becomes dangerous quickly.

---

## 🗑️ Disposal  

End-of-life code must be handled safely.

- Remove access  
- Archive securely  
- Destroy sensitive data  
- Revoke credentials and keys  

Forgotten systems become backdoors.

---

## 🧠 Exam Priorities Recap  

Recognize and apply quickly:

- SDLC phases and where security fits  
- Secure SDLC vs traditional SDLC  
- Threat modeling purpose and STRIDE  
- Common coding vulnerabilities by name  
- Input validation vs output encoding  
- Static vs dynamic testing  
- Dependency and third-party risk  
- DevSecOps principles  
- Change and release control importance  
- Never trust user input  
- Never roll your own crypto  

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)

- Language-specific syntax  
- Full OWASP Top 10 explanations  
- Secure coding standards per language  
- Detailed CI/CD tooling examples  
- Container security internals  
- Advanced fuzzing frameworks  
- Secure compiler flags and build pipelines  
- Software license legal analysis  

---
## 🔗 Useful Links / Mind Map  
[CISSP Domain 8 Destination Certification](https://youtu.be/t-CXqjxJn_I)
