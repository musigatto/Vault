---
type: note
module: "02"
lo: "01"
tags: [policy, mod/02]
topic: "Obtain Regulatory Frameworks Compliance"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-02]]

# Regulatory Frameworks Compliance (§2.1)

## Definition
- Set of **guidelines + best practices** orgs follow to meet regulatory needs, enhance processes, improve security
- Prevents large fines and data breaches; most orgs comply with **>1 framework**
- Evolving nature (org environments in flux); guidelines leveraged by:
  - **Internal auditors** (assess required controls)
  - **External auditors** (assess required controls)
  - **Third parties** (customers, investors — risk review before collaborating)

## Security hierarchy (top → bottom)
| Layer | Role | Example |
|---|---|---|
| Regulatory Frameworks | Document policies, standards, procedures, practices, guidelines — each separate purpose, not combined | PCI-DSS Requirement 3: Encrypt/protect stored cardholder data |
| Policies | High-level statements; business mandate; top-down management; ≥1 per org | Email policy, encryption policy |
| Standards | **Low-level, mandatory** controls / tech implementation; enforce + support policies | Password complexity; DES, AES, RSA |
| Procedures / SOP | Step-wise instructions to implement controls | Secure Windows installation, data encryption procedure |
| Guidelines | **Non-mandatory** recommendations / best practices; interchangeable w/ "best practices"; reviewed more often than standards & policies | Password ≥8 chars + best practice of expiry |

## Policy generally outlines
- Security roles & responsibilities
- Scope of information to be secured
- Description of required controls
- References to supporting standards & guidelines

## Why organizations need compliance
- **Improved security** — regulations improve overall security; consistent data security
- **Minimized losses** — best security prevents breaches → avoid repair costs, legal fees, fines
- **Maintain trust** — compliant orgs keep customer confidence (data safe)
- **Increased control** — prevent employee mistakes, strong credentials, encryption, monitoring outside threats

## Identifying the framework to comply with
Self-assessment → find gaps between existing control environment and requirements.

| Framework | Organizations in scope |
|---|---|
| HIPAA | Healthcare data handlers: doctor's offices, insurance cos, business associates, employers |
| SOX | US public company boards, management, public accounting firms |
| FISMA (2002) | All federal agencies — method to protect information systems |
| GLBA | Cos offering loans, financial/investment advice, insurance |
| PCI-DSS | Cos handling credit card information |

Assessment inputs: financial institution letters · NIST publications · industry guidance (ISO 27002, NIST CSF) · notice cybercrimes/exploits/trends for large-scope breach.

## Deciding how to comply
1. Interpret regulatory requirements correctly
2. Analyze how requirements apply to org services
3. Resolve internal/external ambiguities; sort compliance requirements by importance/breach risk
4. **Separate/group** requirements (important + central first)
5. Establish policies, procedures, security controls to organize information security

### PCI-DSS example requirements → controls
| Regulatory requirement | Satisfying control |
|---|---|
| 1.1.1 Formal process to approve/test network connections + firewall/router changes | Provision for unauthorized network connection detection |
| 1.2.1 Restrict inbound/outbound traffic to cardholder data env; deny all other | Provision for insecure protocols/services on systems |
| 1.1.6 Document + justify all services/protocols/ports, incl. insecure | Provision for insecure protocols/services running on systems |
| 1.3.1 Implement DMZ to limit inbound traffic | Provision for checking traffic flow across DMZ |
| 1.3.2 Limit inbound Internet traffic to DMZ IPs | — |
| 1.3.5 No unauthorized outbound traffic to Internet | — |
| 5.1 Deploy anti-virus on all systems | — |
| 5.3 Anti-virus actively running; policy for disabled cases | Provision for detecting malware when protection disabled |

## Cards
Q:: Order the security hierarchy from top to bottom?
A:: Regulatory Frameworks → Policies → Standards → Procedures (SOP) → Guidelines.
#flashcard

Q:: Standards vs guidelines · mandatory?
A:: Standards = specific low-level MANDATORY controls (e.g., password complexity, DES/AES/RSA). Guidelines = non-mandatory recommendations/best practices, reviewed more often.
#flashcard

Q:: Why is compliance not optional?
A:: Investment worth more than cost of risks: improved security, minimized losses, maintained trust, increased control.
#flashcard

Q:: What defines scope per HIPAA/SOX/FISMA/GLBA/PCI-DSS?
A:: HIPAA=healthcare data · SOX=US public companies & accounting · FISMA=federal agencies · GLBA=financial products/services · PCI-DSS=cardholder data.
#flashcard