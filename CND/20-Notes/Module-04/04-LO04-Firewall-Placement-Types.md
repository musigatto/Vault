---
type: note
module: "04"
lo: "04"
tags: [concept, mod/04]
topic: "Hardware / Software / Host / Network / Internal / External Firewalls"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Firewall Placement Types (§4.4)

Three comparisons: hardware vs software · host vs network · external vs internal. **Recommended: combine both sides of each pairing.**

## Hardware vs Software
- **Hardware**: dedicated standalone device (or built into a broadband router); perimeter placement; effective with little config; uses **packet filtering** (reads header → compare vs rules → forward/drop); per-system or single-interface network
  - Examples: Cisco ASA · FortiGate · Cisco/SonicWall/Netgear/ProSafe/D-Link
  - ☑ own OS reduces risk, better control · faster responses, more traffic · separate component → easier mgmt/moves/reconfig
  - ☒ more expensive · hard to implement/configure · space + physical cabling · difficult to upgrade
- **Software**: program on a computer, sits between apps and OS networking; implant in the application/network path; analyzes data flow vs ruleset; intercepts all requests; user-defined controls, privacy/web/content filtering
  - Examples: Windows Firewall · Iptables · UFW · Norton/McAfee/Kaspersky
  - ☑ cheaper · ideal for home/mobile users · easy to configure/reconfigure
  - ☒ consumes system resources (slows PC) · hard to uninstall · poor for fast-response environments

## Host vs Network-based
- **Host-based**: **software**, filters in/out traffic of the individual computer it's installed on; part of the OS (Windows Firewall, Iptables, UFW)
  - Analysis levels: packet analysis (network + transport layers) → checks MAC/IP/source/dest port → stateful filter → application-layer validation
  - ☑ security regardless of location · internal security vs internal attacks · basic hardware/software setup · good for individuals/small business · VMs/apps carry their firewall across cloud moves · per-device custom rules
  - ☒ not for larger networks · attacker with host access can disable FW/install malware undetected · replace/scale if bandwidth grows (costly per-server install/maintenance) · dedicated IT per device
- **Network-based**: **hardware** filtering internal-LAN in/out traffic; functions at network level → **first line of defense at the network perimeter**; routes traffic to proxy servers which manage transmissions
  - Examples: pfSense · Smoothwall · Cisco SonicWall · Netgear · ProSafe · D-Link
  - ☑ no per-server install/maintenance · greater security at the barrier · scalable bandwidth · high availability (uptime) · limited workforce · suits SMEs/large networks
  - ☒ ignores app/vulns on systems/VMs · no protection for host-to-host in same VLAN · skilled setup · incorrect proxy maintenance hurts performance
- **Real world**: combine both — breach of network-level security still faces each host-based firewall (for big orgs with sensitive data/compliance needs)

## External vs Internal
- **External**: limit access between protected network and public network; validate in/out traffic, translate between internal/public IPs; provide access control + protection for **DMZ systems** (no new external→internal connections); protect **legacy devices that lack firewalls** — placed between the legacy device and the LAN (even if compromised, FW detects + stops spread + blocks its Internet contact)
  - Examples: Floodgate Defender (Icon Labs) · Firebox M440 (WatchGuard, switch-oriented)
  - ☑ independent of, and updatable apart from legacy devices · control open-connection systems (browsers) · quick install/easy config · can replace legacy switch connection with FW connection
- **Internal** (internal network segmentation firewalls): protect one segment from others; contain malicious activity within one segment; sit between two org segments (or two orgs sharing a network); enforce stateful policies instead of switches
  - ☑ isolate/secure critical servers from internal + external users · block host-to-host comms, isolate malicious segments · how have visibility · segment/monitor large L2 networks · restrict remote users to few segments · contain + monitor VPN traffic
  - ☒ need additional subnets · problematic for moving systems · expensive devices

## Cards
Q:: Hardware vs software firewall cost/placement?
A:: Hardware: dedicated perimeter device (Cisco ASA/FortiGate), pricier, faster; software: per-host program (Windows FW/iptables/UFW), cheap, resource-heavy.
#flashcard
Q:: Host vs network-based firewall example each?
A:: Host: Windows Firewall/iptables/UFW (software, per device); network: pfSense/SmoothWall/Cisco SonicWall (hardware, perimeter).
#flashcard
Q:: Host-based firewall analysis order?
A:: Packet inspection (L3/L4, MAC/IP/ports) → stateful filter validation → application-layer validation.
#flashcard
Q:: External firewall primary role?
A:: Limit protected↔public traffic, protect DMZ + legacy devices without firewalls; block new external→internal connections.
#flashcard
Q:: Internal firewalls sit where?
A:: Between two segments of the same org (or two orgs on the same network); segment + monitor, contain malicious spread.
#flashcard