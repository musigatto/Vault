---
type: note
module: "04"
lo: "12"
tags: [bestpractice, process, mod/04]
topic: "Effective IDS Deployment (Network & Host)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Deploying Network- and Host-Based IDS (§4.12)

## Staged IDS deployment
- Understand network infrastructure + org security policies **before** deploying
- Use a **staged deployment**: initial deployment requires high maintenance; next stages add more — discover exactly where security (sensors) is needed; gives admins time to get used to the technology, evaluate/investigate IDS alerts and logs
- Deploy IDS across the whole network only when personnel can handle alerts from different places; monitoring/maintenance effort scales with org size

## Deploying NIDS — sensor locations
- Deploy the **IDS management console first**, then sensors incrementally; account for differences in traffic, logging, reporting, and alerts per new sensor
- Place sensors at: **internet gateways · between LAN connections · remote-access (dial-up) servers · VPN devices (internal↔external LAN) · between switch-separated subnets · either side of the firewall**
- Inside vs outside firewall: placing sensors **inside the firewall is more secure** (an outside sensor becomes an attack focus); more secure still = **behind the firewall in the DMZ**
- If protecting web/mail servers: place a sensor **inside the firewall** on the segment connecting firewall↔internal network (firewall stops most attacks; IDS catches what passes)
- 4 deployment locations:
  - **L1 — outside the perimeter firewall**: detects inbound attacks (and some outbound); tuned to **least-sensitive** attacks (few false alarms); **logs attack attempts only, no alerts**
  - **L2 — behind external firewall / in DMZ**: secures perimeter + identifies firewall-bypassing attacks; covers web/FTP servers; detects **low-to-moderate** impact attacks; monitors outbound too
  - **L3 — major network backbones / internal network**: detects attacks bypassing internal firewall; inbound + outbound; tuned to **medium-to-high impact**
  - **L4 — critical subnets / sensitive hosts**: focuses on specific critical systems; inbound + outbound; **high-impact attacks**
- Multiple hosts protected from a single location → can customize NIDS to secure the entire network

## Deploying HIDS
- Frontline per-host security — **install + configure on each critical system**; consider on every host
- Initial deployment on **critical servers only**; deploy management console before adding hosts; scale to all hosts **only if** you comfortably manage critical ones (reduces alert-complexity)
- Large-scale HIDS = many false alarms, expensive, requires additional software + maintenance per host

## Cards
Q:: IDS staged deployment benefit?
A:: Discovers where security/sensors are needed, lets admins adapt; initial stage requires highest maintenance.
#flashcard
Q:: NIDS sensor order of deployment?
A:: IDS management console first, then sensors incrementally at choke points/gateways/DMZ.
#flashcard
Q:: Outside-firewall sensor tuning (L1)?
A:: Least-sensitive attacks, logs attempts only (no alerts) to avoid false alarms.
#flashcard
Q:: DMZ sensor (L2) coverage?
A:: Perimeter + firewall-bypass detection; web/FTP servers; low-moderate impact attacks; also outbound.
#flashcard
Q:: HIDS deployment approach?
A:: Critical servers first → management console → then every host, only if manageable (costly, many false alarms).
#flashcard