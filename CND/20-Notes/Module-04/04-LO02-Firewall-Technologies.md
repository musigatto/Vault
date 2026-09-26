---
type: note
module: "04"
lo: "02"
tags: [concept, port, mod/04]
topic: "Firewall Technologies and OSI Layers"
exam_weight: unknown
status: done
unresolved:
  - "Table 4.1 pairing (VPN/packet filtering/NAT/stateful at layers) is OCR-garbled; only clean text retained."
---
[[MOC-Module-04]]

# Firewall Technologies (§4.2)

Emphasis: per-layer filtering depth, per-technique pros/cons.

## Types
- **Packet filtering** (network layer, usually part of a router)
- **Circuit-level gateway** (session layer)
- **Application-level gateway / proxy** (application layer)
- **Stateful multilayer inspection**
- **VPN** · **NAT** · **Application proxy** · **Next-generation firewall (NGFW)** · **Cloud firewall**

## Packet Filtering Firewall
- Works at **network layer** (OSI) / IP layer (TCP/IP); each packet compared to a ruleset (source/dest IP, port, protocol, TCP code bits, direction, interface) → drop / forward / reject-with-message
- Unknown traffic allowed **only up to level 2** of the network stack
- Traditional decisions based on: source IP, dest IP, source TCP/UDP port, dest port, **TCP code bits (SYN/ACK)**, protocol, direction, interface
- 3 config rules: (1) accept only safe, drop rest · (2) drop only confirmed-unsafe · (3) no rule → user decides
- Checks packets against **bypass table** for established connections
- ☑ **Low cost, low impact on performance**; routers support it ☒ Low-level security; bypassable via **packet spoofing** (crafted/replaced headers)

## Circuit-Level Gateway
- Works at **session layer** (TCP layer of TCP/IP); monitors **TCP handshake** to judge session legitimacy; not standalone — coordinates with packet filter + application proxy
- Unknown traffic allowed up to **level 3**; packets appear to originate from the gateway (hides private network); inexpensive
- Adv: hides private-network data · easy to implement · no individual-packet filtering
- Dis: can't scan active content · **only handles TCP connections**

## Application-Level Gateway (Proxy)
- Works at **application layer**; filters by app (e.g. browser), protocol (e.g. FTP), or combination; filters app-specific commands (HTTP `POST`, `GET`)
- Unknown traffic allowed only up to the **top** of the network stack; no proxy ⇒ no access for that service; can act as **web proxy** blocking FTP, gopher, Telnet
- Client/server never talk directly — proxy renews connections; commonly a **caching proxy** (frequent content cached → avoids repeat server requests)

## Stateful Multilayer Inspection
- **Combines** packet filter + circuit-level + application-level aspects: filters at network layer, judges session legitimacy, evaluates packet content at application layer
- Uses algorithms (not proxies); remembers prior packets → informs future decisions; **tracks/logs slots & translations**; drops non-compliant packets at each layer (network → TCP session → application)
- ☑ high security, better performance, transparent ☒ **expensive, needs competent personnel**
- Example: **Cisco Adaptive Security Appliance (ASA)** contains stateful firewalls

## Application Proxy
- Proxy-server-style: filters connections per service/protocol (an FTP proxy only passes FTP; all else blocked); runs on firewall host (**dual-homed or bastion host**)
- **Transparency** key advantage: user thinks they talk directly to real server; real server thinks it talks to the user
- Adv: effective logging (understands app protocols) · caching reduces network load · user-level authentication · protects weak/faulty IP implementations (generates new IP packets)
- Dis: lags behind non-proxy services until proxy software exists · each service may need separate servers · may require client/application/procedure changes

## NAT
- Separates IP addresses into two sets (internal/external); modifies packets with the router (source address on outbound, destination on inbound); hides internal network layout; **forces connections through a choke point**; limits public IP consumption; blocks outside-originated connections
- Translation modes: one-for-one fixed mapping (slowest, no savings) · dynamic external address without port change (limits concurrent hosts) · fixed internal→external + **port mapping** (many internal → same external) · **dynamic address+port pair per connection (most efficient)**

## VPN (as firewall tech)
- Private network built over public networks; **encapsulation + encryption**; creates virtual point-to-point connections; only the device running VPN software can access it
- Principles (over Internet): encrypt all traffic → check integrity → encapsulate → reverse encapsulation → check integrity → decrypt
- Adv: hides flow, encryption against snooping · remote access with outside-attack defense
- Dis: user on public network still vulnerable to attacks on the destination network

## NGFW
- **Third-generation** firewall tech; moves beyond port/protocol inspection; inspects traffic by **packet content** at layer 7 plus layers 3–4 packet filtering and proxying
- Capabilities: deep packet inspection (DPI) · encrypted-traffic inspection · QoS/bandwidth · **threat-intelligence integration** · integrated IPS · advanced threat protection · application control · antivirus inspection
- Features: app awareness/control · user-based auth · malware protection · stateful inspection · integrated IPS · identity awareness · bridged/routed modes · external intelligence sources
- Adv: app-level security (IDS/IPS) · single console · **multilayered protection layers 2–7** · simplified infrastructure · consistent throughput (no speed loss with more protocols/devices) · bundled AV/ransomware/spam/endpoint security · **role-based access** via identity detection

## Cloud Firewall
- Works like a traditional firewall but **hosted on the cloud**; aka **FaaS (firewall as a service)**; physical barrier between cloud platform/infrastructure/apps; protects on-site infrastructure
- Types: **SaaS firewalls** (like on-prem/software firewall but deployed from cloud, protects org network + users) · **NGFWs in virtual datacenters** (PaaS/IaaS protection; firewall app on the virtual server safeguards cloud app data flow)
- Benefits: scalability (no on-prem install/maintenance) · availability (provider infrastructure support) · extensibility (deploy anywhere with secure channel) · migration security (filters internet, virtual networks, tenants, virtual DCs) · secure-access parity with on-prem · identity (granular visibility into filtering tools) · performance management (insight, utilization, settings, logging)

## Cards
Q:: Packet-filtering firewall layer + bypass vector?
A:: Network layer; evaluates headers (IP/ports/protocol/TCP bits); bypassable via packet spoofing.
#flashcard
Q:: Circuit-level gateway layer + limitation?
A:: Session layer; validates TCP handshake; hides private network; can only handle TCP, no content scanning.
#flashcard
Q:: Application-level gateway filtering?
A:: Application layer: per app/protocol (e.g., web proxy blocks FTP/Telnet), filters HTTP GET/POST commands.
#flashcard
Q:: Stateful multilayer inspection?
A:: Combines packet + session + application checks; tracks slots/translations; expensive, needs skilled staff.
#flashcard
Q:: NAT translation most efficient mode?
A:: Dynamic address+port pair allocated per inbound connection (best external-address use).
#flashcard
Q:: NGFW = generation + extra layer?
A:: Third-generation; traditional L3–L4 + application layer 7 (DPI, encrypted-traffic inspection, integrated IPS, threat intel).
#flashcard
Q:: Cloud firewall alias + types?
A:: FaaS (firewall as a service); types: SaaS firewalls, NGFWs in virtual datacenters (PaaS/IaaS).
#flashcard