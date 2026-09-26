---
type: note
module: "02"
lo: "02"
tags: [policy, mod/02]
topic: "Regulatory Frameworks and Laws — PCI-DSS, HIPAA, GDPR, SOX, GLBA"
exam_weight: unknown
status: done
unresolved:
  - "GLBA website page reference split mid-list; top-info-protection list incomplete in OCR."
---
[[MOC-Module-02]]

# Regulatory Frameworks and Laws (§2.2) — part a

## PCI-DSS (Payment Card Industry Data Security Standard)
- **Proprietary** info-security standard for orgs handling cardholder info for major debit/credit/prepaid/e-purse/ATM/POS cards
- Applies to: merchants, processors, acquirers, issuers, service providers, **and all entities that store, process, or transmit cardholder data**
- Framework of specs, tools, measurements, support resources; min. requirement set
- **6 high-level requirements** (dev/maintained by **PCI Security Standards Council**):
  1. Build and Maintain a Secure Network
  2. Protect Cardholder Data
  3. Maintain a Vulnerability Management Program
  4. Implement Strong Access Control Measures
  5. Regularly Monitor and Test Networks
  6. Maintain an Information Security Policy
- Non-compliance → **fines or termination of payment card processing privileges**

## HIPAA (Health Insurance Portability and Accountability Act, 1996)
- HHS develops regulations protecting privacy/security of health information
- **Covered entities**: health plans, health care clearinghouses, certain health care providers
- **Administrative Simplification Statute and Rules**:

| Rule | Purpose |
|---|---|
| Electronic Transaction & Code Sets | Providers doing business electronically use same transactions, code sets, identifiers (ASC X12N or NCPDP) |
| Privacy Rule | Federal protections for protected health information (PHI); patient rights (access, copy, corrections); sets limits on non-authorized uses/disclosures |
| Security Rule | Administrative, physical, technical safeguards for **electronic PHI** — confidentiality, integrity, availability |
| National Provider Identifier (NPI) | Unique ID for covered providers; **10-position, intelligence-free numeric** identifier; used in all HIPAA administrative/financial transactions |
| Enforcement Rule | Compliance, investigations, civil money penalties, hearings |

## GDPR (General Data Protection Regulation)
- EU law on **data protection & privacy for all individuals in EU/EEA**; also export of personal data outside
- Replaces **Data Protection Directive 95/46/EC**
- Goals: harmonize data privacy laws across Europe; protect & empower all EU citizens' data privacy
- **Two types of data handlers**:
  - **Controller** — determines purposes and means of processing (alone or jointly)
  - **Processor** — processes personal data on behalf of controller
- Serious penalties for non-compliance; hire a **Data Protection Officer** for special-category / large-scale processing

## SOX (Sarbanes-Oxley Act, 2002)
- US federal law; new/enhanced standards for all US **public company boards, management, and public accounting firms**
- 11 titles (key):

| Title | Focus |
|---|---|
| I | **PCAOB** — independent oversight of auditors |
| II | Auditor independence; restricts non-audit services (consulting) for same clients |
| III | Corporate responsibility — senior execs individually responsible for financial reports |
| IV | Enhanced financial disclosures; **Section 404**: management & auditors establish internal controls and report on effectiveness |
| V | Analyst conflicts of interest |
| VI | SEC commission resources & authority |
| VII | Studies and reports (Comptroller General + SEC) |
| VIII | Corporate & Criminal Fraud Accountability ("of 2002") — penalties + **whistle-blower protections** |
| IX | White Collar Crime Penalty Enhancement ("of 2002") — failure to certify reports = criminal offense |
| X | Corporate tax returns — CEO signs company tax return |
| XI | Corporate Fraud Accountability ("of 2002") — SEC can freeze large/unusual transactions |

- Also key: **Section 302** — senior management **certifies accuracy of reported financial statements**

## GLBA (Gramm-Leach-Bliley Act)
- US federal law; requires **financial institutions** to explain how they share/protect customers' private info
- Covers: companies offering loans, financial/investment advice, insurance
- Objective: ease transfer of financial info between institutions/banks, make individual rights specific via security requirements
- Key points:
  - Protect consumer's personal financial info held by institutions + service providers
  - Privacy notices explaining sharing practices; customers can **limit sharing** of their info
- **Violations**:

| Party | Penalty |
|---|---|
| Organization | Civil penalty ≤ **$100,000** per violation |
| Officers/directors | Personally liable ≤ **$10,000** per violation |
| Org + officers/directors | Fines or **imprisonment ≤ 5 years**, or both |

- Top information-protection requirements: **Financial Privacy Rules** (privacy notice after relationship established) + **Safeguards Rules** (written info security plan for protecting clients' NPI)
- Security/encryption requirements: administrative, technical, physical standards for customer records; encryption to reduce disclosure/alteration risk (key mgmt, reliability, securing encrypted endpoints)

## Cards
Q:: Six high-level PCI-DSS requirements?
A:: Build/Maintain a Secure Network · Protect Cardholder Data · Maintain a Vulnerability Management Program · Implement Strong Access Control Measures · Regularly Monitor & Test Networks · Maintain an Information Security Policy.
#flashcard

Q:: HIPAA Administrative Simplification Rules?
A:: Electronic Transaction & Code Sets · Privacy Rule · Security Rule · National Provider Identifier (NPI, 10-digit intelligence-free) · Enforcement Rule.
#flashcard

Q:: GDPR controller vs processor?
A:: Controller = determines purposes/means of processing; Processor = processes data on behalf of the controller.
#flashcard

Q:: SOX Section 302 and Section 404?
A:: 302: senior mgmt certifies accuracy of financial statements. 404: management + auditors establish internal controls and report on their effectiveness.
#flashcard

Q:: GLBA penalty caps?
A:: Org ≤ $100,000 per violation; officers/directors personally liable ≤ $10,000 each; fines or imprisonment ≤ 5 years.
#flashcard