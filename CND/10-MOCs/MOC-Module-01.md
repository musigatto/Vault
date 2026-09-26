---
type: moc
module: "01"
tags: [concept, mod/01]
topic: "Network Attack and Defense Strategies"
exam_weight: unknown
status: done
unresolved:
  - "Exam blueprint per-module weights are not stated in the courseware (Exam 312-38: 4 h, 100 questions)."
---
# Module 01 — Network Attack and Defense Strategies

> [!abstract] Scope
> 13 LOs · 13 sections · courseware pp. 3–155. Attack vectors across the stack (network, application, human, email, mobile, cloud, wireless, supply chain), attacker methodologies & frameworks, and defense strategies (continual/adaptive + defense-in-depth).

## Sections
| LO   | §    | Section                                                       | Course pp. |
| ---- | ---- | ------------------------------------------------------------- | ---------- |
| LO01 | 1.1  | Essential Terminologies Related to Network Security Attacks   | 6          |
| LO02 | 1.2  | Examples of Network-level Attack Techniques                   | 21         |
| LO03 | 1.3  | Examples of Application-level Attack Techniques               | 45         |
| LO04 | 1.4  | Examples of Social Engineering Attack Techniques              | 66         |
| LO05 | 1.5  | Examples of Email Attack Techniques                           | 70         |
| LO06 | 1.6  | Examples of Mobile Device-specific Attack Techniques          | 78         |
| LO07 | 1.7  | Examples of Cloud-specific Attack Techniques                  | 85         |
| LO08 | 1.8  | Examples of Wireless Network-specific Attack Techniques       | 102        |
| LO09 | 1.9  | Examples of Supply Chain Attack Techniques                    | 107        |
| LO10 | 1.10 | Attacker Hacking Methodologies and Frameworks                 | 120        |
| LO11 | 1.11 | Fundamental Goal, Benefits, and Challenges in Network Defense | 131        |
| LO12 | 1.12 | Continual/Adaptive Security Strategy                          | 138        |
| LO13 | 1.13 | Defense-in-Depth Security Strategy                            | 152        |

> [!note] LO12 splits into two notes: `a` (continual/adaptive cycle, pp. 138–142) and `b` (security controls & defense elements, pp. 143–151).

## Exam facts
- Exam **312-38** · **4 hours** · **100 questions** · availability via ECCouncil & VUE (passing score: see EC-Council FAQ).
- Blueprint per-module weights: **not in courseware** → `exam_weight: unknown`.

## Notes
```base
filters:
  and:
    - 'type == "note"'
    - file.inFolder("CND/20-Notes/Module-01")
views:
  - type: list
    name: Notes
    order:
      - file.name
```

## Module map
- Canvas: [[40-Canvas/01-attack-and-defense-strategies.canvas|Attack & Defense Strategies Map]]
- Flows to visualize: CEH 5 phases · Cyber Kill Chain 7 stages · MITRE ATT&CK 11 tactics · APT phases · Adaptive strategy cycle (Predict→Protect→Detect→Respond) · Defense-in-depth layers

## Cross-links
- [[00-Home]]
- [[Question-Bank]] · [[Answer-Key]] · [[Mock-Exam-100]]
- Related modules: [[MOC-Module-04]] (perimeter/firewall/IDS), [[MOC-Module-20]] (threat intelligence), [[MOC-Module-18]] (risk anticipation)

## Unresolved
- Per-module exam blueprint weights (not stated in courseware).
- "Reverse social engineering" is listed in §1.4 scope but no definition appears in the extracted text.