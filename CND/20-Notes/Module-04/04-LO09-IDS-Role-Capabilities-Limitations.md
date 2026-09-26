---
type: note
module: "04"
lo: "09"
tags: [concept, tool, threat, mod/04]
topic: "IDs role, Capabilities, Limitations, Concerns"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# IDS — Role, Capabilities, Limitations, Concerns (§4.9)

## Role & why needed
- **IDS = detect intrusions; IPS = detect AND prevent** (inline). Same principle; IPS adds firewall-like technology; IPS also corrects **CRC errors, defragments packet streams, detects TCP sequencing issues, manages transport/network-layer options**
- IDS works from **inside the network** (firewall only looks at outside threats); placed **behind the firewall**, inspecting all traffic with heuristics + pattern matching
- **Why IDS?** Firewalls allow/deny by rules but don't inspect contents of legitimate traffic (e.g., port 80/25 traffic passes uninspected). Legitimate traffic may carry malicious content → IDS inspects it, **signature-based analysis**, alerts defenders

## Capabilities / IDS functions
- **Extra layer of security (defense-in-depth)**; does things basic firewalls can't; minimizes missed threats from **firewall evasions**
- Monitoring + analyzing user/system activities · analyzing system configurations + vulnerabilities · assessing system/file integrity · recognizing typical attack patterns · analyzing abnormal activity · tracking user **policy violations**
- On detection: issue alerts to admins → defenders apply countermeasures (block, terminate sessions, back up systems, route to trap/legal infrastructure)
- Alerts + logs support **forensic research** and future patch/signature installs
- Records info about events → forwards to centralized log servers, **SIEM**, enterprise management
- Sends alerts via email, pop-up on IDS UI; excludes environment/extraneous criteria for suspicious events

## What an IDS/IPS is NOT (limitations)
Not every security device is an IDS:
- **Network logging systems** — traffic-monitoring only; detect DoS vulnerabilities on congested networks
- **Vulnerability assessment tools** — check for OS/service bugs (security scanners)
- **Antivirus products** — detect malicious software (viruses, Trojans, worms, bacteria, logic bombs); feature-similar to IDS, effective breach detection
- **Security/cryptographic systems** — protect data from theft/alteration through user authentication: VPN, SSL, S/MIME, Kerberos, RADIUS

## IDS/IPS security concerns (deployment mistakes)
- **Improper configuration/management makes IDS/IPS ineffective**; plan carefully: planning, preparation, prototyping, testing, specialized training
- Common mistakes: deploying where it **doesn't see all traffic** · ignoring alerts · no response policy/plan (what is normal vs malicious? action per alert?) · **not fine-tuning false positives/negatives** · not updating signatures · **monitoring only inbound traffic**
- Inefficient infrastructure planning → floods the network with alerts (ability to disable it)
- **Incorrect sensitivity**: max sensitivity → many false positives → real alerts may be missed
- **NIDS without IPsec**: encrypted-tunnel traffic → only packet-level analysis (app contents inaccessible) → more vulnerable
- Place **IDS sensors near choke points** (if cost effective) to also monitor **outbound + internal host traffic**
- Don't deploy sensors on a single NIC or multiple data links (sensing + reporting on same interface → attacker can disable IDS/alter data) → connect to a **dedicated monitoring network**

## Cards
Q:: IDS vs IPS core difference?
A:: IDS detects + alerts; IPS detects + actively blocks (inline); IPS also fixes CRC, defragmentation, TCP sequencing, layer options.
#flashcard
Q:: Why implement an IDS behind the firewall?
A:: Firewalls allow/deny by rules but never inspect legitimate traffic content; IDS inspects it for malicious payloads/signatures.
#flashcard
Q:: What is NOT an IDS?
A:: Network logging systems, vulnerability assessment tools, antivirus products, cryptographic systems (VPN/SSL/S-MIME/Kerberos/RADIUS).
#flashcard
Q:: Common IDS deployment mistakes?
A:: Wrong placement (not seeing all traffic), ignoring alerts, no response plan, not tuning false pos/neg, stale signatures, inbound-only monitoring.
#flashcard
Q:: NIDS + encrypted traffic problem?
A:: Without IPsec visibility, NIDS only does packet-level analysis of encrypted tunnels (app contents inaccessible) → more vulnerable.
#flashcard