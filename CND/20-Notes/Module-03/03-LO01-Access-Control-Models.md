---
type: note
module: "03"
lo: "01"
tags: [concept, mod/03]
topic: "Access Control — Principles, Models, and Implementation"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-03]]

# Access Control (§3.1)

## Definition
- **Selective restriction of access** to an asset / system / network resource; determines who can access what → protects information assets
- Access control function uses **identification, authentication, authorization** to restrict/grant access
- Crucially maintains **integrity, confidentiality, availability** of information

**Mechanism steps:**
1. User provides credentials/identification while logging in
2. System validates user against database (password, fingerprint…)
3. On successful identification, system provides access to the system
4. System allows only those operations/resources the user is authorized for

## Terminologies
| Term | Meaning |
|---|---|
| **Subject** | User or process attempting to access an object |
| **Object** | Specific resource the user wants to access (file, hardware device) |
| **Reference Monitor** | Checks access-control rules for specific restrictions; implements rules on subject-object actions |
| **Operation** | Action performed by a subject on an object (e.g., deleting a file) |

## Principles
| Principle | Rule |
|---|---|
| **Separation of Duties (SoD)** | Break authorization into steps; different privileges per step; no single individual authorizes all functions or owns all objects; reduces collusion-driven breaches (GDPR emphasizes roles/duties on the security team) |
| **Need-to-know** | Access only to information required for a specific task |
| **Principle of Least Privilege (POLP)** | Extends need-to-know; "not more, not less" based on roles & responsibilities; two underlying principles: **low rights, low risks**; better stability + security |

## Access control models
Access control models specify **how a subject can access an object**.

| Model | Control | Details | Example |
|---|---|---|---|
| **MAC** | Admin/system owner only assigns privileges; end user cannot decide who accesses info | High security (defenders set controls), fewer errors, OS labels incoming data (external app control policy). Data marked highly confidential | SELinux, Trusted Solaris |
| **DAC** | Owner (possessor) of object decides subject access — a reconfigure: **need-to-know access model** | Based on file/data ownership + access rights/permissions; owner may transfer ownership; ACLs identify & authorize users; drawback: ACL maintenance | UNIX, Linux, Windows access control |
| **RBAC** | Permissions per **user roles**; system-defined policies, beyond user control | Three rules: **role assignment**, **role authorization**, **transaction authorization** | JEA, Windows Admin Center |
| **ABAC** | Access based on **attributes** of user, resource, environment (**fine-grained**) | Attributes from IAM/ERP/CRM; elastic policy-based approach; fast onboarding; regulatory compliance; scalable | XACML, Keycloak, Axiomatics |

## ABAC attributes & benefits
- **Subject/User** attrs (username, job title, email) · **Object/Resource** attrs (classification/sensitivity metadata) · **Environmental/Context** attrs (time, location) · **Action** attrs (CRUD, specifics of requested action)
- Benefits: broad range of policies · easy to use · fast onboarding · flexibility · regulatory compliance · scalability

## MAC examples
### Bell-LaPadula Model (BLP) — **confidentiality**
- Prevents access above security level; static labels; **no read-up, no write-down**; integrates aspects of DAC + MAC; uses access matrix; layered classification (subjects) + categorization (objects)
  - **Simple security property — no read-up**: subject may not read object at higher level
  - **\*-property — no write-down**: subject may not write to object at lower level
- **Trusted subjects** enable transfer from high-sensitivity to lower-sensitivity document
- Limitations: only addresses confidentiality + write control + \*-property + DAC · covert channels not comprehensively addressed · tranquility principle limitation

### Biba Integrity Model (Kenneth J. Biba, 1975) — **integrity**
- Exact **opposite of BLP**: **read-up, write-down**; users create content ≤ own integrity level, view content ≥ own level
- Three integrity axioms:
  1. **Simple integrity — no read-down**
  2. **\*-integrity — no write-up**
  3. **Invocation axiom** — subject cannot invoke a subject at a higher level
- Access modes: **Modify** · **Observe** · **Invoke** · **Execute**
- Mandatory policies: **Strict integrity** (no write-up/no read-down) · **Low-watermark for subjects** (read-down allowed) · **Low-watermark for objects** (write-up allowed); discretionary policies: ACLs + object hierarchy

## DAC example: Access Control Matrix
- **Two-dimensional array**: rows = subjects (access profile), columns = objects (**ACL**); each cell = access mode (read/write/own) the subject may exercise on the object

## Logical implementation
| Model | Implementation |
|---|---|
| DAC | **Windows File Permissions** (per-group/user ACL-based folder/file access; owner can transfer) |
| MAC | **Windows UAC** (restricts app installs to admin authorization) |
| RBAC | **JEA — Just Enough Administration** (fine-grained rights in remote PowerShell; non-admins run specific commands) · **WAC — Windows Admin Center** (roles for server management: Administrators / Hyper-V-Administrators / Readers) |
| ABAC | **XACML** framework · **Keycloak** (fine-grained authz policies, centralized PDP, REST-based) · **Axiomatics Policy Server** (XACML 2.0/3.0, externalized authorization, zero-trust) |

## XACML components (ABAC framework)
| Point | Role |
|---|---|
| **PDP** — Policy Decision Point | Evaluates incoming requests against policies |
| **PEP** — Policy Enforcement Point | Inspects user's request, generates authorization request, sends to PDP |
| **PAP** — Policy Administration Point | UI for creating/managing/testing/debugging policies; stores in repository |
| **PIP** — Policy Information Point | Retrieves data needed for policy evaluation / PDP decisions |

## Cards
Q:: Access control terminologies?
A:: Subject = user/process accessing; Object = resource (file/device); Reference Monitor checks rules; Operation = action on object.
#flashcard

Q:: Bell-LaPadula two properties?
A:: Simple security = no read-up; *-property = no write-down (confidentiality).
#flashcard

Q:: Biba three axioms?
A:: Simple integrity = no read-down; *-integrity = no write-up; invocation = no invoking higher-level subject (integrity).
#flashcard

Q:: RBAC rules?
A:: Role assignment · role authorization · transaction authorization.
#flashcard

Q:: XACML roles?
A:: PDP (decision) · PEP (enforcement/inspect) · PAP (admin) · PIP (information).
#flashcard

Q:: ABAC attribute types?
A:: Subject/user · object/resource · environmental/context · action.
#flashcard