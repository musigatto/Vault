---
type: note
module: "02"
lo: "06"
tags: [process, mod/02]
topic: "IT Asset Management (ITAM)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-02]]

# IT Asset Management (§2.6)

## Definition
- Tracking assets throughout **lifecycle, from initial discovery to final disposal**
- Assets: **hardware, software, licenses, or proprietary information**
- Develops/maintains **policies, standards, processes, metrics** per risk, control, governance, compliance, cost, performance objectives
- Security teams: identify/remove **rogue devices**, prevent unauthorized installations, detect missing assets, keep apps patched, full visibility of devices

## Advantages
- Thorough tracking of hardware/software assets (purchase date, product number, CPU/memory/speed/IP/disk specs)
- Compliance with **license agreements** (auto-detect installed software vs SLAs — avoid penalties)
- Assess software installations; remove unneeded licenses; track real usage
- Integrates **procurement + IT management** into unified dashboard (strategic planning, budget)
- Remove rogue devices
- Enhance employee productivity

## Components of ITAM
| Component | Content |
|---|---|
| **Financial data** | Cost of purchasing/operating, value generation, resale price; purchase date, depreciation, quantity, price |
| **Physical data** | Location + current usage status; in use vs out of commission (damage/malfunction) |
| **Contractual data** | Contract clauses company/vendor/purchaser: service levels, maintenance, license types, device quantities, pricing, contract durations |

## Types of ITAM
| Type | Scope |
|---|---|
| Physical/Hardware AM | IT hardware, inventory, tech products (monitors, hard drives, scanners); compatibility, storage, equipment orders |
| Software AM | Software needs + administration policies; license compliance, 3rd-party agreements, update frequency |
| Network AM | Network devices: **routers, firewalls, switches, WAPs**; inventory, configuration, performance |
| Digital AM | Digital data: **images, videos, documents, spreadsheets, financials, customer info** |
| Mobile Device Management | How employees use mobile devices on business network; app policies, password-protected org apps, data-access limits |
| Cloud AM | Oversight of cloud services (security + function); online servers, metadata, web storage, cloud security/compliance |

## ITAM process
1. **Asset Identification & Categorization** (first step; know what assets exist, where, how used)
   - Identification: discover + document physical (computers, servers, networking) + digital (licenses, certificates, data) assets → accurate inventory → maintenance, firmware-vuln remediation, up-to-date systems
   - Categorization groups by: **type · usage · location · owner/department · lifecycle stage · vendor/manufacturer · criticality · license type** (auto-sorted types, dynamic groups, or by IP). Example tool: **Lansweeper**
2. **Asset Tracking** — continuous monitoring with ITAM tool; real-time notifications (new installs, hardware removals, licensing status); details needed: name, serial, purchase date, **warranty**, license, **SLAs + user assignments**, physical condition; file-scanning rules (audio/video/docs; disk space); alerts for deletions
3. **Asset Maintenance** — regular maintenance (reactive for unexpected issues) + preventive; safeguards against downtime/breaches; **all activities logged into ITAM system** → track performance. (e.g., Microsoft Patch Tuesday audit in **Lansweeper**)

## ITAM tools
| Tool | Notes |
|---|---|
| **Lansweeper** | Discover assets without installing software; visibility into every device/user/software; NIST vulnerability info; diagramming |
| **Ivanti Neurons** | Consolidate IT asset data; track/configure/optimize/manage full lifecycle; barcode scanning; vendor mgmt; product catalog |
| **SolarWinds Service Desk** | Cloud ITAM; unified dashboard; automates risk detection; aligns assets with incidents; discovers current assets; centralized config overview |
| **ServiceNow** | End-to-end lifecycle for software licenses, hardware, cloud; mitigate compliance risk (unlicensed deployments, re-harvesting) |
| **IBM Maximo** | Enterprise asset management; analytics + IoT to improve availability, lifecycle; Maximo Scheduler; field tech access |
| **SyAM** | Centralized asset database; hardware/OS config, apps, location/function/last-used/user access |
| **AssetSonar** | Single source of truth; tracks custody/location/maintenance; agent-based scans; Google Workspace/Okta; license entitlements |
| **ManageEngine AssetExplorer** | Web-based; lifecycle planning→disposal; license compliance; purchase orders & contracts |

## Best practices
- **Establish policies & procedures**: asset standards · BYOD guidelines · security guidelines · software-licensing guidelines · configuration standards · service-dispatch/preventive-maintenance/support/escalation pairings · configuration-management (change control) · asset-disposal guidelines
- **Conduct regular internal audits** — reduce discrepancies, early-warning system, avoid penalties/fines
- **Use automated tools** — auto-detect hardware/software/network assets, optimize ROI
- **Establish centralized asset repository** — for hardware/software inventory; incident, service-level, configuration, problem management
- **Implement asset lifecycle management** — track/use to full capacity; expiry → purchase decisions; history + maintenance data (downtime, costs)
- **Optimize asset usage** — quantify unused hardware/software value; reduce waste/maintenance costs
- **Ensure compliance** — rules by authorities/government; licensing agreements; avoid penalties
- **Monitor security risks** — overview of all assets → reduce data risks; track assets vulnerable to hacking/theft
- **Document & track changes** — hours of use, location, modifications; notify on significant changes
- **Continuous improvement** — different scanning techniques, refresh DB; add new purchases/leases/assets from new facilities

## Cards
Q:: Three ITAM data components?
A:: Financial, physical, contractual data.
#flashcard

Q:: Six ITAM types?
A:: Physical/hardware, software, network, digital, mobile device, cloud asset management.
#flashcard

Q:: ITAM process phases?
A:: Identification & Categorization → Asset Tracking → Asset Maintenance.
#flashcard

Q:: Lansweeper discovery highlight?
A:: Network-wide asset discovery without installing agents/software on systems (works for IoT too).
#flashcard

Q:: Asset categorization criteria?
A:: Type · usage · location · owner/department · lifecycle stage · vendor/manufacturer · criticality · license type.
#flashcard