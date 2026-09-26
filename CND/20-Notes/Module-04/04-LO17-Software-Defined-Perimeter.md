---
type: note
module: "04"
lo: "17"
tags: [concept, process, tool, mod/04]
topic: "Zero-Trust Security with Software-Defined Perimeter (SDP)"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-04]]

# Zero-Trust Model via Software-Defined Perimeter (§4.17)

## Why SDP
- Dynamic, scalable, distributed multi-cloud environments → **traditional boundaries gone**; perimeter-based approach insufficient (not identity-centric; anyone can access resources; devices inside perimeter raise vulnerabilities; no fine-grained user access control, traffic visibility, Wi-Fi segmentation)
- Orgs shift to **zero-trust**; SDP implements it by **hiding the underlying architecture** + **least-privilege access control** based on policies; reduces attack surface to **zero** by single customized micro-segmented **1:1 connection** user↔resource

## Six traditional-security drawbacks SDP defeats
1. **Outside-only attacks**: external users authenticated once → full resource access, insider threats ignored. SDP = **"Never trust, always verify"**; external AND internal users both authenticated+authorized; insider restricted to a small data slice; access limited to business-function resources
2. **Static firewalls**: allow/deny specific IPs+ports; granting one IP = everyone; no per-user limits. SDP = **dynamic logical firewall**, **one rule: deny all connections**; adhd/removes policy per authorized user → **prevents lateral movement**
3. **Traditional VPN wide access**: trust-based network-centric; credential theft + excessive access; not cloud-friendly; lacks segmentation/visibility. SDP = zero-trust secure remote access; **detaches application access from network access**; fine-grained segments user↔app; **MFA** before access; blocks ports, encrypts traffic
4. **Lacks identity-centric model**: broad access, host-limited controls, no fine-grained control; NSGs can't identify users, need frequent updates. SDP = **identity-centric** dynamic security; micro-segmentation + fine-grained access; **makes resources invisible → prevents DDoS**; protects against server scanning, DoS, SQLi, OS/app exploits, MITM, PtH, PtT
5. **Fails vs lateral movement**: compromise one host → move freely. SDP authenticates+authorizes **user and device** before app access; encrypted **mutual TLS tunnel** per app (other apps can't reuse tunnel); dynamic firewall rules tether users to devices
6. **Traditional connectivity model less effective**: connect → credentials → authenticate; open to DoS, brute-force, server exploits, session hijacking, lateral movement, APT. SDP connectivity = **connection-based, not IP-based**; "need-to-know model"

## What is SDP
- SDP = **"Black Cloud"** — identity-centric security framework by the **Cloud Security Alliance (CSA)**; only authorized users; 1:1 connection; endpoints authenticate+authorize **before** app access; connections encrypted; need-to-know model verifies device + identity
- **Three pillars**: Zero trust (micro-segmentation + least privilege) · Identity-centric (identity, not IP) · Built for the cloud (cloud networks, scalable security)
- Features: software-defined (no physical/virtual appliances) · micro-segmented least-privileged app access · **reverses the TCP process** (SDP: authenticate&authorize first, then connect; TCP connects, authenticates, then data) · security layers protect resources · dynamic firewall (only authenticated users) · hides info/infra → **low + high volume DDoS protection** · connection- (not IP-) based security · flexible fine-grained policy · removes VLAN broad access · bidirectional trust (client↔SDP and app↔SDP) then authentication then connect

## SDP applications
- **Enterprise application isolation** (hide high-value apps → no lateral movement) · **private/hybrid cloud** (maximize flexibility/elasticity, obscure public-cloud instances) · **SaaS** (safeguard hosts+connecting users) · **IaaS** (SDP-as-a-Service: agility + cost savings, less exposure) · **PaaS** (minimize network-based attacks) · **cloud-based VDI** (simpler user interaction + granular access) · **IoT** (obscure backend servers/interactions → security + uptime)

## Deployment models (clients/servers/gateways)
- **Client-to-Gateway**: servers behind accepting host as gateway; minimizes lateral movement; on Internet separates protected server from unauthorized (DDoS, SQLi, XSS, CSRF)
- **Client-to-Server**: same, but protected server runs the software (choice depends on topology — load balancing, server elasticity)
- **Server-to-Server**: for server-to-server communication; initiating vs accepting SDP host (e.g., REST caller vs REST service); reduces service load + attack count
- **Client-to-Server-to-Client**: peer-to-peer (IP telephony, video conferencing, chat); obscures client IPs
- **Client-to-Gateway-to-Client**: gateway hidden in perimeter; variation of client-to-server-to-client; peer-to-peer access policies
- **Gateway-to-Gateway**: for certain IoT environments; gateway hidden in perimeter

## Architecture & components
- Three components:
  - **Client (initiating host)**: runs on every user device; communicates with controller to connect to gateway; may be queried for hardware/software inventory
  - **Controller**: authentication point evaluating policy, granting access; determines which client↔gateway pairs may communicate; sends info to external auth services (attestation, geo-location, identity)
  - **Gateway (accepting host)**: safeguards resources; only communicates at controller's request; decrypts tunneled traffic → protected resources
- Client generates **HMAC-based one-time password** via **Single-Packet Authorization (SPA)** as first packet for setup (client→gateway + gateway→controller); invalid packets rejected → safer deployment, minimizes DDoS impact

## Workflow (Figure 4.4)
1. Controllers go online → connect/authenticate to PKI, MFA, device fingerprinting services
2. Gateways come online, connect+authenticate to controller (never talk to clients directly)
3. Client connects + authenticates to controller
4. Controller determines authorized gateways for client
5. Controller instructs gateway to communicate with client + enforce encryption policies
6. Controller sends client the gateway list + optional encryption policies
7. Client starts **mutual VPN** to authorized gateway (control + data channels)

## Advantages vs traditional NAC
- **Reduced attack surface**: fine-grained per-user/per-app control; conceal unauthorized apps/ports; simple secure third-party access; VPN replaced; automatic infra adjustments; flexible anomaly response (vs quarantine)
- **Cloud adoption**: policy-based dynamic server access; auto-detect new IaaS/cloud servers; unified control of IaaS + physical + private cloud (VLANs can't extend to IaaS)
- **BYOD**: dynamic-attribute device+user validation; identity-system integration (vs 802.1X); fine-grained user control (vs coarse VLAN)
- **Streamlined compliance**: complete visibility of user history + access permissions (not just IP); descriptive-policy segmentation; reduced audit scope (vs SIEM consolidation + all-or-nothing VLAN policies)

## SDP tools
- **OPSWAT SDP**: cloud-based; "verify first, connect second" zero-trust (vs connect-then-authenticate); mTLS within + beyond perimeter; protects vs credential theft, connection hijacking, data loss, DDoS, MITM; least-privileged app-session model
- Others: Open Source SDP (Waverley Labs) · Absolute ZTNA (risk/compliance context) · Perimeter81 (mTLS, segmentation) · Cisco Software-Defined Access (SDA, zero-trust workplace + IoT) · NetMotion SDP · AppGate SDP · GoodAccess · Wandera (zero-day blocking, cloud SDP per-app isolated connections)

## Cards
Q:: SDP name + founder?
A:: "Black Cloud", identity-centric security framework by the Cloud Security Alliance (CSA).
#flashcard
Q:: Three SDP pillars?
A:: Zero trust (micro-segmentation, least privilege), identity-centric (identity not IP), built for the cloud (scalable).
#flashcard
Q:: How SDP defeats static firewalls?
A:: Dynamic logical firewall with one rule — deny all connections; rules added/removed per authorized user; prevents lateral movement.
#flashcard
Q:: SDP reverse of TCP?
A:: SDP authenticates/authorizes first then connects; TCP connects, authenticates, then passes data.
#flashcard
Q:: SDP three components?
A:: Client (initiating host), controller (auth + policy), gateway (accepting host, controller-directed).
#flashcard
Q:: SPA in SDP?
A:: Single-Packet Authorization — client sends HMAC-based one-time password packet as first packet; invalid packets rejected (minimizes DDoS impact).
#flashcard
Q:: SDP workflow steps?
A:: Controllers online → gateways online+authenticate → client authenticates → controller picks authorized gateways → instructs gateway → sends list to client → mutual VPN established.
#flashcard
Q:: SDP deployment models?
A:: Client-to-gateway, client-to-server, server-to-server, client-to-server-to-client, client-to-gateway-to-client, gateway-to-gateway.
#flashcard
Q:: SDP vs traditional NAC (examples)?
A:: Fine-grained per-user/app control vs all-or-nothing VLAN; VPN replaced vs VPN required; dynamic attr + identity integration vs 802.1X; reduced audit scope vs SIEM consolidation.
#flashcard