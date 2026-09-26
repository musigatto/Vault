---
type: note
module: "04"
lo: "03"
tags: [concept, mod/04]
topic: "Firewall Topologies"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Firewall Topologies (§4.3)

Three architectures: **Bastion Host · Screened Subnet · Multi-homed Firewall**.

## Bastion Host
- Computer system designed/configured to protect network resources; **mediator between inside and outside network**; platform for an application-level or circuit-level gateway; requires extra authentication for proxy services
- Firewall has **two interfaces**: public (→ Internet) + private (→ intranet); filters all in/out traffic
- Used by orgs with a **simple network that offers no public services**; with two firewalls, bastion host sits inside them or on the public side of the DMZ; examples: mail, DNS, FTP servers
- Selection: single layer of protection (network can fall if penetrated); suffices for corporate web-surfing networks; **not enough for web hosting / email-server protection**

## Screened Subnet (DMZ)
- Aka **"triple-homed firewall"**; single firewall with **three interfaces** (Internet / DMZ / intranet)
- DMZ (additional zone) = hosts offering **public services**; public zone connects directly to Internet (no org-controlled hosts); private zone = systems Internet users shouldn't access
- Two screening routers: perimeter↔internal network and perimeter↔external network; to reach the internal network the attacker must pass **both routers**
- Main advantage: **separates DMZ and Internet from the intranet** — even if firewall is compromised, intranet is not directly reachable; more secure
- Selection: ideal for orgs **hosting a website or email server**

## Multi-homed Firewall
- **Two or more networks**; more than three interfaces; further subdivides systems by security objectives; **different security policy per interface**
- Users access only presentation servers → middleware servers → data servers (defense layers)
- Increases IP-network efficiency/reliability; duplicates firewall functions in one box; replaces IP router (packets not forwarded at IP layer — the host processes them)
- **Dual-homed host**: related concept, two NICs (untrusted external + trusted internal); **no direct routing from untrusted to trusted** — firewall acts as intermediary
- Selection: orgs with **two or more network zones** (DMZ + trusted + untrusted); protects trusted network even if DMZ is compromised; DMZ rules laxer than private-network rules

## Choosing a topology
- Bastion host → simple network, no public services
- Screened subnet → org offers public services
- Multi-homed → different zones by security objectives
- Place a **separate firewall for each isolated zone** based on security demand

## Cards
Q:: Screened subnet alias + structure?
A:: "Triple-homed firewall" (single FW, 3 interfaces: Internet/DMZ/intranet); DMZ hosts public services; compromises FW can't reach intranet.
#flashcard
Q:: Dual-homed host key property?
A:: Two NICs (untrusted + trusted); no direct routing between them — firewall is the intermediary.
#flashcard
Q:: Topology for a simple network with no public services?
A:: Bastion host (single layer of protection; fine for corporate surfing, not web/email hosting).
#flashcard
Q:: Topology when two or more network zones exist?
A:: Multi-homed firewall (per-interface security policies; trusted network stays safe if DMZ breached).
#flashcard