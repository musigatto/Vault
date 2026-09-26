---
type: note
module: "04"
lo: "14"
tags: [process, bestpractice, mod/04]
topic: "Considerations for Selection of Appropriate IDS/IPS Solutions"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Selecting Appropriate IDS/IPS Solutions (§4.14)

## Characteristics of a good IDS solution
- Runs **continuously with less human intervention**; monitors all suspicious host activity
- **Fault tolerant** — must not require reconfig/reboot after host failure; monitors itself
- **Resistant to subversion**, **not easily deceived**
- Capable of **halting/blocking attacks** from any application; alert via online/mobile/email per admin config
- **Information-gathering** capabilities → detect attack type, source, impact; gather **forensic evidence**
- **Fail-safe/hiding feature** in large orgs: create fake network to attract intruders, analyze attack possibilities, vulnerability analysis
- **File checker** detects file changes; reports every network activity (vulnerability analysis)
- Adapts to **dynamic/recursive system behavior** (different defense mechanisms per system)
- **Minimal overhead** on system/network

## Product selection criteria (compare tech types → choose per org needs)
Evaluation categories:
- **General requirements**
- **Required security capabilities**
- **Performance requirements**
- **Management requirements**
- **Lifecycle cost requirements**

### General requirements
- **System/network environments**: org size modifies number of IDS products; evaluate technical specs of IT environment + existing security protections; product must detect/log events of interest
- **Goals and objectives**: technical-, operational-, business-related; which threats protected against? monitor acceptable-use violations / non-security reasons?
- **Security and other IT policies**: policy goals, reasonable-use policies, violation consequences
- **External requirements**: security-specific requirements, security-audit requirements, system-accreditation requirements, law-enforcement/incident-investigation/incident-response requirements, independent evaluation process, cryptography requirements
- **Resource constraints**: budget (purchase/deploy/administer/maintain hardware+software+infrastructure); staff to monitor/maintain the IDS

### Security capability requirements
Product used in conjunction with other security controls — must offer:
- **Information gathering** (detection + incident analysis)
- **Logging** (analysis, alert validation, correlating logged events)
- **Detection** (identify threat events via different methodologies)
- **Prevention** (cater to future needs/situations)

### Performance requirements
- **NIDS**: ability to monitor/handle network traffic · **HIDS**: events/second
- Verify: tuning features (manual/automatic), processing capability + memory, ability to track multiple products/activities simultaneously, latency of event processing, delay in tracking an event, hardware models + OS configs, up-to-date test suites

### Management requirements
- Comply with org management policy; criteria: **interoperability, scalability, security**
- Design/implementation criteria (technology type, reliability); operation + maintenance (daily usage, updates); resources: **training, documentation, technical support**

### Lifecycle costs
- Must fit available budget; two categories:
- **Initial costs**: appliances/hardware tools, network equipment/components, software + licensing fees, installation, customization, training
  - Hardware/software deployment tools · installation/config (labor) · application customization (developers) · training & awareness
- **Maintenance costs**: staff wages, customization costs, maintenance contracts, technical support fees
  - **Labor** · **technical support** (third party) · professional services (vendors that don't provide IDS service)

## Cards
Q:: Good IDS characteristics?
A:: Continuous run, fault tolerant, subversion-resistant, minimal overhead, deviation detection, not easily deceived, tailored to system, copes with dynamic behavior.
#flashcard
Q:: Five IDS product selection categories?
A:: General requirements, security capabilities, performance, management, lifecycle cost.
#flashcard
Q:: IDS security capability requirements?
A:: Information gathering, logging, detection, prevention.
#flashcard
Q:: NIDS vs HIDS performance measure?
A:: NIDS = monitor/handle network traffic; HIDS = events processed per second.
#flashcard
Q:: Lifecycle cost categories?
A:: Initial (appliances, software/licensing, installation, customization, training) and maintenance (staff wages, customization, maintenance contracts, support).
#flashcard