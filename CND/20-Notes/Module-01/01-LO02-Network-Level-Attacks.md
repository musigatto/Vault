---
type: note
module: "01"
lo: "02"
tags: [threat, mod/01]
topic: "Network-level Attack Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Network-level Attacks (§1.2)

## Reconnaissance
- Primary objectives: collect network info, system info, organizational info (names, phones, designations → basis for social engineering)
- Techniques: packet sniffing · port scanning · ping sweeping (ICMP; well-configured ACL prevents) · DNS footprinting (DNS lookup + whois) · social engineering
- **Active** (sends packets: port scans, OS scans, traceroute) vs **Passive** (sniffing only)

## Network Sniffing
- Capturing, decoding, inspecting packets on TCP/IP network to steal user IDs, passwords, credit card numbers; passive → hard to detect
- Types: **internal** (already on LAN) · **external** (intercepts at firewall level) · **wireless** (anywhere in RF range)

## Man-in-the-Middle (MITM)
- Form of session hijacking; eavesdrop → intrude → intercept → modify
- Splits TCP connection: client-to-attacker + attacker-to-server; in HTTP the client↔server TCP connection is targeted
- Susceptible: login functions, unencrypted connections, financial sites, telnet, wireless

## Password Attacks
- Common weak passwords: `password`, `root`, `administrator`, `admin`, `test`, `guest`, `qwerty`, personal info
- Techniques:
  - **Dictionary**: guess common words; faster than brute force (esp. long/complex pw in list); LAN Manager auth is case-insensitive → easier
  - **Brute Force**: all character combinations; time/resource heavy; suits short/simple passwords
  - **Hybrid**: dictionary term + appended/prepended numbers, dates, symbols
  - **Birthday**: brute-force kind on hash functions; ≥2 of 23 people share a DOB with P>0.5; relies on hash collisions
  - **Rainbow Table**: large pre-matched hash↔plaintext lookup; compare against hashed DB
- Acquisition vectors also: social engineering, spoofing, phishing, malware, sniffing, keylogging

## Privilege Escalation
- Exploits design flaws, programming errors, bugs, configuration oversights
- **Vertical**: user account → higher-privilege account (e.g., admin)
- **Horizontal**: user account → another user account with SAME privileges (e.g., bank user A → user B's account)

## DNS Poisoning / Spoofing
- Unauthorized manipulation of IP addresses in DNS cache; redirects victim to fake/malicious server (e.g., google.com → goggle.com like fake)

## ARP Poisoning
- ARP maps IP → MAC; **provides no authenticity verification** — hosts accept ARP replies even without a request
- Attacker associates own MAC with victim's IP → traffic for victim IP routed to attacker

## DHCP Starvation
- Floods DHCP server with fake DHCP requests (spoofed MACs, tool: **Gobbler**) → exhausts IP pool → DoS for valid users; like SYN flood
- Defenses: **port security** (limit MACs per port) · **DHCP snooping** (Cisco Catalyst; filters untrusted DHCP messages)

## DHCP Spoofing (rogue DHCP)
- Rogue DHCP between client and real server; responds first → client accepts; can set attacker as default gateway/DNS (silent MITM, may remain undetected) or wrong IP (DoS)
- Mitigation: mark interface where rogue is connected as **untrusted** (blocks ingress DHCP server messages)
- Message flow: DHCPDISCOVERY/SOLICIT (broadcast) → DHCPOFFER/ADVERTISE (unicast) → DHCPREQUEST (broadcast) → DHCPACK/REPLY (unicast)

## MAC Spoofing
- Sniff network for MACs of clients associated to a switch port, reuse one to receive that user's traffic; MAC-filtered WLAN APs also affected
- Purposes: spread malware, bypass auth checks, steal sensitive info

## DoS / DDoS
- **Network DoS** exploits protocol implementations: **TCP SYN flooding · UDP flooding · ICMP Smurf flooding · intermittent flooding**
- Types: bandwidth attacks (flood traffic) vs connectivity attacks (exhaust connections/resources)
- **DDoS**: large-scale coordinated; attacker→handler→zombies→target; primary target = victim service, secondary target = compromised systems
  - *Network-centric*: consume bandwidth · *Application-centric*: inundate with packets
- Impact: loss of goodwill, disabled network, financial loss; also used as **decoys** (crash unrelated systems while real target is hit)

## Malware
| Type        | Behavior                                                                                                            |
| ----------- | ------------------------------------------------------------------------------------------------------------------- |
| Virus       | Self-replicating via host program; spreads via network/removable media; **armored** = obfuscated to evade detection |
| Trojan      | Masquerades as legitimate software; server/client model; remote access, file theft                                  |
| Adware      | Tracks browsing for ads; legit when consented; malicious when collects w/o permission (→ spyware)                   |
| Spyware     | Extracts user info to attacker; e.g., keylogger; degrades performance, disables firewall/AV                         |
| Rootkit     | Hides OS compromise; kernel-level; used to hide viruses/worms/bots                                                  |
| Backdoor    | Bypasses authentication to gain admin privileges; not logged                                                        |
| Logic bomb  | Malicious action on a logic condition (e.g., date); used for extortion/blackmail                                    |
| Botnet      | Compromised PCs (bots) under **botmaster**; spam, DDoS, identity theft, ad-click fraud                              |
| Ransomware  | Locks/encrypts files until ransom; no guarantee of recovery                                                         |
| Polymorphic | Changes signature to evade pattern-matching; payload encrypted                                                      |
- Spyware/adware install vector: cookies, plug-ins, file sharing, freeware/shareware; consumes bandwidth + CPU/memory

## Advanced Persistent Threat (APT)
- Unauthorized access maintained undetected for a long period; objective = **steal sensitive info**, not sabotage
- Advanced = sophisticated exploitation (zero-days); Persistent = external **C&C**; Threat = human coordination
- Characteristics: objectives · timeliness · resources · risk tolerance · skills & methods · actions · attack origination points · numbers involved · knowledge sources · **multiphased** (recon → gaining access → discovery → capture → data exfiltration) · tailored to vulns · multiple entry points · evades signature-based detection · specific warning signs
- Warning signs: inexplicable account activity, backdoor trojans, unusual file transfers/uploads, unusual DB activity

## Cards
Q:: Two types of DoS and examples?
A:: Bandwidth (flood traffic) and Connectivity (exhaust resources); e.g. TCP SYN flood, UDP flood, ICMP Smurf flood, intermittent flooding.
#flashcard

Q:: How does a DHCP starvation attack work and two mitigations?
A:: Floods DHCP server with fake DHCP requests (Gobbler) to exhaust the IP pool → DoS. Mitigate with port security and DHCP snooping.
#flashcard

Q:: Vertical vs horizontal privilege escalation?
A:: Vertical = same account → higher-privilege account; Horizontal = one user account → another with equal privileges.
#flashcard

Q:: Why is ARP easy to poison?
A:: ARP provides no authenticity verification; hosts even accept unsolicited ARP replies.
#flashcard