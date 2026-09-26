---
type: note
module: "01"
lo: "01"
tags: [concept, mod/01]
topic: "Essential Terminologies Related to Network Security Attacks"
exam_weight: unknown
status: done
unresolved: []
---
	[[MOC-Module-01]]

# Essential Terminologies (§1.1)

## Formulas
- `Risk = Asset + Threat + Vulnerability` — threat but no vuln (or vice versa) → little/no risk
- `Attack = Motive (Goal) + Method (TTPs) + Vulnerability`

## Asset
- Anything of interest to an attacker; tangible or intangible, with monetary value
- Tangible: databases, hosting server, network connections
- Intangible: secrets, critical business processes, reputation
- Critical assets must be protected from unauthorized access

## Threat
- Potential undesirable event damaging/disrupting operations and functions
- Sources:
  - **Natural**: fires, floods, power failures, lightning, meteor, earthquakes
  - **Unintentional**: insider-originating breaches, negligence, operator errors, unskilled admins, untrained employees, accidents
  - **Intentional — Internal**: disgruntled/negligent employees (mostly privileged users), fired employees; more dangerous than external (know architecture & policies; defenses focus outward)
  - **Intentional — External**: exploits existing weaknesses w/o insider help; structured vs unstructured
    - *Structured*: skilled attackers w/ tools — distributed ICMP floods, spoofing, multi-source attacks; hard to track
    - *Unstructured*: unskilled, curiosity-driven; prevented by port-scanning & address-sweeping tools

## Threat actors (types)
| Actor | Profile |
|---|---|
| Hacktivist | Hacking for political/social agenda — website defacement, DDoS |
| Cyber Terrorist/Criminal | Wide skills (phishing, ransomware); religious/political/monetary motives |
| Suicide Hacker | Brings down critical infra for a cause; not deterred by jail/punishment |
| State-Sponsored Hacker | Government-employed; steal top-secret info, damage other governments' systems |
| Organized Hacker | Professional, profit-driven (credit card, bank, monetary data) |
| Script Kiddie | Unskilled; runs tools/scripts by professional hackers |
| Industrial Spy | Commercial purposes; hired by competitors/agencies |
| Insider Threat | Disgruntled/terminated employees; undertrained staff (SE victims) |
| Thrill-Seeker | Attacks for personal enjoyment/curiosity; not necessarily destructive |

## Vulnerability
- Weakness in design/implementation exploitable to compromise security (e.g., bypassing authentication)
- Causes: hardware/software misconfiguration · insecure/poor network+app design · inherent technology weaknesses · end-user carelessness · intentional end-user acts (ex-employees leaking shared drives)
- Classes:
  - **Technological**: TCP/IP protocols (HTTP, FTP, ICMP, SNMP, SMTP inherently insecure); OS (unpatched); network devices (no password, no auth, insecure routing protocols)
  - **Configuration**: user account (insecure transmission of creds) · system account (weak passwords) · internet service misconfiguration (JavaScript, IIS/Apache/FTP/Terminal) · default passwords/settings · network device misconfig
  - **Security policy**: unwritten policy · lack of continuity · politics · lack of awareness

## Risk
- Potential loss/damage when a threat to an asset meets an exploitable vulnerability
- Examples: business disruption/shutdown · loss of productivity · loss of privacy · data theft · legal liability (lawsuits, settlement costs) · reputation damage & loss of consumer confidence

## Attack & TTPs
- Attack: intent to breach an IT system's security (obtain/edit/remove/destroy/implant/reveal w/o auth)
- **TTPs**: patterns of activities/methods of specific threat actors
  - Tactic = strategy start→finish → predict & detect early
  - Technique = technical method for intermediate results → identify vulns, prep defenses
  - Procedure = systematic approach to launch → reveals what attacker seeks
- Motives: disrupt continuity · fear/chaos via critical infrastructure · state military objectives · info theft · revenge · financial loss to target · data manipulation · ransom · propagating beliefs · reputation damage

## Cards
Q:: Risk formula?
A:: Risk = Asset + Threat + Vulnerability
#flashcard

Q:: Attack formula?
A:: Attack = Motive (Goal) + Method (TTPs) + Vulnerability
#flashcard

Q:: Why are insider attacks more dangerous than external?
A:: Insiders know network architecture, security policies, and regulations; defenses typically focus on external attacks.
#flashcard

Q:: Three classes of security vulnerabilities?
A:: Technological (protocol/OS/device), Configuration (accounts, misconfig, defaults), Security policy (unwritten, gaps, awareness).
#flashcard