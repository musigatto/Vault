---
type: exam
module: "key"
tags: [exam, mod/01]
topic: "CND Answer Key — one-line justifications"
exam_weight: high
status: draft
unresolved: []
---
# Answer Key

> [!info] Convention
> `Q#### → Answer` + one-line justification citing `Module NN · Topic`.

## Module 01
- Q001 — **A** — Courseware §1.1: *Risk = Asset + Threat + Vulnerability* (Module 01 · Essential Terminologies).
- Q002 — **B** — *DHCP starvation* floods the server with spoofed-MAC requests using tools such as Gobbler, exhausting the IP pool → DoS (Module 01 · Network-level Attacks).
- Q003 — **C** — *Session side-jacking* uses packet sniffing to intercept session cookies when the site does not use SSL/TLS for the **entire** session (Module 01 · Application-level Attacks — Session Hijacking).
- Q004 — **B** — *Reactive approach* is complementary to preventive and includes security monitoring methods such as IDS, SIMS, TRS, and IPS (Module 01 · Continual/Adaptive Security Strategy).
- Q005 — **B** — The 11 Enterprise tactics are derived from the later Cyber Kill Chain stages: exploit, control, maintain, and execute (Module 01 · Hacking Methodologies — MITRE ATT&CK).

## Module 02
- Q006 — **B** — Compliance hierarchy: *Frameworks → Policies → Standards → Procedures → Guidelines* (Module 02 · Regulatory Frameworks Compliance).
- Q007 — **A** — A *data controller* alone or jointly determines purposes/means of processing; a *data processor* processes on the controller's behalf; controllers/processors in the EU must comply with GDPR (Module 02 · Regulatory Frameworks — GDPR).
- Q008 — **D** — *Prudent*: all services blocked by default, network defender individually enables safe/necessary services, maximum security + everything logged (Module 02 · Security Policy — Internet Access Policies).
- Q009 — **B** — Asset categorization groups by type, usage, location, owner/department, lifecycle stage, vendor/manufacturer, criticality, and license type (Module 02 · Asset Management — ITAM process).
- Q010 — **A** — A *Secret*-level user has "access to secret + confidential + restricted + unclassified" but **NOT** top secret; only Top Secret users access everything (Module 02 · Security Awareness Training — Data Classification).

## Module 03
- Q011 — **C** — *Research* honeypots evaluate the attacker's steps precisely to build countermeasures; *production* honeypots look real next to production servers to identify attackers (Module 03 · Essential Network Security Solutions — Honeypot).
- Q012 — **C** — NAC checks AV presence/update, configured firewall or IPS, viruses, and OS updates — a Wi-Fi password check is **not** listed (Module 03 · Essential Network Security Solutions — NAC).
- Q013 — **B** — *TACACS+* (Cisco) separates AAA and encrypts the entire client–server communication including the password; it is connection-oriented over **TCP port 49** vs RADIUS (UDP) (Module 03 · Essential Network Security Protocols — TACACS+).
- Q014 — **A** — *AH* authenticates the sender only; *ESP* authenticates the sender **and** encrypts the data (Module 03 · Essential Network Security Protocols — IPsec).
- Q015 — **C** — *UTM* combines firewall, IDS, anti-malware, spam filter, content filtering, DLP, and VPN in one appliance; a known drawback is single point of failure (Module 03 · Essential Network Security Solutions — UTM).

## Module 04
- Q016 — **B** — *Packet filtering* firewalls "work at the network level of the OSI model," checking each packet's header against rules; circuit-level works at the session layer and application-level at the application layer (Module 04 · LO02 Firewall Technologies).
- Q017 — **A** — Deployment *L1 (outside the perimeter firewall)* is tuned to least-sensitive attacks, "logs attack attempts only, no alerts"; L2 DMZ covers low–moderate, L3 backbone medium–high, L4 critical high-impact (Module 04 · LO12 NIDS Deployment Locations).
- Q018 — **A** — Because encrypted payloads can't be matched to signatures, the courseware advises placing "an IDS behind a VPN termination with SSL encryption" so traffic arrives decrypted (Module 04 · LO13 Dealing with False Negatives).
- Q019 — **C** — *Static* port security "allows only a single MAC address to be connected to a port"; sticky assigns per port (lost on reboot), dynamic is the CAM default (Module 04 · LO16 Switch Security Measures).
- Q020 — **D** — The *SDP controller* is "an authentication point that evaluates the policy and grants access to the client" and determines which client↔gateway pairs communicate; traffic tunnels only after controller approval (Module 04 · LO17 SDP Architecture and Components).