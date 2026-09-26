---
type: note
module: "03"
lo: "07"
tags: [tool, mod/03]
topic: "Essential Network Security Solutions — Appliances & Analyzers"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-03]]

# Essential Network Security Solutions (§3.7) — part a

## Firewall
- Software/hardware/both **separating protected internal network from unprotected public network**; monitors + filters in/out traffic; prevents unauthorized access
- Principles: allow traffic meeting criteria; deny traffic not matching; criteria = configured rules (type of traffic, source/destination addresses, protocols, ports)
- Typical use: protect private apps/services · restrict private hosts' access to public services · **NAT** (private IPs, share single internet connection)
- Example: **pfSense** (open-source gateway firewall, FreeBSD-based)

## Intrusion Detection / Prevention (IDS/IPS)
- **IDPS** inspects all inbound/outbound traffic for suspicious patterns → identify, log, report, attempt to block
- **IPS** extends IDS (in-line): send alarms, drop malicious packets, reset connections, block malicious source IPs, defragment streams, fix CRC errors, reduce TCP sequencing issues, clean unneeded transport/network-layer options
- **IDS** sits off to the side (network tap), monitors but **cannot act directly**: alerts, logs, pages admin, re-configures to mitigate
- **How an IDS works:** signature-file comparison → anomaly detection (statistical compare vs normal traffic; finds new attacks but **false positives**) → **stateful protocol analysis** (vendor-defined malicious profiles) → if matched across stages: drop packet, disconnect source IP, log; else pass to switch
- IDS features: evaluate system/network activity · analyze vulnerabilities · measure system/file reliability · identify possible attacks · monitor irregular activity · evaluate policy violations
- vs firewall: firewall prevents but doesn't alert; IDS monitors, identifies, and alarms
- Pros: continuous tracking, extra security layer, incident logs · Cons: not always detecting, needs trained staff, false alarms
- **Tools:**
  - **Snort** — open-source NIDS: real-time traffic analysis + packet logging; detects buffer overflows, stealth port scans, CGI attacks, SMB probes, OS fingerprinting; usable as packet sniffer (tcpdump), packet logger, or NIDS/IPS
  - **Suricata** — network IDS/IPS + security monitoring engine; highly scalable (load-balances across configured processors); identifies thousands of files
  - **OSSEC** — open-source **host-based** IDS: file-integrity monitoring, log monitoring, root check, process monitoring; alerts via logs/email; exports to SIEM via **syslog**

## Honeypot
- Decoy system to attract/trap attackers; no authorized activity, no production value — any traffic = probe/attack
- Setup: log-only system · old unpatched OS (e.g., NT 4 + IIS 4; use standard IDS to log hacks) or special software simulating success without real access · prevent attacker from deleting honeypot data
- Intent: track attacker activities → build countermeasures · collect **forensic information**
- Types (deployment): **Production** (with production servers, looks real → identify attackers) · **Research** (evaluate attacker steps precisely → develop countermeasures; track stolen data)
- Types (design): **Pure** (complete tracking, trap on link) · **Low-interaction** (fakes frequently-requested services; single machine w/ VMs) · **High-interaction** (real production systems on VMs; highly secure, examines every step; costly)
- Benefits: simplicity · detects inside attacks (insiders) · reduces false positives · identifies false negatives · small high-value data collection · captures all IP activity (IPv6) · incident response + warning system · misleads attackers
- Tools: **KFSensor** (simulates vulnerable services/trojans) · **HoneyBot** (medium-interaction honeypot for Windows; early-warning IDS)

## Proxy Server
- Dedicated computer/software virtually **between client and actual server**; sentinel between internal network and open internet; intercepts + filters requests; serves client requests on behalf of real servers (hides them); additional defense layer vs OS/web-server attacks; deployed to intercept malicious/offensive content, viruses hidden in client requests
- Uses: firewall + local-network protection · anonymous surfing (limited) · content filtering (ads/unsuitable) · hacking-attack protection
- Workflow: user → proxy receives request → sends to actual server on user's behalf → mediates response
- Benefits: security protector between clients & servers · privacy of client devices · browsing speed · advanced logging · control restricted services · hide internal IP · fewer cookie modifications / malware · filters external-site requests · auth before handling requests
- Attackers also use proxies to hide on the internet
- Tools: **Squid Proxy** (caching proxy; HTTP/HTTPS/FTP; access controls; GNU GPL) · **Protoport Proxy Chain** (multi-country proxy chains, anonymous surfing) · **ProxyCap** (redirects connections through proxies; supports SSH as proxy) · **CCProxy** (Windows; broadband/DSL/dial-up/optical/satellite/ISDN/DDN; HTTP, mail, FTP, SOCKS, news, telnet, HTTPS)

## Network Protocol Analyzer (packet analyzer / sniffer)
- Hardware/software capturing + analyzing packets; complements firewall/AV/spyware; puts NIC in **promiscuous mode**; timing chart of packet flow; snapshot of network traffic
- Features/benefits: network + packet data analysis · threat alarms · bandwidth analysis · troubleshooting/debugging (perf issues, protocol errors, DHCP failures, virtual-network misrouting) · ID implementation/config errors · improve firewall/IDS performance · analyze DoS attacks · application statistics (HTTP transaction time, DNS, top talkers/listeners) · forensic records · query specific data strings · untrusted-content details · monitor users · debug protocol apps
- Tools: **Wireshark** (deep packet display) · **Capsa** (LAN/WLAN; real-time capture, 24x7 monitoring, protocol analysis, expert diagnosis) · **PRTG** (unlimited NetFlow/flow sensors)

## Web Content Filter
- Software/hardware blocking harmful sites/undesirable content; protects vs **malware, phishing, pharming**; filters by **keywords, URLs, contextual analysis**; beyond firewall+AV
- Implementation types: browser-based · e-mail filters · client-side · content-limited · network-based · search-engine filters
- Advantages: control productivity (block non-work/social sites) · high-level protection (malware) · restrict liability (external file sharing) · flexibility (change blocked sites anytime) · faster internet (bandwidth control)
- Tools: **OpenDNS** (3 predefined filtering levels + custom categories/allow-list) · **Netsentron** (schools/businesses; blocks porn/offensive/unapproved sites; remote file work) · **Net Nanny** (parental: Windows/Mac/Android/iPhone/iPod/iPad; blocks porn, masks profanity, time limits, alerts/reports, per-user profiles)

## Cards
Q:: IDS vs IPS placement?
A:: IPS is in-line (blocks/drops/corrects); IDS sits off-side via a network tap (monitors, cannot act directly).
#flashcard

Q:: Three detection methods in an IDS?
A:: Signature-based → anomaly-based (statistical) → stateful protocol analysis.
#flashcard

Q:: Honeypot deployment types?
A:: Production (in production network, looks real) vs Research (analyze attacker steps for countermeasures).
#flashcard

Q:: Honeypot design types?
A:: Pure · low-interaction (fake common services) · high-interaction (real systems via VM, costly).
#flashcard

Q:: Proxy server main function?
A:: Intercepts/filters client requests and serves them on behalf of real servers, hiding internal IPs; extra defense layer.
#flashcard

Q:: Protocol analyzer NIC mode?
A:: Promiscuous mode to capture all packets on the network.
#flashcard

Q:: Web content filter protections?
A:: Malware, phishing, pharming; filters by keywords, URLs, contextual analysis.
#flashcard