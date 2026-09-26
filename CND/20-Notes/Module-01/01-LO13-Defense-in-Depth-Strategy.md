---
type: note
module: "01"
lo: "13"
tags: [process, mod/01]
topic: "Defense-in-Depth Security Strategy"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Defense-in-Depth Strategy (§1.13)

- Comprehensive approach; security implemented at **multiple layers** of the network stack
- Military principle: harder to defeat a complex, multi-layered defense than a single barrier
- Break in one layer → attacker only reaches the next layer; buys defenders time to deploy new/updated countermeasures; minimizes adverse impact

## Layers (7)
| Layer | Scope |
|---|---|
| 1. Policies, Procedures, & Awareness | First level of countermeasures for every org; prevent resource misuse & unauthorized operations |
| 2. Physical | Protect assets from physical threats (locks, access controls, security personnel, firefighting, power supply, video surveillance, lighting, alarms) |
| 3. Perimeter | Security at perimeter level (DMZ/public servers, Internet perimeter security) |
| 4. Internal Network | Measures for internal network (internal servers, intranet, internal LAN, routers, firewalls, switches) |
| 5. Host | Per-host measures (OS, antivirus, patch management, password management, logging, host firewall) |
| 6. Application | Application-level security |
| 7. Data | Data at rest & in transit (encryption, hashing, data access controls, DLP, backup, recovery, retention, disposal) |

## Correlation
- Data is at the core; layers wrap around it: Physical → Host/Network → Application → Data
- Enforced through the security controls & elements in [[01-LO12b-Security-Controls-Defense-Elements]] (administrative/physical/technical; technology-operations-people)
- Continual/adaptive cycle ([[01-LO12a-Continual-Adaptive-Security-Strategy]]) + defense-in-depth = the two strategies required for effective protection

## Cards
Q:: Seven defense-in-depth layers?
A:: Policies/procedures/awareness, Physical, Perimeter, Internal network, Host, Application, Data.
#flashcard

Q:: Why does defense-in-depth help after a breach?
A:: A break in one layer only exposes the next layer, giving defenders time to deploy new/updated countermeasures and limiting impact.
#flashcard