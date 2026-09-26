---
type: note
module: "03"
lo: "07"
tags: [tool, protocol, concept, mod/03]
topic: "Security Platforms: Load Balancers, UTM, SIEM, NAC, VPN, SOAR"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-03]]

# Security Platforms — Load Balancer · UTM · SIEM · NAC · VPN · SOAR (§3.7) part b

## Load Balancer
- Physical item inserted before servers, controls server accesses (routes client requests to least-loaded / most-available server)
- Components (load balancer + server farm): server guard / dispatcher / virtual server / director · primary/secondary IPs · floating IP / NAT
- Setup: interim network found between servers + switches; can be NLB (network load balancing) or dedicated appliance
- Algorithms: **round-robin** · **least-connections** · **least-loaded** · work-request · resource-usage · arbitrary-assignment
- Tools: **Microsoft Network Load Balancing (NLB)** · **HAProxy** · **Apache mod_proxy_balancer** · **LVS** (Linux Virtual Server)

## UTM (Unified Threat Management)
- Single appliance/console: firewall, intrusion detection, anti-malware, spam filter, **load balancing, content filtering, DLP, VPN** in one
- Advantages: reduced complexity · simplicity · easy management · **low cost** (single console for whole network) · low maintenance · easy install/wiring · fully integrated
- Disadvantages: **single point-of-failure** · single point of compromise · **less specialization** (one console may miss features) · possible performance constraints (shared CPU time)
- Protects users from **blended threats** — evaluate/examine security apps + components through a single console
- Examples: Endian UTM (EFW) · Sophos UTM (firewall rules across destinations/sources/services, country blocking, IPS, flow-monitor app control) · Fortinet (endpoint→cloud, end-to-end) · WatchGuard (all-in-one monitoring/isolation) — UTM sits between Load Balancer / Network Firewall / Content Filter / Anti-virus / Anti-spam / VPN / IDS-IPS

## SIEM (Security Information and Event Management)
- Must-know use: collecting all external + internal data from devices → monitor + analyze → **correlate events to identify unusual/suspicious activity** on the IT infrastructure
- Actions: manages security easier, single console; detects what signature-based misses; **communicates/reconfigures firewall & IPS rules** to act on threats
- Example: **Splunk ES** — analytics-driven, automates collection/indexing/alerting on real-time machine data (structured or unstructured), ML/AI insights; faster response, end-to-end visibility, advanced detection/investigation, threat-intel decisions

## NAC (Network Access Control)
- Definition & goal: appliances/solutions restricting end-user connection **based on security policy**; often preinstalled agent inspects items + restricts where the device may connect
- What it does: authenticate users for network resources · identify devices/platforms/OSs · define devices' connection points · develop + apply security policies
- Keeps systems **without AV / intrusion prevention off the network**; per-user/per-system policies, define policies by **IP address**
- Detection checks: AV present+updated? configured firewall/IPS? OS updated? viruses present?
- Main actions: evaluate unauthorized users/devices/behaviors → give authorized entities access · identify users/devices + their security state · examine system integration vs security policies
- Pitfalls to check before implementing: does NAC authenticate users? how well implemented? device integration? end-user blocked check? (rectification plans needed)
- Cost-bearing resources to consider: **network infrastructure, security, human resources, operations, management** (policy priority, budget)
- Examples: ForeScout CounterACT™ (visibility of users/devices/OS/apps; discovery+classification then enforce compliance) · Extreme Control · Trustwave NAC (granular control; **BYOD** endpoints, stops malware spread) · Cisco NAC Appliance (manager+server; LANs, remote-access gateways, wireless APs; posture assessment incl. guest users)

## VPN (Virtual Private Network)
- Private network using public networks (internet / telephone lines) to give remote employees secured connections linked to the corporate network
- Security via tunneling protocols + encryption (data integrity + authentication); scalable for new clients, organizations, apps; virtual user↔public-network connection
- Encapsulation: packet wrapped in a **new packet with new header** inside a **tunnel**; de-encapsulated at tunnel endpoint → original forwarded
- Tunnel protocols operate at **layer 2 (data link) or layer 3 (network, OSI)**: IPsec · PPTP · L2TP · SSL
- Example: **OpenVPN** (uses TCP/UDP + TLS, e.g. 101.99.74.214:443; OpenVPN GUI) — TLS 1.2 tunnel with ECDHE-RSA-AES256-GCM-SHA38

## SOAR (Security Orchestration, Automation, and Response)
- Streamlines + automates security processes → improves security posture, responds/manages cybersecurity threats efficiently
- 3 interacting elements
  - **Security orchestration** — connects/integrates tools via integrations + APIs (endpoint protection, SIEM, UBA, vuln scanners, end-device security, firewalls, IDPS, external threat-intel); more data gathered ⇒ more threats found
  - **Security automation** — ingests + analyzes data; builds repeatable automated processes replacing manual (vuln scan, log analysis, auditing, ticket checking); prioritizes threats, recommends, auto-responds
  - **Security response** — unified dashboard for planning, monitoring, management, reporting of incident response; reporting, case management, threat-intel exchange
- Example: **Splunk SOAR** — orchestrates workflows, automates tasks in seconds (SOC), repeatable playbooks so analysts go proactive; dashboard (events resolved, playbooks, actions, FTE/time/dollars saved); codifies SOPs into reusable templates
- Distinguished from SIEM: SIEM correlates/analyzes events; SOAR connects automation to the tools to execute responses/playbooks

## Cards
Q:: Load balancer purpose + example algorithms?
A:: Routes client traffic to least-loaded/most-available server. Algorithms: round-robin, least-connections, least-loaded.
#flashcard
Q:: UTM biggest risks?
A:: Single point-of-failure + single point-of-compromise; one console = overall need, but less specialized.
#flashcard
Q:: How does SIEM act on detected threats?
A:: Correlates/analyzes events, then communicates with + reconfigures firewall and IPS rules to respond.
#flashcard
Q:: NAC main purpose?
A:: Restrict/allow end-user network access based on a security policy; blocks systems lacking AV/IPS.
#flashcard
Q:: VPN tunneling protocol layers?
A:: Layer 2 (data link) or layer 3 (network, OSI). Common: IPsec, PPTP, L2TP, SSL.
#flashcard
Q:: SOAR three elements?
A:: Orchestration (connect tools), Automation (replace manual tasks), Response (single dashboard IR actions).
#flashcard