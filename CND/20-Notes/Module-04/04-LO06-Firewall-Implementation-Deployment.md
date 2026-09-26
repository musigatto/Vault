---
type: note
module: "04"
lo: "06"
tags: [process, tool, policy, mod/04]
topic: "Firewall Implementation and Deployment Process"
exam_weight: unknown
status: done
unresolved:
  - "OCRed firewall log screenshots (pfSense/Smoothwall/ManageEngine) are pedagogic; only tool names + roles are asserted."
---
[[MOC-Module-04]]

# Firewall Implementation & Deployment (§4.6)

Five phases: **Planning → Configuring → Testing → Deploying → Managing & Maintaining** (minimizes unforeseen issues, catches pitfalls early).

## 1. Planning
- **Assess the need**: conduct a **security risk assessment** first → identify threats + vulnerabilities · evaluate threat impact (CIA) · identify security controls → build org security policy from results → decide whether a firewall is needed to enforce it
- Things to consider:
  - Define the **technical objectives** (drives firewall selection)
  - Fit of firewall vs **existing network topology** (perimeter vs LAN isolation; how much traffic; how many interfaces) → drives topology choice
  - **Type of traffic to inspect** → drives firewall technology (packet filter = simple rules; stateful = tracks TCP 3-way handshake; app proxy = breaks client/server connection + stateful)
  - **Hardware vs software** solution (physical = easy install, pricier; software = tricky install, often less secure)
  - **OS** choice (Windows, UNIX…) — admins must be able to work with it
- Points of consideration:
  - Don't build a firewall from non-firewall gear (e.g. router) — overload, no intended security
  - Don't overload the firewall with non-security services (web/email server)
  - Use firewalls at **multiple levels** (perimeter, department, individual host); keep sensitive systems behind internal firewalls (internal threats matter too)
  - Do extensive market research on each model's capabilities + limitations; prefer a policy that requires firewall use
- Purchase factors: **Management** (encrypted mgmt, HTTPS/SSH, restrict remote mgmt to certain interfaces/source IPs, centralized mgmt from same vendor) · **Performance** (throughput, connections, per-connection time, latency, bottleneck resistance, failover + load balancing) · **Integration** (hardware needs, compatibility with other security devices, log system compatibility) · **Security capabilities** (what to secure, technology support, extra features like IDS/VPN/content filtering) · **Physical requirements** (rack/shelf space, backup power, air conditioning) · **Personnel** (trained network defenders before deployment) · **Future needs** (IPv6, bandwidth, compliance)

## 2. Configuring
- **Hardware & software install**: install OS + patches + vendor updates (both FW types); remote-management software; restrict access to the firewall to responsible personnel; **disable SNMP** management services; configure admin accounts (separate admin account if supported)
- **Policies**: define how the firewall is setup/operated/updated/maintained, its scope, services offered, supported communications
  - Policy-creation steps: 1 Identify important network apps (traffic, bandwidth, connection type) → 2 Identify app-related vulnerabilities/impact → 3 Cost-benefit analysis to secure apps → 4 **Create a network application traffic matrix** → 5 Build the **ruleset from the traffic matrix**
  - Checklist: verify policies meet org needs; create one or more inbound rules for voluntary inbound traffic
- **Periodic policy review**: ~80% of installed firewalls are misconfigured; review + update policies **every six months**; formally update ruleset when firewall app upgrades; audit installs/systems regularly; scheduled reviews include audits + vuln assessments of production, and backup-infrastructure tests
- **Rules & rulesets**:
  - Rule = characteristics to inspect (protocol type, source/dest address, source/dest port) → action; three basic actions: **Allow · Block · Ask** (or Allow / Allow if secured via IPsec / Block)
  - Ruleset = rules that establish firewall functionality; contains packet source/dest address + traffic type; filter at **outer edge and inside** the network; alert on user login/ruleset changes
  - **Blacklist**: allow all, deny listed (easier internal protection) · **Whitelist**: deny all, allow only listed (safer)
  - Examples: allow dest 10.1.1.0 with source port >1023; explicit allow/deny verified vs **implicit deny** at end of access list (blocks everything not explicitly allowed)
  - Build tricks: edit rules offline · reload rulesets from scratch · **use IP addresses never hostnames**
  - Synchronize identical rules across multiple firewalls; rules apply to inbound + outbound across LAN/wireless/remote access
- **Logging & alerting**: store + synchronize logs to a centralized log-management system (case-by-case logging); read-only user accounts for auditing; alarm systems notify defenders on: firewall-rule manipulation attempts, reboots/disk shortages, system status changes
  - Log contents: port scans, unauthorized connection attempts, failed auth, abnormal protocols, virus attacks, activity from compromised systems, boundary threats (trace attack source)
  - Huge volumes (≥10,000 events/sec) need specialized collection/analysis software; keep **logs on a centralized secure server** (or attacker may delete footprints); log types: virus logs, attacks, audit trail, event logs, network traffic, VPN establishment; benefits: admin/troubleshooting, baseline comparison, clearer system view, forensic analysis
  - **Firewall analyzers**: ManageEngine Firewall Analyzer (browser-based, collects/correlates/analyzes Cisco, CheckPoint, WatchGuard, NetScreen, Fortinet FWs/VPNs/proxies) · SolarWinds Firewall Analyzer (analyzes logs, automates threat remediation)
- **Integrating into architecture**: configure the boundary network router to handle firewall addressing; integrate with internal/external firewall + DMZ layout

## 3. Testing
- Test on a **test network replicating production**, not production itself; evaluates: **connectivity · ruleset · application compatibility · management · logging · performance (simulated live traffic) · security of implementation (vulnerability assessment) · component interoperability · policy synchronization**
- Steps: develop test cases → derive test packets → send to firewall → examine performance
- Failure causes: incorrect test cases, wrong security-policy implementation in rules, implementation errors, packet loss, buggy test environment, faulty hardware

## 4. Deploying
- Notify affected users/owners; deploy per org policy; **add the firewall policy to the overall security policy**; integrate with interacting network elements; handle firewall addressing in the network infrastructure
- Phased deployment for multiple firewalls resolves conflicting-policy issues; reconfigure the outside network device; update all hosts; alert users; finally allow private traffic through

## 5. Managing & Maintaining
- Apply latest patches/updates; maintain architecture/policies/software; **update policy on new threats**; review policy periodically (remove unneeded rules, add new); monitor + log all alerts; back up rulesets + policies regularly; update rulesets per security requirements; perform log analysis
- Scope includes: extending life, keeping it operating, confirming protective coverage, improving performance, checking updates, verifying components

## Cards
Q:: Firewall deployment phases?
A:: Planning → Configuring → Testing → Deploying → Managing & Maintaining.
#flashcard
Q:: Firewall policy creation steps?
A:: 1 key apps → 2 vulnerabilities → 3 cost-benefit → 4 app traffic matrix → 5 ruleset from matrix.
#flashcard
Q:: Ruleset review cadence + implicit rule?
A:: Review/update every 6 months; implicit deny blocks all traffic not explicitly allowed.
#flashcard
Q:: Blacklist vs whitelist ruleset?
A:: Blacklist: allow all, deny listed. Whitelist: deny all, allow only listed (stricter).
#flashcard
Q:: Firewall log placement?
A:: Centralized secure server/syslog; huge volumes (≥10k events/s) need specialized software.
#flashcard
Q:: Test-network evaluation attributes?
A:: Connectivity, ruleset, app compatibility, management, logging, performance, security, component interoperability, policy sync.
#flashcard
Q:: Maintenance activities?
A:: Patches, policy updates on new threats, 6-month review, log analysis, regular ruleset/policy backups.
#flashcard