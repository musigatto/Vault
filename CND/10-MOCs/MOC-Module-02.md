---
type: moc
module: "02"
tags: [concept, mod/02]
topic: "Module 02 — Administrative Network Security"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights are not stated in the courseware (Exam 312-38: 4 h, 100 questions)."
  - "ISO 27k table in the PDF contains a few OCR-corrupted pairings; only standards with clean objective text are listed."
---
# Module 02 — Administrative Network Security

> [!abstract] Scope
> 7 LOs · 7 sections · courseware pp. 157–285. Administrative (non-technical) network security: regulatory frameworks/laws/compliance, security-policy design & development, security awareness training, other administrative measures, IT asset management, and keeping up with security trends/threats.

## Sections
| LO   | §    | Section                                                        | Course pp. |
| ---- | ---- | -------------------------------------------------------------- | ---------- |
| LO01 | 2.1  | Regulatory Frameworks Compliance                               | 160        |
| LO02 | 2.2  | Regulatory Frameworks, Laws, and Acts                          | 168        |
| LO03 | 2.3  | Design and Development of Security Policies                    | 194        |
| LO04 | 2.4  | Security Awareness Training                                    | 250        |
| LO05 | 2.5  | Other Administrative Security Measures                         | 259        |
| LO06 | 2.6  | Asset Management                                               | 263        |
| LO07 | 2.7  | How to Stay Up to Date on Security Trends and Threats          | 282        |

> [!note] LO02 splits into two notes: `a` (PCI-DSS · HIPAA · GDPR · SOX · GLBA, pp. 168–193) and `b` (ISO 27k standards · DMCA · FISMA · other acts · cyber laws). LO03 also splits into two: `a` (policy fundamentals/design, pp. 194–215) and `b` (specific policy documents + implementation checklist, pp. 215–249).

## Compliance focus
- Hierarchy driving Compliance Program: **Frameworks → Policies → Standards → Procedures/Guidelines**.
- Frameworks covered: PCI-DSS (6 high-level requirements) · HIPAA (Administrative Simplification) · GDPR (Controllers/Processors, DPO) · SOX (11 titles, §§302/404) · GLBA (penalties ≤ $100K org / ≤ $10K officers / ≤ 5 yrs imprisonment) · ISO/IEC 27k · DMCA (5 titles) · FISMA · CISA · CFAA (18 USC §1030) etc.

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions** · availability via ECCouncil & VUE (passing score: see EC-Council FAQ).
- Blueprint per-module weights: **not in courseware** → `exam_weight: unknown`.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("CND/20-Notes/Module-02")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/02-security-policy-flow.canvas|Security Policy & IT Management Flow]]
- Flows to visualize: security-policy creation & implementation steps (Risk→Guidelines→Management→Penalties→Publish→Sign→Enforce→Train→Review) · policy document content checklist · ITAM process (Identification→Tracking→Maintenance) · asset lifecycle across ITAM types

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- Related modules: [[MOC-Module-01]] (defense-in-depth) · [[MOC-Module-19]] (policy/architecture/business continuity — admin security) · [[MOC-Module-04]] (log management/audit under compliance)

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- ISO 27k OCR-corrupted pairings (only clean standards listed in [[02-LO02b-ISO-Standards-DMCA-FISMA-Cyber-Laws]]).