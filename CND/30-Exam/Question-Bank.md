---
type: exam
module: "bank"
tags: [exam, mod/01]
topic: "CND Question Bank — 100 Single-Best-Answer"
exam_weight: high
status: draft
unresolved:
  - "Blueprint per-module weights not in courseware → equal 5/module used until weights are sourced."
---
# Question Bank

> [!info] Rules
> 100 single-best-answer items, answerable strictly from PDF content. Distribution: equal 5 per module (weights unknown). Answers + justifications live in [[Answer-Key]].

## Index by module
| Module | Items | Key |
|--------|-------|-----|
| 01 — Network Attack and Defense Strategies | Q001–Q005 | [[Answer-Key#Module 01]] |
| 02 — Administrative Network Security | Q006–Q010 | [[Answer-Key#Module 02]] |
| 03 — Technical Network Security | Q011–Q015 | [[Answer-Key#Module 03]] |
| 04 — Network Perimeter Security | Q016–Q020 | [[Answer-Key#Module 04]] |

## Module 01 — Network Attack and Defense Strategies (Q001–Q005)

**Q001.** Which of the following best represents how risk is calculated in network security?
- A) Risk = Asset + Threat + Vulnerability
- B) Risk = Motive + Method + Vulnerability
- C) Risk = Asset + Motive + TTPs
- D) Risk = Threat + Vulnerability + Motive

**Q002.** An attacker floods a DHCP server with a large number of DHCP requests carrying spoofed MAC addresses, exhausting the available IP address pool. Which type of attack is this, and which tool is commonly used?
- A) DHCP spoofing, using a rogue DHCP server
- B) DHCP starvation, using Gobbler
- C) ARP poisoning, using Cain & Abel
- D) MAC flooding, using SMAC

**Q003.** A web application uses SSL/TLS only for the login page, and a packet sniffer is used to intercept the session cookie afterwards. Which session hijacking method is used?
- A) Session fixation
- B) Cookie theft by malware
- C) Session side-jacking
- D) CSRF injection

**Q004.** Which security approach uses methods such as IDS, SIMS, TRS, and IPS to address attacks that the preventive approach failed to avert?
- A) Preventive
- B) Reactive
- C) Retrospective
- D) Proactive

**Q005.** According to the courseware, the 11 tactic categories in MITRE ATT&CK for Enterprise are derived from which sources?
- A) The Reconnaissance, Weaponization, and Delivery stages of the Cyber Kill Chain
- B) The Exploit, Control, Maintain, and Execute stages of the Cyber Kill Chain
- C) The five phases of the CEH hacking methodology
- D) The OWASP Top 10 risk list

## Module 02 — Administrative Network Security (Q006–Q010)

**Q006.** A security consultant is building an organization's compliance program. Which of the following represents the correct hierarchy as given in the courseware?
- A) Standards → Policies → Frameworks → Procedures
- B) Frameworks → Policies → Standards → Procedures
- C) Policies → Frameworks → Guidelines → Standards
- D) Frameworks → Guidelines → Policies → Standards

**Q007.** Which of the following is responsible for determining the purposes and means of processing personal data, while the other handles data on its behalf, under the GDPR?
- A) Data controller vs. data processor
- B) Data owner vs. data custodian
- C) Information owner vs. system admin
- D) DPO vs. DPO assistant

**Q008.** An organization wants to block all Internet services by default and only enable each service that the network defender individually deems safe and necessary, while logging everything. Which Internet access policy type is this?
- A) Promiscuous
- B) Permissive
- C) Paranoid
- D) Prudent

**Q009.** During the first phase of IT asset management, the team discovers and documents all assets and then groups them. Which grouping basis is used?
- A) By KPI and SLA thresholds
- B) By type, usage, location, owner/department, lifecycle stage, criticality, and license type
- C) By threat severity and vulnerability score
- D) By procurement cost and depreciation

**Q010.** Which access rule applies when a user holds the "Secret" data classification level, according to the courseware?
- A) Access to Secret, Confidential, Restricted, and Unclassified (but not Top Secret)
- B) Access to all levels including Top Secret
- C) Access limited to Secret only
- D) Access to Unclassified only unless explicitly granted

## Module 03 — Technical Network Security (Q011–Q015)

**Q011.** An enterprise deploys honeypots to study attacker behavior in isolation. The network defenders discover exactly how attacks unfold step by step in order to develop new countermeasures. Which honeypot type is this?
- A) Production honeypot
- B) Low-interaction honeypot
- C) Research honeypot
- D) Pure honeypot

**Q012.** Which NAC detection check is NOT among those the courseware lists for admission?
- A) Search for an antivirus program and check whether it has been updated
- B) Check if the end system has a configured firewall or intrusion prevention software
- C) Verify that the end user's device is on the latest Wi-Fi password
- D) Search for viruses and check whether the operating system has been updated

**Q013.** A technician must centrally administer switches, routers, and firewalls while encrypting the entire client–server communication including the username and password. Which AAA protocol fits?
- A) RADIUS over UDP ports 1812/1813
- B) TACACS+ over TCP port 49
- C) Kerberos as a Ticket-Granting Service
- D) S/MME with a CA-issued certificate

**Q014.** Which IPsec service authenticates the sender but does NOT encrypt the data?
- A) Authentication Header (AH)
- B) Encapsulating Security Payload (ESP)
- C) Tunnel mode only
- D) The TLS Record Protocol

**Q015.** A network defender wants a single security console that provides firewall, IDS, anti-malware, spam filtering, content filtering, DLP, and VPN, while accepting the risk of a single point of failure. Which solution is described?
- A) Load balancer with round-robin algorithm
- B) SIEM with correlated events
- C) UTM (Unified Threat Management)
- D) Network Access Control appliance

## Module 04 — Network Perimeter Security (Q016–Q020)

**Q016.** A firewall checks each packet's header against a rule set and makes its decision independently at the network level of the OSI model, without tracking session state. Which firewall technology is this?
- A) Application-level gateway
- B) Packet filtering firewall
- C) Circuit-level gateway
- D) Stateful multilayer inspection firewall

**Q017.** An IDS sensor is placed outside the perimeter firewall. The team tunes it to the least-sensitive attacks so it logs attack attempts only, without raising alerts. Which deployment location is this?
- A) L1 — outside the perimeter firewall
- B) L2 — behind the external firewall in the DMZ
- C) L3 — major network backbone
- D) L4 — critical subnets

**Q018.** An IDS cannot detect intrusions when they are encapsulated in encrypted traffic because encrypted payloads cannot be matched to signatures. What does the courseware recommend to fix this?
- A) Place the IDS behind a VPN termination with SSL encryption
- B) Increase the IDS sensitivity threshold
- C) Disable stateful protocol analysis on the sensor
- D) Deploy the sensor outside the firewall in stealth mode

**Q019.** A network defender wants to allow only a single MAC address per port on an access switch. Which port-security method is this?
- A) Dynamic — MAC held in CAM
- B) Sticky — MAC saved across reboot
- C) Static — only a single MAC allowed
- D) AAA-based port authentication

**Q020.** In a Software-Defined Perimeter, which component is the authentication point that evaluates the policy, grants access to the client, and determines which gateways the client may communicate with?
- A) SDP gateway (accepting host)
- B) SDP client (initiating host)
- C) Single-Packet Authorization service
- D) SDP controller

## Draft scaffold
- Modules 02–20: one 5-item block each, generated from the corresponding module OCR content.