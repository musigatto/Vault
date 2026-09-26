---
type: note
module: "02"
lo: "03"
tags: [policy, mod/02]
topic: "Security Policy — Design & Development Fundamentals"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-02]]

# Security Policy Fundamentals (§2.3) — part a

## Definition
- Well-documented set of **plans, processes, procedures, standards, guidelines** to establish ideal information security status
- Integral part of an information security management program
- Informs safe/secure work; defines & guides employee actions on sensitive operations, data, resources
- High-level document(s) describing security controls to implement; maintains **confidentiality, availability, integrity, asset values**

## Three goals
1. Reduce/eliminate **legal liability** to employees & third parties
2. Protect **confidential & proprietary information** from theft, misuse, unauthorized disclosure/modification
3. **Prevent computing resource waste**

## Need for a security policy
- Consistent application of security principles · legal protection · quick incident response · standards compliance · reduced incident impact · limit exposure to external threats · minimize data-breach risk · enhance data/network security · senior management commitment · trust-based client relationships

## Advantages
- Enhanced data & network security
- Risk mitigation
- Monitored/controlled device usage & data transfers
- Better network performance
- Quick response + lower downtime
- Reduction in management stress
- Reduced costs

## Characteristics of a good policy
Concise & Clear · Usable · Economically Feasible · Understandable · Realistic · Consistent · Procedurally Tolerable · **Compliant with cyber/legal laws, standards, rules, regulations**

## Key elements
- **Clear communication**
- **Brief & clear information**
- **Defined scope & applicability** (what is covered/hidden/protected/public)
- **Enforceable by law** (penalties for breach; decided at creation)
- **Recognizes areas of responsibility** (employees, org, third parties)
- **Sufficient guidance** (references to other policies)

## Contents of a security policy
| Block | Content |
|---|---|
| High-level security requirements | Discipline, safeguard, procedural, **assurance** security |
| Policy description | Security disciplines, safeguards, procedures, continuity of operations, documentation |
| Security concept of operation | Roles, responsibilities, functions; mission, communications, encryption, user/maintenance rules, idle-time, public vs private domain, shareware rules, virus protection |
| Allocation of security enforcement | Computer system architecture allocation per system in the program |

**Security requirement types:**
- **Discipline** — computer, operations, network, personnel, physical security
- **Safeguard** — access control, malware protection, audit, availability, confidentiality, integrity, cryptography, identification, authentication
- **Procedural** — access policies, accountability, continuity of operations, documentation
- **Assurance** — compliance with standards, certifications, accreditations

## Typical policy document content
Overview · Document Control · Policy Statements · Document Location · Purpose · Sanctions & Violations · Related Standards/Policies/Processes · Revision History · Scope · Approvals · Definitions · Contact Info · Distribution · Roles & Responsibilities · Where to Find More Info · Document History · Target Audience · Glossary/Acronyms

> [!tip] Document content checklist
> Overview (background) · Purpose (why) · Scope (who/what) · Definitions (terms) · Roles & Responsibilities · Target Audience · Policies (statements) · Sanctions & Violations (allow/deny) · Contact Information · Version number (change tracking) · Glossary/Acronyms.

## Policy statements
- Must be written in clear, formal style; define structure of the policy; employees understand permissible preventive measures
- Ideal example: _*"All access to data will be based on a valid business need and is subject to a formal approval process."*_
- Other examples: all computers must have AV protection (real-time); all software purchased by IT per procurement policy; no abuse/defamation/stalking/harassment/therapy threats online; servers run minimum services; backup media copy off-site; data access on valid business need

## Steps to create & implement
1. **Risk assessment** — identify risks to assets; severity & criticality
2. **Standard guidelines** — learn from standard guidelines & other orgs
3. **Management input** — senior management + staff in policy development (policy without mgmt consent is illegal)
4. **Penalties** — set clear penalties; enforce them
5. **Final draft** — publish to everyone in the organization
6. **Read & sign** — every member reads, signs, understands the policy
7. **Deployment** — deploy tools to enforce policies
8. **Training** — train & educate employees (periodically; new employees always)
9. **Review & update** — regularly review; update for new technologies/breaches

> [!tip] Chain: Risk → Guidelines → Management → Penalties → Publish → Sign → Enforce → Train → Review.

## Considerations before designing
- Purpose: value-add or mere formality?
- In line with training programs?
- Complies with org objectives?
- Guideline for best practice vs based on a standard?
- Least info each employee must know to do the job?
- Are all details needed (or in System-Specific policies for IT pros)?
- Can policies be linked?
- What must staff understand from policies?

## Design points
- Description of the issue · policy status & domains applied · functions/responsibilities of employees · tasks & procedures in/not in policy · consequences of incompatibility
- Develop policies to **enforce**; explain purpose; differentiate policies vs standards vs recommendations; represent basic org goals; ensure understood; include policies in security awareness training; pre-estimate basic risks

## Types of information security policies
| Type | Role | Examples |
|---|---|---|
| **EISP** — Enterprise Information Security Policy | Drives scope & direction; ideology, purpose, methods; ensure info-security framework requirements | Encryption policy, network & network-device security policy |
| **ISSP** — Issue-Specific Security Policy | Addresses specific issues; directs audience on technology-based systems via guidelines | Acceptable-use, password, access-control, backup/restore, Internet & web usage, user-account, email, remote access & wireless policies |
| **SSSP** — System-Specific Security Policy | Directs users while configuring/maintaining a system | DMZ policy, application policy, secure cloud computing, IDS/IPS, personal devices, servers |

## Internet access policies (4 types)
| Policy | Behavior |
|---|---|
| **Promiscuous** | No restrictions on Internet/remote access; nothing blocked → malware/virus/Trojan risk |
| **Permissive** | Wide open; only known dangerous services/attacks blocked → admin always playing catch-up |
| **Paranoid** | Everything forbidden; no/severely limited Internet; users find workarounds |
| **Prudent** | All services blocked by default; network defender enables safe/necessary services individually; maximum security + everything logged |

## Cards
Q:: Three goals of a security policy?
A:: (1) Reduce/eliminate legal liability; (2) protect confidential & proprietary information; (3) prevent computing resource waste.
#flashcard

Q:: Four security requirement types?
A:: Discipline · Safeguard · Procedural · Assurance.
#flashcard

Q:: EISP vs ISSP vs SSSP?
A:: EISP=enterprise scope/direction; ISSP=issue-specific (acceptable use, password…); SSSP=system-specific (DMZ, servers, cloud).
#flashcard

Q:: Internet access policies — paranoid vs prudent?
A:: Paranoid forbids everything; Prudent blocks all by default then enables each safe/necessary service and logs everything.
#flashcard

Q:: Step 3 & 4 of policy creation?
A:: 3 = include senior management/staff (policy without mgmt consent is illegal); 4 = set clear penalties and enforce them.
#flashcard