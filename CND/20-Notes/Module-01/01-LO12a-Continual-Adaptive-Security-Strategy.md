---
type: note
module: "01"
lo: "12"
tags: [process, mod/01]
topic: "Continual/Adaptive Security Strategy"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Continual/Adaptive Security Strategy (§1.12)

## Computer network defense (CND)
- Applying rules, configurations, processes, measures to protect integrity, confidentiality, availability of the network's information systems & resources

## Four security approaches
| Approach | Methods / Examples |
|---|---|
| Preventive | Firewall (access control) · NAC/NAP (admission control) · IPSec & SSL (cryptographic) · biometrics (speech/facial recognition) |
| Reactive | Complements preventive; addresses what prevention missed (DoS/DDoS); IDS, SIMS, TRS, IPS |
| Retrospective | Examine causes; contain, remediate, eradicate, recover; protocol analyzers & traffic monitors (fault finding) · CSIRT/CERT (security forensics) · post-mortem analysis (risk & legal assessments) |
| Proactive | Informed decisions on future attacks; threat intelligence & risk assessment; preemptive measures |

## Adaptive strategy — four activities
| Activity | Definition |
|---|---|
| Predict | Identify most likely attacks, targets, methods before materialization; risk & vulnerability assessment, attack surface analysis, threat intelligence |
| Protect | Prior countermeasures to eliminate networking vulnerabilities; security policies, physical security, host security, firewall, IDS |
| Detect | Continuous monitoring; identify abnormalities & origins; network monitoring & packet sniffing tools |
| Respond | Contain, eradicate, mitigate, recover; incident identification, root-cause, containment, impact mitigation, eradication; decide real incident vs false positive |

- Prescribes continuous **prediction, prevention, detection, response** for comprehensive CND
- Pairs: Predict→Protect · Detect→Respond; mapped onto People, Technology, Assets, Operations, Physical contexts

## Cards
Q:: Four network security approaches?
A:: Preventive, Reactive, Retrospective, Proactive.
#flashcard

Q:: Four activities of adaptive security?
A:: Protect, Detect, Respond, Predict.
#flashcard

Q:: Which approach includes IDs/SIMS/TRS/IPS?
A:: Reactive approach (complements preventive for attacks it failed to avert).
#flashcard