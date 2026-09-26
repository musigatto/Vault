---
type: note
module: "04"
lo: "08"
tags: [process, bestpractice, policy, mod/04]
topic: "Firewall Administration Activities"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Firewall Administration (§4.8)

Administration = managing firewall devices/software to maintain security. Includes: platform access, OS builds, failover, logging, security incidents, backups + assessment/modification of policies, vulnerability identification, threat detection, countermeasures.

## Accessing the firewall platform
- Threats arise from exploiting **remote management resources** (e.g., graphical management interface) → use **encryption + strong user authentication**
- GUI management usually uses **SSL over HTTP (HTTPS)**; internal auth = unique user ID + password; some firewalls support token-based services (RADIUS)

## Building the OS platform for the firewall
- Use systems tailored for strong security applications (e.g., **bastion host**)
- Install all **security patches before** installing the firewall; **disable unused network services, protocols, applications, and user accounts** (must not affect OS function)

## Firewall failover strategies
- Balance security on firewall failure: **heartbeat-based services** shift all inbound/outbound traffic to the backup firewall when a failover event triggers (includes back-end/customized network interfaces)
- Reduces network-failure chances; primary + backup firewalls kept behind **a single MAC address** for seamless function

## Firewall logging
- All firewalls have default logging; use a **centralized logging service** (e.g., UNIX syslog) providing log examination + parsing; store logs centrally for security using few examination packages; firewalls without syslog support keep internal logging

## Firewall backups
- Use **"day zero" or full backups, not incremental**, immediately before production release
- Because firewall access control doesn't permit centralized backup, firewalls have **in-built backup facilities**
- Windows: back up critical file systems to external devices; **UNIX: `/var`** filesystem/subdirectories need write access (system logs + spool dirs)

## Security incidents
- Firewalls **correlate events** passing through (especially network attacks); **synchronize with NTP** for effective event correlation
- On incident: temporarily **disable remote access + revoke user authentication** until controlled
- Incident levels: **minor** (basic network probes, lower severity, often ignored) · **medium** (attempts unauthorized access) · **high-end** (attacker succeeds; restricts resource availability)
- Event-correlation uses time synchronization to **roll back the firewall state to a unique state** and reconstruct incident phases

## System administration (supporting)
- Standardize OSes ready for updates/fixes; centralized system administration; examine firewall↔system communication path for config faults; decide the right firewall type for the org

## Deny unauthorized public network access
- Unauthorized access leads to data/service manipulation + DoS; enforce user access restrictions + security controls for granting permissions
- Use **SSL + HTTPS** when accessing corporate resources over public networks (only encrypted info passes, consistent with firewall policy)
- **Scan regularly for open ports** (e.g., **Nmap**) and disable them; control remotely accessible resources

## Deny unauthorized access inside the network
- Prevents running malicious programs / installing suspect software:
  - Prohibit **plug-and-play devices** (virus-infected flash drives)
  - Restrict remote use of corporate resources from public networks (internet cafés, hotels, free Wi-Fi) that bypass the perimeter firewall
  - **Educate on social engineering** (credential/identity theft → network attacks)
  - Trained admins provide firewall instructions; updated internet security solutions stop email virus spread
  - Provide access only to required docs/files; carefully structure account rights; user training

## Restricting a client's access to an external host
- Clients must **not have direct access** to external hosts — all access through the firewall (acts as **proxy server** for high-level application connections; a single firewall = packet filtering at application level + proxy server at domain level)
- Vulnerable external hosts gather client info (IPs, security type/level, server locations, remote-access credentials); remote-access tools (e.g., GoToMyPC) have risks: password sniffing, packet stealing, IP spoofing; dial-through can open security holes
- Policy controls: allow only internal IPs through the firewall · block traffic containing private addresses · block all outbound VLAN workgroup traffic · block broadcast traffic + traffic from servers needing no external connectivity

## Cards
Q:: Firewall remote management protection?
A:: Encryption + strong user auth; HTTPS (SSL over HTTP) GUI; unique user IDs/passwords, token-based RADIUS.
#flashcard
Q:: Failover mechanism?
A:: Heartbeat-based services shift traffic to backup firewall; primary+backup behind a single MAC address.
#flashcard
Q:: Firewall backup policy?
A:: Full 'day zero' backups (not incremental) before production release; in-built backup facilities; UNIX /var holds logs+spools.
#flashcard
Q:: On security incident, first actions?
A:: Temporarily disable remote access + revoke user authentication; correlate events via NTP-synchronized firewall.
#flashcard
Q:: Client access to external hosts?
A:: Never direct — through firewall as proxy; a firewall combines application-level packet filtering + domain-level proxy.
#flashcard