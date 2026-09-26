---
type: note
module: "02"
lo: "02"
tags: [policy, mod/02]
topic: "ISO Information Security Standards, DMCA, FISMA, and Cyber Laws"
exam_weight: unknown
status: done
unresolved:
  - "ISO 27k table OCR includes a handful of corrupted pairings (e.g., 27090/27099 row ordering); only standards with clean objective text are listed."
---
[[MOC-Module-02]]

# ISO Security Standards, DMCA, FISMA, Cyber Laws (§2.2) — part b

## ISO/IEC 27k family (key standards)
| Std | Objective |
|---|---|
| ISO/IEC 27000 | IS27k overview & glossary |
| ISO/IEC 27001 | **Formal ISMS specification** (risk-driven; key advantage vs PCI-DSS) |
| ISO/IEC 27002 | Information security **controls catalogue** (all org types) |
| ISO/IEC 27003 | ISMS implementation guide |
| ISO/IEC 27004 | Infosec measurement (**metrics**) |
| ISO/IEC 27005 | Information security **risk management** |
| ISO/IEC 27006-n | ISMS & PIMS certification guide |
| ISO/IEC 27007 | Management system auditing (refers to ISO 19011) |
| ISO/IEC TR 27008 | Security controls auditing |
| ISO/IEC 27009 | Sector variants of ISO27k |
| ISO/IEC 27010 | Inter-organization communication (critical infrastructure) |
| ISO/IEC 27011 | ISMS in telecoms (ITU-T X.1051 joint) |
| ISO/IEC 27013 | ISMS & ITIL/service management integration |
| ISO/IEC 27014 | Information security governance |
| ISO/IEC TR 27015 | Financial services ISMS guideline (banks/insurance/cards) |
| ISO/IEC TR 27016 | Information security economics |
| ISO/IEC 27017 | Cloud security controls (supplements 27002) |
| ISO/IEC 27018 | **Cloud privacy** — PII protection by cloud providers |
| ISO/IEC TR 27019 | Process control in energy industry |
| ISO/IEC TR 27021 | Competences for ISMS professionals |
| ISO/IEC TS 27022 | ISMS processes |
| ISO/IEC 27031 | ICT element of **business continuity** |
| ISO/IEC 27032 | **Cybersecurity** (== Internet security); CIA in Cyberspace |
| ISO/IEC 27033-n | Network security |
| ISO/IEC 27034-n | Application security |
| ISO/IEC 27035-n | Incident management |
| ISO/IEC 27036-n | ICT supply chain & cloud |
| ISO/IEC 27037 | Digital evidence / eForensics |
| ISO/IEC 27038 | Document redaction |
| ISO/IEC 27039 | Intrusion prevention (IDS/IPS) |
| ISO/IEC 27040 | Storage security |
| ISO/IEC 27041–27043, 27050-n | Incident investigation / digital evidence analysis |
| ISO/IEC 27070 | Virtual roots of trust |
| ISO/IEC 27701 | Managing **privacy** within an ISMS |
| ISO/IEC 27100 | Cybersecurity overview/concepts |
| ISO/IEC 27102 | Cyber-insurance |
| ISO/IEC 27103 | ISMS for cybersecurity (guidance on 27001:2013) |
| ISO/IEC TS 27110 | Cybersecurity frameworks |
| ISO/IEC 27400 | **IoT** security and privacy |
| ISO/IEC TR 27550 | Privacy engineering |
| ISO/IEC 27553-n | Mobile device biometrics |
| ISO/IEC 27555 | Deleting PII / personal data |
| ISO/IEC 27556–27557 | Privacy preferences / privacy risk management |
| ISO/IEC 27559 | De-identification of personal data |
| ISO/IEC TS 27570 | Smart city privacy |

## DMCA (Digital Millennium Copyright Act)
- US copyright law implementing **two 1996 WIPO treaties** (WIPO Copyright Treaty; WIPO Performances & Phonograms Treaty)
- Prohibitions: circumvention of **technological protection measures**; removal/alteration of **copyright management information** (civil remedies + criminal penalties)
- **5 titles**:

| Title | Content |
|---|---|
| I | WIPO Treaty Implementation — anti-circumvention + anti-tampering |
| II | Online Copyright Infringement Liability Limitation — §512, **4 safe-harbor categories** (transitory communications · system caching · storage at direction of users · information location tools) + special rules for nonprofit educational institutions |
| III | Computer maintenance or repair — owner/lessee may copy program while repairing |
| IV | Miscellaneous (Copyright Office clarification, ephemeral recordings, sound recording performance right, residual payments) |
| V | Vessel Hull Design Protection Act (VHDPA) — protections for vessel hulls ≤ 200 ft |

## FISMA (Federal Information Security Management Act, 2002)
- Comprehensive framework for **effectiveness of information security controls** over federal operations & assets
- Each federal agency must **develop, document, implement an agency-wide program** for info security (incl. contractor/other-source managed)
- Provides:
  - Standards for **categorizing information/info systems by mission impact**
  - Standards for **minimum security requirements**
  - Guidance for **selecting** security controls
  - Guidance for **assessing** controls & determining effectiveness
  - Guidance for **security authorization** of information systems

## Other information security acts & laws
| Act | Key point |
|---|---|
| Cybersecurity Information Sharing Act (CISA, 2015) | Non-federal entities share cyber threat indicators with the Federal Government |
| Freedom of Information Act (FOIA) | Public right to request federal agency records; **9 exemptions** (privacy, national security, law enforcement) |
| Electronic Communications Privacy Act (ECPA, 1986) | Updated Federal Wiretap Act 1968; extended to computer/digital communications; clarified/updated by USA PATRIOT Act |
| Human Rights Act 1998 (UK) | Underpins rights of European Convention on Human Rights |
| Freedom of Information Act 2000 (UK) | Disclosure of info held by UK public authorities |
| Computer Fraud and Abuse Act (CFAA) | **18 U.S.C. § 1030**; unauthorized access / exceeding authorized access to a "protected computer" (term added 1996); criminal law, civil actions since 1994 |

## Cyber laws in different countries
- Based on **UNCITRAL Model Law on Electronic Commerce** framework principles

| Country | Examples |
|---|---|
| US | Copyright fair use (§107) · Lanham (Trademark) Act (15 USC §§1051–1127) · ECPA · FISA · Protect America Act 2007 · Privacy Act 1974 · NIIP Act 1996 · Computer Security Act 1987 · FISMA · DMCA · SOX |
| Australia | Trade Marks Act 1995 · Patents Act 1990 · Copyright Act 1968 · Cybercrime Act 2001 |
| UK | Copyright, Etc. and Trademarks (Offenses & Enforcement) Act 2002 · Trademarks Act 1994 · Computer Misuse Act 1990 |
| China | Copyright Law (amend. 27 Oct 2001) · Trademark Law (amend. 27 Oct 2001) |
| India | Patents (Amendment) Act 1999 · Trade Marks Act 1999 · Copyright Act 1957 · Information Technology Act |
| Germany | §202a Data Espionage · §303a Alteration of Data · §303b Computer Sabotage |

## Cards
Q:: ISO/IEC 27001 vs 27002?
A:: 27001 = formal ISMS specification; 27002 = information security controls catalogue.
#flashcard

Q:: ISO/IEC 27018 and ISO/IEC 27400?
A:: 27018 = cloud privacy (PII by CSPs); 27400 = IoT security and privacy.
#flashcard

Q:: DMCA Title II?
A:: Online Copyright Infringement Liability Limitation — 4 safe-harbor categories for service providers (transitory · caching · storage · location tools).
#flashcard

Q:: FISMA core requirement?
A:: Each federal agency develops, documents, and implements an agency-wide information security program for its information/information systems.
#flashcard

Q:: CFAA basis?
A:: 18 U.S.C. § 1030 — intentionally accessing a protected computer without authorization / exceeding authorized access.
#flashcard