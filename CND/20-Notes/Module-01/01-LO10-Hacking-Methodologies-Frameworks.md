---
type: note
module: "01"
lo: "10"
tags: [process, mod/01]
topic: "Attacker Hacking Methodologies and Frameworks"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Hacking Methodologies & Frameworks (§1.10)

## CEH Hacking Methodology (5 phases)
| Phase | Activities |
|---|---|
| 1. Reconnaissance | Gather max info on target (competitive intelligence); social engineering, dumpster diving (usernames, passwords, bank/CC statements, SSNs, phone numbers), **whois**. Broader intel → easier entry |
| 2. Scanning | More in-depth probing; mapping systems/routers/firewalls via **Traceroute**, **Cheops**; dialers, port scanners, network mappers, ping tools, **vulnerability scanners**; extract live machines, ports/status, OS, device type, uptime. Defense: shut unused services, port filtering |
| 3. Gaining Access | Actual hacking; exploit identified vulns (password cracking, **stack-based buffer overflows**, DoS, session hijacking); escalate privileges; impact can be catastrophic; **smurf attacks** make users flood each other |
| 4. Maintaining Access | Retain privileges; use system as launchpad or stay low-profile; sniffer for Telnet/FTP traffic; install **backdoor/trojan** (app level) or **rootkit** (kernel level); Windows trojans run as local admin services |
| 5. Clearing Tracks | Erase evidence; **PsTools · Netcat · trojans** (edit log files); **steganography** (hide data in image/sound) · **tunneling** (carry one protocol over another; extra TCP/IP header space); defense: host IDS + AV |

## Lockheed Martin Cyber Kill Chain (7 phases)
1. **Reconnaissance** — collect target/system/org info; whois, DNS footprinting, scan open ports/services
2. **Weaponization** — create tailored deliverable payload (exploit + backdoor); phishing campaign; exploit kits; botnets
3. **Delivery** — transmit weapon (email attachment, malicious link, USB, watering hole); gauges effectiveness of target defenses
4. **Exploitation** — trigger malicious code to exploit OS/app/server vuln; mitigations incl. hardening (blocks zero-days)
5. **Installation** — install more malware (backdoors), hide from firewalls; maintain access; spread laterally
6. **Command and Control** — two-way channel victim↔adversary server (web traffic, email, DNS); encrypted/hidden
7. **Actions on Objectives** — accomplish goals: access confidential data, disrupt services, destroy operational capability, or launch another attack

## MITRE ATT&CK
- Globally accessible knowledge base of adversary tactics/techniques from real-world observations
- Three matrices: **Enterprise · Mobile · PRE-ATT&CK**
- **Enterprise = 11 tactics** derived from later stages (exploit, control, maintain, execute) of the Kill Chain → deeper granularity
- Tactics: Initial Access · Execution · Persistence · Privilege Escalation · Defense Evasion · Credential Access · Discovery · Lateral Movement · Collection · Exfiltration · Command and Control
- Use cases: prioritize CND capability dev · alternatives analysis · coverage determination · describe intrusion chain (start→finish) · identify tradecraft commonalities/distinguishers · connect mitigations, weaknesses, adversaries

## Mnemonic
> [!tip] Mnemonic
> CEH: **R-S-G-M-C** (Recon → Scan → Gain → Maintain → Clear). Kill Chain: Recon → Weaponize → Deliver → Exploit → Install → C2 → Actions.

## Cards
Q:: CEH five hacking phases?
A:: Reconnaissance, Scanning, Gaining Access, Maintaining Access, Clearing Tracks.
#flashcard

Q:: Lockheed Martin Cyber Kill Chain phases?
A:: Reconnaissance, Weaponization, Delivery, Exploitation, Installation, Command and Control, Actions on Objectives.
#flashcard

Q:: MITRE ATT&CK Enterprise matrices and source of its 11 tactics?
A:: Enterprise, Mobile, and PRE-ATT&CK matrices; the 11 Enterprise tactics derive from the later Cyber Kill Chain stages (exploit, control, maintain, execute).
#flashcard