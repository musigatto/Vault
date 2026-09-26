---
type: note
module: "04"
lo: "07"
tags: [bestpractice, process, policy, mod/04]
topic: "Secure Firewall Implementation Best Practices"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Secure Firewall Implementation (§4.7)

## Best practices (hardening)
- **Filter unused and vulnerable ports** — layered filters (simple packet → complex app filters) for defense-in-depth
- **Run firewall under a unique user ID**, not admin/root; roles define administrator access type
- **First determine traffic needed by approved apps → then set ruleset to deny-all and allow only needed services** (improves performance by only granting important apps)
- **Remote syslog server**: date/time/timezone must match network config (NTP keeps all device clocks synced); protect the syslog server from malicious users
- **Monitor firewall logs at regular intervals** (websites, files, email content); log `allow` actions for insight and `deny` actions to identify threats
- **Backups**: monthly (≈at least), on secondary storage for legal/future reference; backup before + after rule changes (verify config usable); use firewall scheduling
- **Audit at least once per year** to evaluate implemented standards; account for every change
- **Default `deny` for inbound** with explicit `allow` rules — deny at ruleset end catches wrong-zone traffic; cover every combination
- Prioritize rules per org security requirements; **granular rules**, group similar rules, avoid needless nesting of rule objects; standard naming conventions; same ruleset for similar policies within a group
- **Secure email**: create a separate email network zone firewalled from DMZ + internal network; place email + webmail servers there (allows secure email access through the firewall)
- **Rule lifecycle**: add expiration dates to temporary rules, review for cleanup
- **Test firewall policies before implementing** (assess performance, traffic, other devices)
- **Firewall audits** identify policy-violation activities; **upgrade quickly to latest patches**; remove firewall rule base regularly (better security/performance/efficiency)
- Restrict unauthorized config modification (permission-based); only skilled personnel administer
- Filter correct source/destination packets; **change passwords every 6 months**; keep config simple + review periodically
- Internal attacks: firewall can't stop them — use policies restricting external devices + monitoring software for suspicious internal activity

## Recommendations (change management)
- Notify the security policy administrator on firewall changes + **document rules added/changed** (who to contact per rule) → easier troubleshooting, fewer service disruptions
- Generate analysis reports to evaluate access rules; eliminate unnecessary rules; implement a consistent **workflow** for the change process (identify risks, fix config errors before change)

## Do's and Don'ts
- **Do**: implement a strong firewall · limit apps running on it · control physical access · evaluate firewall capabilities · consider workflow integration · review/refine policies · incorporate trustmarks · take regular backups of ruleset + config · ensure IDPS capabilities (vs DoS), SSL encryption uses, proper hardware
- **Don't**: overlook scalability · rely on packet filtering alone · be unsympathetic to hardware needs · cut back on additional security · implement without SSL encryption · use underpowered hardware · allow **telnet access** through the firewall · allow **direct connections between internal clients and outside services**

## Cards
Q:: Firewall log backup cadence + purpose?
A:: Monthly to secondary storage; backup before/after rule changes; for legal/future reference after incidents.
#flashcard
Q:: Default inbound rule posture?
A:: Default 'deny' inbound with explicit 'allow' rules; implicit deny at end of ruleset blocks everything not allowed.
#flashcard
Q:: Secure email access design?
A:: Separate email network zone firewalled from DMZ + internal network; email + webmail servers placed in it.
#flashcard
Q:: Rule lifecycle management?
A:: Add expiration dates to temporary rules, review for cleanup; test policies before implementing.
#flashcard
Q:: Firewall audit frequency + password policy?
A:: Audits at least once a year; change firewall passwords regularly (≈ every 6 months).
#flashcard
Q:: Key firewall don'ts?
A:: No telnet access through FW, no direct internal-client↔outside-service connections, don't rely on packet filtering alone, don't skip SSL.
#flashcard