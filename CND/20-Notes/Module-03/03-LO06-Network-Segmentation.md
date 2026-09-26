---
type: note
module: "03"
lo: "06"
tags: [process, mod/03]
topic: "Network Segmentation"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-03]]

# Network Segmentation (§3.6)

## Concept
- Split network into smaller segments; separate groups of systems/applications from each other (physical or virtual)
- Overcomes **flat-network** drawback (all resources on same network → any perimeter breach = easy access to everything; detective tools focus outside, not inside)
- In segmented network, non-interacting groups live on different segments; even a penetrated perimeter can't cross segments

## Security benefits
| Benefit | Effect |
|---|---|
| Improved security | Isolates traffic; prevents access between segments |
| Better access control | Allows access to specific network resources |
| Improved monitoring | Event logging/monitoring; deny internal connections; detect malicious actions |
| Improved performance | Fewer hosts/subnet; less local traffic; broadcast isolated to local subnet |
| Better containment | Limits network issues to the local subnet |

## Working principle (example topology)
- Separation of servers: **one firewall, two DMZ zones (L3 subnet isolated), internal zone**
- Internet-facing servers (web, email) separated from non-internet-facing (application/database) — compromise of one reduces damage
- Traffic rules: **bidirectional** internal↔**DMZ2** (backups/authentication via Active Directory); **one-way** internal→**DMZ1**; firewall allows internet→DMZ1 on selected ports (**80, 25, 443**…), closes others (TCP/UDP), blocks internet→DMZ2 entirely
- Internal-zone workstations reach the internet **via HTTP proxy in DMZ1** (internal zone isolated from internet); DMZ1 compromise doesn't reach internal zone (one-way rule)
- Optional add-on: **cloud web filtering** (WebTitan, TitanHQ, SolarWinds MSP) to block malicious sites

## DMZ (Demilitarized Zone)
- Small network between private network and outside public network; prevents direct outsider access to internal servers — an additional security layer
- Contains externally-accessible servers: **web, email, DNS, FTP**
- Configurations: **single firewall (three-legged)** — 3 interfaces (ISP exterior, exterior, interior); single point of failure, must manage all DMZ traffic · **dual firewall** — first allows only sanitized traffic into DMZ, second double-checks (**most secure + most complex**)
- Both internal and external networks can connect to DMZ; **DMZ hosts cannot initiate connections into the internal network**
- Advantages: high-level LAN protection · increased control of resources · multi-platform software/hardware layers · flexibility for internet apps (email, web)

## Best practices
1. **Follow least privilege** — only necessary connections/access between segments; minimize attack surface & lateral movement
2. **Limit third-party access** — remote access is a key vulnerability
3. **Audit & monitor** — proactive gap identification, incident response
4. **Make legitimate paths easier** than illegitimate ones (plot user access routes)
5. **Combine similar network resources** into individual segments/DBs — consistent policies, less overhead
6. **Do not over-segment** — too many segments → complexity, harder to manage
7. **Visualize the network** — segments/interconnections/traffic flows; holistic view of who needs what

> [!info] Segmentation = one layer of defense-in-depth; complement with strong authentication, encryption, IDS, vulnerability assessments.

## Cards
Q:: Segmentation benefits?
A:: Improved security, better access control, improved monitoring, improved performance, better containment.
#flashcard

Q:: DMZ hosting rules?
A:: Web/email/DNS/FTP servers; internal + external can connect to DMZ; DMZ hosts cannot connect into internal network.
#flashcard

Q:: DMZ firewall designs?
A:: Single (three-legged, single point of failure) vs dual firewall (most secure, most complex).
#flashcard

Q:: Segmentation best practices?
A:: Least privilege · limit third-party access · audit & monitor · easy legitimate paths · combine similar resources · don't over-segment · visualize.
#flashcard