---
type: note
module: "03"
lo: "03"
tags: [process, mod/03]
topic: "Identity and Access Management (IAM)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-03]]

# Identity & Access Management (§3.3)

## IAM core
- Provides **the right individual with the right access at the right time**; RBAC over enterprise critical info
- Comprises business processes, policies, technologies monitoring electronic/digital identities
- 4 framework areas: **Authentication · Authorization · User Management · Central User (Identity) Repository**
- Preferred: all-in-one authentication extendable to **identity federation** — IAM + **SSO** + centralized **Active Directory** account; data correctness required for IAM to function
- **IDM (Identity Management)** manages the shared **identity repository** accessed by apps + access management system

## User Identity Management (IDM)
- **Identification** = confirm identity of user/process/device (unique user ID; most-used technique); attributes: username, account number, roles
- **Identity repository** = database storing user-identity attributes

## Access Management — Authentication
*Validates identity against system/app/network.* Factors:
- **Something you know** — username, password
- **Something you have** — OTP token, employee ID card
- **Something you are** — biometrics (retina, fingerprint…)

Common methods: Passwords · Biometrics · Token management. Wired + wireless networks authenticate users before resource access.

### Method flow
| Method | Mechanics | Notes |
|---|---|---|
| **Password** | username+password vs DB/AD | ≥8 chars mixed; vulnerable to brute force; capture plaintext via sniffing |
| **Smart card** | chip card + reader + **PIN**; stores password files, tokens, OTP, biometric templates, public/private keys | cryptography-based; stronger than password; apt for VPN/email/DL encryption, electronic signatures, wireless logon, biometrics. Pros: highly secure, easy to carry, less user deception. Cons: easily lost, identity risk if lost, high production cost; limited chip storage |
| **Biometric** | scan → digital compare vs DB → grant | techniques: fingerprint (ridges/minutia) · retinal (blood vessels) · iris · vein structure · face · voice. Pros: hard to tamper/share/steal. Cons: hard to change if compromised; retina/vein can reveal medical conditions (privacy) |
| **Two-factor (2FA)** | 2 of 3 factors | e.g., bank card + PIN; reduces identity theft & phishing; delays waiting for token issuance. Combos: password+smart card · password+biometrics · password+OTP · smart card+biometrics |
| **MFA** | ≥2 independent credentials (know/have/are) | core IAM component; layered defense; e.g., ATM card + PIN; pairs with **SSO**; sometimes = 2FA with unique marker (time/location) |
| **Token-based** | server sends unique token after verify; valid until session/logout | secure APIs; advantages: security, scalability, cross-origin sharing, revocation, **statelessness**. Steps: Request → Verify → Token → Storage |
| **Certificate-based** | public-key crypto; private key corresponds to cert public key | digital cert on user's computer; three-way handshake, VPN, email security, IoT; centralized control, scalability, key safeguarding; cert fields: name, device name, version, issuer, serial, validity, public key; then cryptographic challenges |
| **SSO** | one login → multiple apps (e.g., Google) | policy server stores creds; cookie-based; pros: fewer logins, less reauth, less phishing, centralized mgmt, lifecycle provisioning simplified. Cons: single credential loss = total loss; many vuln issues; multiuser-computer concerns |
| **Risk-based** | risk per transaction; stringency varies | considers device, location, network, sensitivity; key aspects: **risk assessment** (threat models), **risk scoring** (prioritize), **real-time adaptation**; vulnerable to social engineering — pair with other controls |
| **CRAM (challenge-driven)** | one side challenges, other answers | prevents bot attacks/fake registrations; resists replay attacks; scalable; cons: complexity, limited usability/accessibility/mobility, cost |
| **EAP** | extensible wireless auth protocol; PPP/802.1X messaging | request/response core messages; methods: **MD5, generic tokens, TLS**; used for dial-up/VPN/LAN/wireless; RADIUS/LDAP for identity verify + credential validate |
| **PAM** | authorizes root/admin security functions; restricts to necessary access | high-risk task → designated approver → privileges expire after interval → admin no longer has access; encrypted remote channels, privileged reports, integrated password security, session monitoring, **just-in-time access** |

### Privileged account types
**Privileged** (beyond non-privileged) · **Domain administrator** (all workstations in domain) · local (service) accounts (app↔OS) · **Emergency** (unprivileged → admin access in disaster) · **Business** (higher privilege per job responsibilities) · **Local admin** (specific workstations/servers; maintenance) · **Application admin** (full app access for operations)

## Authorization
- Controlling access to information for individuals (e.g., read-only vs write/delete)
| System | Behavior |
|---|---|
| **Centralized** | single central authorization unit/database for all resources; easy, inexpensive; policy decisions by central unit; easy add/edit/delete of apps |
| **Decentralized** | each resource maintains own authorization unit + database; user can grant access to others; flexible but **cascading/cyclic authorization** issues |
| **Implicit** | indirect access via primary resource (web page → linked pages); higher granularity |
| **Explicit** | separate authorization per resource request; simpler, but large storage |

## Accounting (AAA third leg)
- Track user actions on the network (files accessed, alteration/modification)
- Data used for **trend analysis, data breach detection, forensics**
- Accountability triad: **Authentication** (who are you) + **Authorization** (what rights do you have) + Accounting

## IAM tools
- Software to manage/secure identities, control access, enforce policies; centralized admin; align with security + business requirements
- **Features**: IAM systems (centralized directory service, hybrid/on-prem/cloud) · SSO solutions · MFA solutions (IP, device footprint, prior login-time checks) · user **provisioning/deprovisioning** (kills zombie accounts; auto-removal on exit) · **PAM** solutions (service/system/root/network/domain admin accounts)
- **Roles**: Authentication · Authorization · Manage user account · Audit & compliance · Password management · Single sign-on · Privileged access mgmt

### Example: SolarWinds Access Rights Manager (ARM)
- Manage + audit access rights across IT infrastructure; visual insight into who-has-what; compliance reports; role-based provisioning/deprovisioning
- Features: respond to high-risk access · reduce insider-threat risk · compliance via change tracking · fast account provisioning · delegated access-rights management

### Other tools
| Tool | Notes |
|---|---|
| **ManageEngine ADManager Plus** | Web-based AD management; bulk user create/modify; role-based security |
| **ManageEngine ADAudit Plus** | AD content/config + Azure AD + Windows servers audit; access intelligence for workstations/file servers (NetApp, EMC) |
| **NordLayer** | Adaptive internet security built on NordVPN; network-access integration |
| **IBM Security Identity & Access Assurance** | Centralized IAM: SSO, MFA, adaptive AI access, passwordless, lifecycle + consent management |
| **SailPoint IdentityIQ** | Enterprise-scale IAM: provisioning, access requests, certifications, separation of duties |
| **Ping Identity** | Cloud-hosted IAM for on-prem + cloud apps; admin access-control toolkit |

## Cards
Q:: Four IAM areas?
A:: Authentication · Authorization · User management · Central user (identity) repository.
#flashcard

Q:: Authentication factors?
A:: Something you know (password) · Something you have (token/card) · Something you are (biometrics).
#flashcard

Q:: 2FA combos?
A:: Password+smart card · password+biometrics · password+OTP · smart card+biometrics.
#flashcard

Q:: Token-based auth advantages?
A:: Security, scalability, cross-origin sharing, revocation, statelessness.
#flashcard

Q:: Centralized vs decentralized authorization?
A:: Centralized = single DB/unit for all resources (easy, cheap); decentralized = per-resource DB, flexible but cascading/cyclic auth issues.
#flashcard

Q:: Accounting purpose?
A:: Track user actions → trend analysis, breach detection, forensics (AAA: Authentication/Authorization/Accounting).
#flashcard

Q:: Provierre/deprovisioning benefit?
A:: Eradicates idle "zombie" accounts; auto-removes access on departure.
#flashcard