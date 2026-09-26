---
type: note
module: "04"
lo: "01"
tags: [threat, tool, bestpractice, mod/04]
topic: "Firewall Concerns, Capabilities, and Limitations"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Firewalls — Concerns, Capabilities, Limitations (§4.1)

## Role
- Firewall = **first line of defense**; gateway/filtering device enforcing the **network security policy** between private network and Internet
- Improper configuration/implementation **diminishes** its ability to defend; careless design leaves exploitable loopholes → attackers use techniques to bypass restrictions; care needed defining/configuring/administering rules (avoid firewall evasion)

## Why firewalls get bypassed
- Poor selection, design, implementation
- **Lack of deep traffic inspection**; poor incident detection + traffic-handling capability
- No specific **evasion protection** in the firewall (most vendors can't fully protect against evasions)
- Flawed designs / improper implementation → bypass via improper traffic handling, inspection, or detection

## Capabilities
- Prevent network scanning · control traffic · perform **user authentication** · filter packets/services/protocols · traffic logging · **NAT** · prevent malware attacks
- Examines all traffic vs the firewall ruleset; only explicitly allowed traffic passes (**default deny**)
- Filters inbound + outbound; per-packet decision (forward/drop)
- Manages public access to private resources (host applications); **logs all entry attempts + alarms** on hostile/unauthorized entry
- Functions: **gateway defense · enforce security policies · hide internal addresses · report threats · segregate trusted-network activity**

## Limitations
- Can't protect from **backdoor attacks / insider attacks**; nothing if network design/config is faulty
- **Not an alternative to antivirus/anti-malware**; can't prevent new/zero-day viruses
- Can't prevent **social engineering** or **password misuse**; can't block attacks from **higher protocol-stack layers** or from **common ports/apps**
- No defense vs **dial-in connections**; **unable to understand tunneled traffic**
- Concentrates security at one point (other systems exposed); **bottleneck** risk; can restrict valuable services (FTP, Telnet, NIS)
- Infected external devices (laptop, phone, drive) plugged in bypass it; sometimes CPU slower than network interface

## Cards
Q:: Firewall core function?
A:: Gateway/filtering device enforcing the network security policy between private network and Internet (first line of defense).
#flashcard
Q:: Typical firewall capabilities?
A:: Prevent scanning, control traffic, user auth, filter packets/services/protocols, traffic logging, NAT, malware prevention.
#flashcard
Q:: Key firewall limitations vs malware?
A:: Not an antivirus substitute; can't stop zero-day/new viruses, backdoor/insider, social engineering, password misuse, tunneled traffic.
#flashcard