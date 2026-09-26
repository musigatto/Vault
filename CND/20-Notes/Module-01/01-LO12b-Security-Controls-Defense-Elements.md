---
type: note
module: "01"
lo: "12"
tags: [concept, mod/01]
topic: "Security Controls and Defense Elements"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Security Controls & Defense Elements (course pp. 143–151)

## Administrative security controls
- Management-implemented access controls; limit/accountability/operation procedures authorizing + authenticating personnel at all levels
- Components: regulatory framework compliance · security policy · employee monitoring & supervising · information classification · separation of duties · principle of least privilege · security awareness & training

## Physical security controls
- Prevent unauthorized access to physical devices, protect info, buildings, physical assets
- Example devices: motion detectors · alarms · security guard · mantrap doors · locks · CCTV · biometrics · badge system · lighting · fences
- Categories:
  - **Prevention** (fences, locks, biometrics, mantraps)
  - **Deterrence** (security guards, warning signs)
  - **Detection** (CCTV, alarms)

## Technical security controls
- Protect data & systems from unauthorized personnel; restrict device access; preserve sensitive data integrity
- Components: system access controls (sensitivity/clearance/rights/permissions) · network access controls (routers, switches) · authentication & authorization · encryption & protocols (privacy + reliability) · network security devices (firewall, IDS) · **auditing** (track & examine device activity; identifies network weaknesses)

## Technology · Operations · People
- **Technology** — appropriate selection crucial (improper choice = false sense of security). Factors: existing topology, appropriate technologies, proper configuration. Questionnaire: which firewalls/IDS/AV? · encryption algorithm type? · centralized vs distributed access? · password complexity? · critical servers on separate segment?
- **Operations** — tech alone insufficient. Examples: create & enforce security policies · standard network operating procedures (consistent/routine ops) · business continuity + disaster recovery planning · configuration control management (inventory, software mgmt, config backup/compare, change detection, change mgmt) · incident response processes · forensics on incidents · security awareness & training · security as culture
- **People** — skilled people implement tech & run operations; collectively the **Blue Team**
  - Roles: Network Administrator (manages entire network) · Network Security Administrator (maintains security solutions) · Network Security Engineer (develops countermeasures) · Security Architect (supervises implementation) · Security Analyst (maintains privacy/integrity; evaluates security measures) · Network Technician (hardware/software components) · End User
- Blue team responsibilities: determine adequacy of security measures, examine security status & deficiencies, propose effective defenses

## Cards
Q:: Three categories of physical security controls with examples?
A:: Prevention (fences, locks, biometrics, mantraps), Deterrence (security guards, warning signs), Detection (CCTV, alarms).
#flashcard

Q:: Major elements required for effective security strategy implementation?
A:: Technology, well-defined Operations, and skilled People (blue team).
#flashcard