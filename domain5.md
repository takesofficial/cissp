# <p align=center>Domain 5 - Identity and Access Management (IAM)</p>

## 🚨 Elevator Pitch  
Make sure the **right subject** gets the **right access** to the **right object** at the **right time**, for the **right reason**, and that every action is **accountable**.  Domain 5 is about identity lifecycle, authentication, authorization, access models, and preventing both abuse and accidents.

Think: who you are, how you prove it, what you're allowed to do, and how it's monitored.

---

## 🧠 Identity and Access Management (IAM)

IAM failures typically result in confidentiality breaches (unauthorized access), not availability outages.
IAM separates identity, authentication, authorization, and accountability to control and trace access to resources.

| Component | Core Question | Purpose | Example |
|------------|--------------|----------|----------|
| 🪪 **Identification** | Who are you? | Subject claims an identity | Username / User ID |
| 🔐 **Authentication** | Can you prove it? | Verifies the claimed identity | Password, MFA, certificate |
| 🚪 **Authorization** | What are you allowed to do? | Grants or denies access to resources | Read-only access to database |
| 🧾 **Accountability** | What did you do? | Links actions to an identity | User ID tied to activity |
| 📋 **Auditing** | What happened? | Records and reviews events | Logs, SIEM reports |

---

## 🧾 Accountability and Non-repudiation Enablers

Accountability is a system property, not a user promise.

| Control | What It Achieves | Why |
|---------|-------------------|-----------------|
| Unique IDs (no shared accounts) | Trace actions to a person | Shared accounts break accountability |
| Strong authentication | Raises confidence in identity | Prevents "it wasn't me" claims |
| Time sync (NTP) | Correct event timelines | Logs without time are weak evidence |
| Central logging | Single source for auditing | Easier detection and investigations |
| Tamper resistance | Log integrity | Evidence must be reliable |

---

## 🧾 Identity Lifecycle  

Access must change as people and systems change.

1. 🆕 **Provisioning** - Create identity and grant access  
2. 🔍 **Review** - Validate access periodically  
3. 🔄 **Modification** - Role or responsibility change  
4. 🗑️ **Deprovisioning** - Remove access immediately

Key exam phrase: **🆕joiner** / **🔄 mover** / **🗑️ leaver**.

---

## 🏢 Access Control Administration

How access decisions are managed.

| Model | Where Decisions Live | Strengths | Risks | Exam Angle |
|------|-----------------------|----------|------|-----------|
| Centralized | One IAM authority (directory/IdP) | Consistent policy, easier auditing | Single high-value target | Preferred for enterprise governance |
| Decentralized | Each system manages its own users | less dependency | Inconsistent access, weak offboarding | Common in legacy, higher risk |
| Hybrid | Central identity, local app roles | Practical mix | Complexity | Most real environments |

Centralized improves control and auditability, decentralized increases orphaned accounts and privilege creep.

---

## 👥 Subjects and Objects  

- **Subject** - Active entity (user, process, service, device)  
- **Object** - Passive resource (file, database, system)  

Access control always mediates **subject > object**.

---

## 🪪 Authentication Factors  

Authentication is based on **factors**, not methods.

- 🧠 **Something you know** - Password, PIN  
- 📟 **Something you have** - Token, smart card  
- 👁️ **Something you are** - Biometrics  
- ⌨️ **Something you do** - Behavior (keystrokes)  
- 📍 **Somewhere you are** - Location

### 🔐 MFA  
- Uses **two or more different factor types**  (🔑 + 📟) or (📟 + 👁️) etc.  

---

## 🧬 Authentication Methods  

- 🔑 **Passwords** - Weak alone, still common  
- 📟 **Tokens** - Hardware or software  
- 💳 **Smart cards** - Certificate-based auth  
- 👁️ **Biometrics** - Fingerprint, iris, face  
- 🛡️ **Certificates** - Strong identity binding

Biometrics trade-off:
- Cannot be revoked  
- False acceptance vs false rejection  

---

## 🎟️ Kerberos (Ticket-Based Authentication)

Centralized authentication used in Active Directory. Uses tickets instead of sending passwords. 
Kerberos = centralized, ticket-based authentication using symmetric crypto and time sync.  
Golden ticket owns the domain.  
Silver ticket owns one service.

| Area | Key Point | Hook |
|------|----------|-----------|
| Purpose | Centralized authentication | No passwords on wire |
| Port | 88 TCP/UDP | Know the port |
| Crypto | Symmetric | Not PKI |
| Time | Requires NTP | Time drift breaks login |
| Mutual Auth | Yes | Client + server verify |

### Core Flow

| Step | Action |
|------|--------|
| 1 | Client authenticates to AS |
| 2 | Receives TGT |
| 3 | TGT presented to TGS |
| 4 | Service ticket issued |
| 5 | Access resource |

Authorization happens at the service, not Kerberos.

---

### Core Components

| Component | Role |
|----------|------|
| Client | Requests access |
| KDC | Authentication authority |
| AS | Issues TGT |
| TGS | Issues service tickets |
| Service | Target resource |

---

### What Kerberos Provides

| Property | Yes / No |
|----------|----------|
| Authentication | Yes |
| Authorization | No |
| Confidentiality | Yes |
| Integrity | Yes |
| Non-repudiation | No |

---

### Attacks You MUST Know

| Attack | Meaning | Impact |
|------|--------|--------|
| Golden Ticket | Fake TGT | Full domain compromise |
| Silver Ticket | Fake service ticket | Single service compromise |

Golden = domain  
Silver = service

---

### Core Defenses

| Control | Why |
|--------|-----|
| MFA for admins | Stops credential abuse |
| Rotate KRBTGT | Kills golden tickets |
| Short ticket lifetime | Limits replay |
| NTP hardening | Prevents auth failure |

---

## 🧠 Biometrics Metrics (exam favorites)

- 🚨 **FAR** - False Acceptance Rate (security risk)  
- 😤 **FRR** - False Rejection Rate (usability issue)  
- ⚖️ **CER** - Crossover Error Rate (equal FAR/FRR)  
- 🪪 **Enrollment** - Initial biometric capture  

Security prefers 🚨 **low FAR**, users prefer 😤 **low FRR**.

---

## 🧱 Access Control Models  

### 🪖 Mandatory Access Control (MAC)
Central authority decides. Users have zero control.
- System-enforced  
- Labels and clearances  
- No user discretion  
- Government environments  

### 📜 Discretionary Access Control (DAC)
Ownership-based = higher risk of privilege sprawl.
- Owner controls access  
- Flexible, weak  
- Common in filesystems  

### 🥸 Role-Based Access Control (RBAC)
Default enterprise model. Best answer for manageability.
- Permissions tied to roles  
- Scales well  
- Best answer for enterprises  

### 📐 Rule-Based Access Control
Environment-driven logic (IP, time, protocol), not identity.
- Decisions based on rules  
- Often used in firewalls  

### 🤹 Attribute-Based Access Control (ABAC)
Policy = attributes, not roles.
- Uses multiple attributes (user, resource, environment, action)  
- Extremely flexible, more complex to manage  
- Common in zero trust architectures  

---

### 🎲 Risk-Adaptive Access Control (Context-Aware)
Access decisions change dynamically based on real-time risk signals.
Dynamic ABAC with risk scoring. Also called *adaptive* or *context-aware* access.

| Input | Example |
|------|---------|
| User context | Impossible travel, unusual location |
| Device posture | Unmanaged device, missing patches |
| Behavior | Abnormal login time or access pattern |
| Data sensitivity | Sensitive data triggers step-up auth |

---

## 🧩 Authorization Vocabulary

Questions often describe "entitlements" without using the word. Think effective access, not intended access.

| Term | Meaning | Example |
|------|---------|---------|
| Permission | Allowed action on an object | Read file X |
| Privilege | Special high-impact permission | Reset passwords |
| Entitlement | Effective access a subject ends up with | Group memberships + app roles combined |
| Right | Often used like permission, sometimes legal/contractual | Right to access HR system |
| Role | Bundle of permissions | "Finance Analyst" |
| Group | Collection of subjects | "IT-Admins" |

---

## 🧭 Least Privilege and Need-to-Know  

- 🎯 **Least privilege** - minimum permissions required  
- 🧠 **Need-to-know** - access only when required for the task  

Applies to:
- 👤 Users  
- 🛠️ Admins  
- ⚙️ Services  
- 🖥️ Applications  

🚨 Over-privileged accounts = red flag

---

## 🧱 Access Control Implementation Types

Controls are layered. Monitoring is not access control by itself, it is detective.

| Type | What It Is | IAM Example | Angle |
|------|------------|-------------|-----------|
| Preventive | Stops unauthorized access | MFA, RBAC, NAC | Best answer when asked "prevent" |
| Detective | Finds misuse after or during | Auth logs, SIEM alerts, UEBA | Best answer when asked "detect" |
| Corrective | Fixes after detection | Disable account, rotate creds | Response action, not prevention |
| Deterrent | Discourages attempts | Login banner, monitoring notice | Weak alone |
| Compensating | Alternative when primary control isn't possible | Jump host + monitoring for legacy | Common exam scenario |

---

## 🔑 Privileged Access  

### 🛠️ Privileged Accounts
- 🤴 Admins, root, service accounts  
- ⚠️ High risk, high impact  

### 🛡️ Core Controls
- 🪪 Separate admin accounts (no shared identities)  
- 🔐 MFA everywhere  
- ⏱️ Just-in-time access (PIM)  
- 📹 Session logging / recording  
- 🗄️ Password vaults / credential rotation

---

## 🧰 PAM vs PIM vs IAM (exam clarity)

- 🪪 **IAM** - Manages *who exists* and *baseline access*  
- 🛡️ **PAM** - Secures *high-risk privileged accounts and sessions*  
- ⏱️ **PIM** - Grants *temporary, just-in-time privilege elevation*  

Exam rule:
- 🚫 **Standing admin access = wrong**  
- ✅ **Temporary, audited elevation = correct**
---

## 🔄 Federation and SSO  

### 🤝 Federation
- Trust relationship between organizations  
- One identity across multiple domains  
- Authentication handled by the IdP  

### 🔑 Single Sign-On (SSO)
- Authenticate once  
- Access many systems without re-auth  

Exam reality:
- ✅ Federation = trust + identity sharing  
- ⚠️ SSO = convenience only  
- 🔐 SSO does **not** increase security by itself (it just centralizes authentication)

---

## 🧠 Federation Trust Models (!!)
- 🔐 **Authentication** always happens at the **IdP**.  
- 🚪 **Authorization** always happens at the **SP**.

### 🏢 Centralized Identity
- 📁 One directory  
- 🏛️ One authority  
- 👤 Internal users only  
- 🧱 Lowest complexity, smallest attack surface  

### 🤝 Federated Identity
- 🏢🏢 Multiple organizations  
- 🔐 Explicit trust between 🪪 IdP and 🖥️ SP  
- 🪪 Authentication at IdP  
- 🚪 Authorization at SP  
- 🌐 Identity shared across domains  

### 🧩 Proxied Federation
- 🧩 Broker sits between 🪪 IdP and 🖥️ SP  
- 🔄 Translates protocols (SAML ↔ OIDC, etc.)  
- 🕶️ Hides internal identities  
- ⚠️ Adds latency ⏳, abstraction 🧠, and attack surface 🎯
---

## 🎭 Federation Roles

- 🪪 **IdP (Identity Provider)**  
  - Authenticates the user  
  - Issues assertions or tokens  

- 🖥️ **SP (Service Provider / Relying Party)**  - does NOT authenticate users.  
  - Consumes identity assertions  
  - Grants access  

---

## 📡 Federation Protocols (recognize purpose)

- 🏢 **SAML** - Enterprise SSO 🔑, XML 📄, identity assertions 🪪  
- 🔐 **OAuth** - Authorization delegation 🚪 (access tokens 🎟️, not identity)  
- 🪪 **OpenID Connect** - Authentication 🔐 built on top of OAuth ⚙️

---

## 🧪 Account Types  

- 👤 **User accounts**  
- ⚙️ **Service accounts**  
- ⚠️ **Shared accounts** (avoid)  
- 🚪 **Guest accounts**  
- 🧯 **Emergency / break-glass accounts**

## 🧯 Break-glass Accounts
- ⛔ Rare use (emergencies only)  
- 🔐 Strong controls (MFA, vaulting)  
- 📋 Fully logged and 👀 reviewed  
- 📝 Clearly documented (ownership + procedure)
---

## 🧾 Access Reviews and Auditing  

🧑‍⚖️ Auditors never accept risk  

- 🔁 Periodic access reviews  
- ✍️ Owner approval  
- 📋 Logging and 👀 monitoring  
- 🧭 Separation of duties enforced  

---

## 🧑‍🤝‍🧑 Separation of Duties, Dual Control, Split Knowledge

SoD is about process design, not technical features.

| Concept | What It Prevents | Example | Angle |
|--------|-------------------|---------|-----------|
| Separation of Duties (SoD) | One person completing fraud alone | Requester cannot approve own access | Governance control |
| Dual Control | Single-person abuse of critical actions | Two admins approve key export | Strong for high-impact actions |
| Split Knowledge | One person knowing all secrets | Key parts held by different people | Common with HSM and vaults |

---

## 🧠 Identity Proofing  
⚠️ Higher risk = stronger proofing.

Before issuing credentials 🔑:
- 🪪 Verify real-world identity (documents, in-person, trusted sources)  
- 📊 Match assurance level to risk  
- 🧱 Prove this human = this account

---

## 🎚️ Identity Assurance (NIST 800-63 concept)

Higher risk system needs higher assurance. Proofing (IAL) and login strength (AAL) are different levers.

| Assurance Area | What It Measures | Meaning |
|----------------|------------------|---------------|
| IAL | How well the person was identity-proofed | Strength of onboarding proof |
| AAL | Strength of authentication | MFA strength and binding |
| FAL | Strength of federation assertion | Token/assertion protection between IdP and SP |

---

## ⚠️ IAM Threats  

Most breaches start with IAM failure.

- 🧪 **Credential stuffing**  
- 🔁 **Password reuse**  
- 📈 **Privilege creep**  
- 👻 **Orphaned accounts**  
- 🔓 **Insecure APIs**  
- 🚨 **Over-permissive roles**

---

## 🧨 IAM Attack Patterns and Fast Defenses

MFA is the default best control for credential-based attacks.

| Attack | What It Exploits | Best Countermeasures |
|--------|-------------------|----------------------|
| Password spraying | Weak shared password habits | MFA, lockout tuning, smart detection |
| Credential stuffing | Reuse from breaches | MFA, breached-password checks |
| Session hijacking | Stolen session token | TLS, secure cookies, short sessions, re-auth |
| Pass-the-hash / pass-the-ticket | Credential artifacts | Credential Guard, hardening, monitor auth anomalies |
| Privilege escalation | Over-permissioned roles | Least privilege, PAM/PIM, SoD |
| Orphaned accounts | Bad offboarding | Joiner/mover/leaver automation, reviews |

---
## 🔗 Useful Links / Mind Map  
[CISSP Domain 5 Destination Certification](https://www.youtube.com/watch?v=WBlQQ6qTlGI)
