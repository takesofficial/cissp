# <p align=center>Domain 5 - Identity and Access Management (IAM)</p>

## 🚨 Elevator Pitch  
Make sure the **right subject** gets the **right access** to the **right object** at the **right time**, for the **right reason**, and that every action is **accountable**.  Domain 5 is about identity lifecycle, authentication, authorization, access models, and preventing both abuse and accidents.

Think: who you are, how you prove it, what you're allowed to do, and how it's monitored.

---

## 🧠 IAM Mindset  

Always separate **identity**, **authentication**, and **authorization**.

- 🪪 **Identity** answers **who**  
- 🔐 **Authentication** answers **prove it**  
- 🚪 **Authorization** answers **what you can do**  
- 🧾 **Accountability** answers **what you did**

IAM failures usually cause **data breaches**, not outages.

---

## 🔐 AAA (+ Auditing)

The IAM lifecycle.

- 🪪 **Identification** - Claiming an identity (username, ID)  
- 🔐 **Authentication** - Proving identity  
- 🚪 **Authorization** - Access (permission granted)  
- 🧾 **Accountability** - Actions tied to identity  
- 📋 **Auditing** - Logs reviewed and retained  

---

## 🧾 Identity Lifecycle  

Access must change as people and systems change.

1. 🆕 **Provisioning** - Create identity and grant access  
2. 🔍 **Review** - Validate access periodically  
3. 🔄 **Modification** - Role or responsibility change  
4. 🗑️ **Deprovisioning** - Remove access immediately

Key exam phrase: **🆕joiner** / **🔄 mover** / **🗑️ leaver**.

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

## 🧠 Biometrics Metrics (exam favorites)

- 🚨 **FAR** - False Acceptance Rate (security risk)  
- 😤 **FRR** - False Rejection Rate (usability issue)  
- ⚖️ **CER** - Crossover Error Rate (equal FAR/FRR)  
- 🪪 **Enrollment** - Initial biometric capture  

Security prefers 🚨 **low FAR**, users prefer 😤 **low FRR**.

---

## 🧱 Access Control Models  

### 🪖 Mandatory Access Control (MAC)
- System-enforced  
- Labels and clearances  
- No user discretion  
- Government environments  

### 📜 Discretionary Access Control (DAC)
- Owner controls access  
- Flexible, weak  
- Common in filesystems  

### 🥸 Role-Based Access Control (RBAC)
- Permissions tied to roles  
- Scales well  
- Best answer for enterprises  

### 📐 Rule-Based Access Control
- Decisions based on rules  
- Often used in firewalls  

### 🤹 Attribute-Based Access Control (ABAC)
- Uses attributes (user, resource, environment)  
- Very flexible, complex  
- Common in zero trust architectures  

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

## 🧠 Identity Proofing  
⚠️ Higher risk = stronger proofing.

Before issuing credentials 🔑:
- 🪪 Verify real-world identity (documents, in-person, trusted sources)  
- 📊 Match assurance level to risk  
- 🧱 Prove this human = this account

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

## 🧠 Exam Priorities Recap  

Recognize and apply quickly:

- Identification vs authentication vs authorization  
- MFA factor types  
- RBAC vs DAC vs MAC vs ABAC  
- FAR vs FRR vs CER  
- Least privilege everywhere  
- Admin account separation  
- PAM vs PIM purpose  
- Federation roles (IdP vs SP)  
- Centralized vs federated vs proxied identity  
- Identity lifecycle (joiner/mover/leaver)  
- IAM as primary breach vector  

---

## 📦 What Was Intentionally Removed (Too Long / Not Test-Critical)

- Vendor-specific IAM platforms  
- OAuth token internals  
- Kerberos ticket flows  
- Password hashing algorithms  
- Biometric sensor hardware  
- Country-specific identity regulations  
- Deep zero trust framework mappings  
- API gateway implementation details  

---
## 🔗 Useful Links / Mind Map  
[CISSP Domain 5 Destination Certification](https://www.youtube.com/watch?v=WBlQQ6qTlGI)
