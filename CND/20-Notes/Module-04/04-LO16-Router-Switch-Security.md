---
type: note
module: "04"
lo: "16"
tags: [bestpractice, process, mod/04]
topic: "Router & Switch Security Measures, Recommendations, Best Practices"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Router and Switch Security (§4.16)

## Why secure a router
- Routers are the **main gateway to the network** and **not designed as security devices**; vulnerable to attacks from inside + outside
- Hardening prevents attackers from:
  - Gaining information about the network
  - Disabling routers / disrupting the network
  - Reconfiguring routers
  - Using routers for internal or external attacks
  - Rerouting network traffic

## Router security measures
- Implement written, approved, distributed **router policy** (baseline)
- **Change the default password** (leaving it = handing attackers the key)
- **Enable + encrypt console password**; set maximum failed-login attempts; password encryption
- **Restrict console access**; limit access restriction; implement ACL to limit traffic to required ports/protocols
- **Disable unnecessary** interfaces/services and management protocols
- **Deactivate IP directed broadcasts** (else spoofed ICMP ECHO to a broadcast address hits all hosts)
- **Disable IP source routing** (else attacker identifies packet path, can sniff); disable **ARP + proxy ARP**
- **Deactivate HTTP configuration** (sends clear-text traffic); configure required services properly (e.g., DNS)
- Create **ingress/egress address-filtering policies**; identify need for packet filtering; check ports/protocols
- Configure **warning banner**; block **ICMP ping requests**; configure **QoS**; use **NTP** for accurate time
- **Enable logging**; logs checked/reviewed/archived per policy (log review = attack intel + router/network status)
- Return on OS version: keep **OS up-to-date**
- **Maintain physical security** (improper placement → sniffing + direct access)

## Why switch security is important
- Layer-2 (switch) vulnerabilities are often neglected; misconfigured switches vulnerable to **MAC-based attacks: MAC flooding, DHCP spoofing, ARP spoofing**
- Configure switch security at levels: **OS · password management · network services · port security · system availability · VLANs · spanning tree protocol · ACLs · logging/debugging · AAA**

## Switch security measures
- Enforce **strong password management**; strong SSH password; **enable SSH**, disable Telnet
- Implement **ACL**s + VLAN ACLs; **private VLANs**; control VLAN count per trunk
- Enable **DHCP snooping**; **Dynamic ARP Inspection (DAI)**
- **Port security** — limit MAC addresses per port (three methods):
  - **Statically**: only a single MAC allowed per port
  - **Dynamically**: present by default in content-addressable memory
  - **Sticky**: MAC assigned to a specific port (lost if not saved during reboot)
- Implement **port-based authentication** (802.1X-style); set privilege on **vty lines**
- Disable **auto-trunking**; disable **DTP** messages; disable **CDP on non-management interfaces**
- Enable **STP root guard + BPDU guard**
- Ensure **physical security**; deactivate unused ports → assign unused VLAN number
- Time-out sessions + user access rights; keep config file offline + control access; review switch security logs; AAA for local + remote access

## Cards
Q:: Why harden routers?
A:: Prevent info disclosure, router disablement/reconfiguration, internal/external attacks via router, traffic rerouting.
#flashcard
Q:: Three key router disables?
A:: IP directed broadcasts, IP source routing, HTTP configuration (clear text); plus ARP/proxy ARP.
#flashcard
Q:: Switch port-security MAC methods?
A:: Static (single MAC), dynamic (CAM default), sticky (port-assigned MAC; lost if not saved over reboot).
#flashcard
Q:: Switch layer-2 attack types?
A:: MAC flooding, DHCP spoofing, ARP spoofing.
#flashcard
Q:: Switch hardening controls?
A:: SSH, ACLs/VLAN ACLs, DHCP snooping, DAI, port security, port auth, STP root/BPDU guards, disable DTP/CDP/auto-trunking, AAA.
#flashcard