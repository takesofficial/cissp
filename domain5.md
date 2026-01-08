# <p align=center>Domain 5 - Identity and Access Management (IAM)</p>

## 🚨 Elevator Pitch  
Make sure the **right subject** gets the **right access** to the **right object** at the **right time**, for the **right reason**, and that every action is **accountable**.  
Domain 5 is about identity lifecycle, authentication, authorization, access models, and preventing both abuse and accidents.

Think: who you are, how you prove it, what you’re allowed to do, and how it’s monitored.

---

## 🧠 IAM Mindset  

Always separate **identity**, **authentication**, and **authorization**.

- Identity answers **who**  
- Authentication answers **prove it**  
- Authorization answers **what you can do**  
- Accountability answers **what you did**

IAM failures usually cause **data breaches**, not outages.

---

## 🔐 AAA (+ Auditing)

The IAM lifecycle.

- **Identification** - Claiming an identity (username, ID)
- **Authentication** - Proving identity
- **Authorization** - Permissions granted
- **Accountability** - Actions tied to identity
- **Auditing** - Logs reviewed and retained

Exam trap: authentication ≠ authorization.

---

## 🧾 Identity Lifecycle  

Access must change as people and systems change.

1. **Provisioning** - Create identity and grant access  
2. **Review** - Validate access periodically  
3. **Modification** - Role or responsibility change  
4. **Deprovisioning** - Remove access immediately  

Key exam phrase: **joiner / mover / leaver**.

---

## 👥 Subjects and Objects  

- **Subject** - Active entity (user, process, service, device)  
- **Object** - Passive resource (file, database, system)  

Access control always mediates **subject → object**.

---

## 🪪 Authentication Factors  

Authentication is based on **factors**, not methods.

- **Something you know** - Password, PIN  
- **Something you have** - Token, smart card  
- **Something you are** - Biometrics  
- **Something you do** - Behavior (keystrokes)  
- **Somewhere you are** - Location  

### MFA  
- Uses **two or more different factors**  
- Two passwords ≠ MFA  

---

## 🧬 Authentication Methods  

- **Passwords** - Weak alone, still common  
- **Tokens** - Hardware or software  
- **Smart cards** - Certificate-based auth  
- **Biometrics** - Fingerprint, iris, face  
- **Certificates** - Strong identity binding  

Biometrics trade-off:
- Cannot be revoked  
- False acceptance vs false rejection  

---

## 🧠 Biometrics Metrics (exam favorites)

- **FAR** - False Acceptance Rate (security risk)  
- **FRR** - False Rejection Rate (usability issue)  
- **CER** - Crossover Error Rate (equal FAR/FRR)  
- **Enrollment** - Initial biometric capture  

Security prefers **low FAR**, users prefer **low FRR**.

---

## 🧱 Access Control Models  

### Mandatory Access Control (MAC)
- System-enforced  
- Labels and clearances  
- No user discretion  
- Government environments  

### Discretionary Access Control (DAC)
- Owner controls access  
- Flexible, weak  
- Common in filesystems  

### Role-Based Access Control (RBAC)
- Permissions tied to roles  
- Scales well  
- Best answer for enterprises  

### Rule-Based Access Control
- Decisions based on rules  
- Often used in firewalls  

### Attribute-Based Access Control (ABAC)
- Uses attributes (user, resource, environment)  
- Very flexible, complex  
- Common in zero trust architectures  

---

## 🧭 Least Privilege and Need-to-Know  

- **Least privilege** - minimum access required  
- **Need-to-know** - access only if required for task  

Applies to:
- Users  
- Admins  
- Services  
- Applications  

Over-privileged accounts = exam red flag.

---

## 🔑 Privileged Access  

### Privileged Accounts
- Admins, root, service accounts  
- High risk, high impact  

### Controls
- Separate admin accounts  
- MFA everywhere  
- Just-in-time access  
- Session logging  
- Password vaults  

---

## 🧰 PAM vs PIM vs IAM (exam clarity)

- **IAM** - Manages *who exists* and *what access they normally have*  
- **PAM** - Manages *high-risk privileged accounts and sessions*  
- **PIM** - Manages *temporary elevation* of privileges  

Exam rule:
- **Standing admin access = wrong**
- **Temporary, audited elevation = correct**

---

## 🔄 Federation and SSO  

### Federation
- Trust relationship between organizations  
- One identity, multiple domains  

### Single Sign-On (SSO)
- Authenticate once, access many systems  

SSO increases convenience, **not security by itself**.

---

## 🧠 Federation Trust Models (!!)
**Authentication always occurs at the IdP; authorization always occurs at the SP.**

### Centralized Identity
- One directory  
- One authority  
- Simple, internal  

### Federated Identity
- Multiple organizations  
- Trust relationship between IdP and SP  
- Authentication happens at the **IdP**

### Proxied Federation
- Broker sits between IdP and SP  
- Translates protocols  
- Adds abstraction and risk  

---

## 🧩 Federation Roles

- **IdP (Identity Provider)**  
  - Authenticates the user  
  - Issues assertions or tokens  

- **SP (Service Provider / Relying Party)**  
  - Consumes identity assertions  
  - Grants access  

Exam trap: **SP does NOT authenticate users.**

---

## 📡 Federation Protocols (recognize purpose)

- **SAML** - Enterprise SSO, XML, assertions  
- **OAuth** - Authorization delegation  
- **OpenID Connect** - Authentication on top of OAuth  

---

## 🧪 Account Types  

- **User accounts**  
- **Service accounts**  
- **Shared accounts** (avoid)  
- **Guest accounts**  
- **Emergency / break-glass accounts**  

Break-glass:
- Rare use  
- Strong controls  
- Logged and reviewed  
- Documented  

---

## 🧾 Access Reviews and Auditing  

- Periodic access reviews  
- Owner approval  
- Logging and monitoring  
- Separation of duties enforced  

Auditors never accept risk.

---

## 🧠 Identity Proofing  

Before issuing credentials:
- Verify identity  
- Match assurance level to risk  

Higher risk = stronger proofing.

---

## ⚠️ IAM Threats  

- Credential stuffing  
- Password reuse  
- Privilege creep  
- Orphaned accounts  
- Insecure APIs  
- Over-permissive roles  

Most breaches start with IAM failure.

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
