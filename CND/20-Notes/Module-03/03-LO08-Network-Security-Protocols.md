---
type: note
module: "03"
lo: "08"
tags: [protocol, crypto, mod/03]
topic: "Essential Network Security Protocols"
exam_weight: unknown
status: done
unresolved: [IPsec layer (module body classifies it at network layer with AH/ESP; one slide line says 'works at the application layer')]
---
[[MOC-Module-03]]

# Essential Network Security Protocols (§3.8)

Security protocols work at network, transport, application layers. RADIUS, TACACS+, Kerberos, PGP, S/MIME, S-HTTP, HTTPS, TLS, SSL, IPsec.

- **Transport layer:** SSL (client⇄server communication security)
- **Network layer:** IPsec (authenticates packets during transmission)
- **Application layer:** PGP (encryption/decryption), S/MIME (email security), Secure HTTP (wwW data), HTTPS (network data), Kerberos (client-server model), RADIUS (remote-access servers ⇄ central server), TACACS+ (client-server model)
- Also covered here: ICMP (resolve network communication problems), TCP (establishes/manages conversations), UDP (connectionless transport), SNMP (monitor/manage devices on LAN/WAN; components: **SNMP manager · SNMP agent · MIB**; standard language for routers/servers/printers ⇄ NMS)

## RADIUS
- Livingston Enterprises; centralized **AAA** for remote-access servers ⇄ central server; client-server, **application layer**, **UDP** or TCP transport; de-facto standard for remote user auth — RFC **2865** (auth) / **2866** (accounting)
- Auth methods: PAP, CHAP, EAP
- Components: access clients · access servers · RADIUS proxies · RADIUS servers · user account databases
- Messages = UDP, one message per UDP payload (header + attributes)
- Auth steps: client sends **access-request** → server compares vs DB, matches → **access-accept + access-challenge** (additional auth), else **access-reject** → client sends **accounting-request** (connection accepted / start / interim-update / stop → **accounting-response**)
- Packet types: `Access-Request (Username, Password)` · `Access-Accept / Access-Reject (UserService, FramedProtocol)` · `Access-Challenge (optional, ReplyMessage)` · Accounting-request / Accounting-response

## TACACS+
- Cisco, derived from TACACS; **performs AAA separately** (unlike RADIUS); primarily **device administration** (switches, routers, firewalls via centralized servers); encrypts the **entire** client⇄server communication incl. **username + password** (sniffing protection)
- Process: user requests connection → AAA client gets resource request → client sends REQUEST to AAA server (after auth already done) for service shell → server RESPONSE (pass/fail) → client grants/denies service shell
- Example auth: user initiates → router/user exchange auth params → router sends params to server → server REPLY

| | RADIUS | TACACS+ |
|---|---|---|
| AAA | Combines authentication + authorization | **Separates** auth / authz / accounting (more flexible) |
| Encryption | Encrypts only the **password** | Encrypts username **and** password |
| Authorization config | Each network device must contain authorization config | Central network device management |
| Transport | **UDP** connectionless (ports 1645/1646, 1812/1813) | **TCP** connection-oriented, port **49** |

## Kerberos
- Network authentication protocol; client-server model; **ticket** mechanism to prove identity on non-secure networks; protects vs **replay attacks and eavesdropping**; often uses public-key cryptography
- Steps: user sends credentials to **AS** → AS **hashes password**, verifies against **Active Directory** database → match ⇒ AS (with **TGS**) returns **TGS session key + Ticket-Granting Ticket (TGT)** → user sends TGT requesting **service ticket** from TGS → TGS validates TGT, grants service ticket (ticket + session key) → client sends service ticket to server; server decrypts with its key, client authenticated

## PGP
- Application-layer program; cryptographic privacy + authentication for network communication; encrypts/decrypts email, authenticates via digital signatures, encrypts stored files
- Flow: recipient public key encrypts → receiver decrypts with private key; message **compressed** (more security); one-time **session key** encrypts the message; session key encrypted with recipient's public key; both sent to recipient; recipient decrypts session key with private key, then the message
- Two versions: **RSA** · **Diffie-Hellman**
- Hash code from user's name + signature encrypts the sender's private key; receiver uses sender's public key to decrypt hash code

## S/MIME
- Application layer; digitally signed + encrypted email; security services: **authentication · message integrity · non-repudiation · privacy · data security**; uses **RSA** for encryption; needs a certificate from a CA; **different private keys for signature vs encryption**; enables mailbox security (network defenders enable S/MIME)
- Flow: Alice signs w/ her private key + encrypts (DES) w/ secret key → key encrypted (RSA) w/ Bob's public key → Bob decrypts secret key (RSA, private) → DES-decrypts → verifies signature/certificate
- PGP vs S/MIME (S/MIME v3 vs OpenPGP): msg format CMS vs PGP binary · cert X.509v3 vs PGP binary · symmetric TripleDES vs TripleDES (CBC) · signature RSA or Diffie-Hellman(X9.42)+DSS vs ElGamal+DSS · hash SHA-1 vs SHA-1 · signed-data CMS vs multipart/signed ASCII armor

## S-HTTP
- Application layer; encrypts **individual web messages** carried over HTTP (SSL instead secures the whole connection between two entities); alternative to HTTPS (SSL); used when the server requires user authentication; uses certificates; client can send a certificate to authenticate a user
- Note: not all web browsers and servers support S-HTTP

## HTTPS
- Secure communication over HTTP between two computers; connection encrypted via **TLS or SSL**; used in confidential online transactions; protects vs **man-in-the-middle** (encrypted channel)
- SSL advantages: encrypts confidential info during exchange · records certificate-owner details · CA checks owner when issuing certificate

## TLS
- Secure communication between client-server apps over the internet; prevents eavesdropping/tampering
- Properties: symmetric crypto (confidentiality/reliability client⇄server) · public-key crypto (authenticate applications) · auth codes maintain data reliability
- Two protocols: **TLS Record Protocol** (connection security via encryption) · **TLS Handshake Protocol** (server + client authentication before communication)

## SSL
- Developed by **Netscape**; uses **RSA asymmetric** encryption; needs reliable transport (**TCP**); application-layer protocols (HTTP, FTP, telnet) sit transparently above it; acts as **arbitrator between encryption algorithm and session key**; verifies destination server before data transfer; encrypts all application-protocol data
- Channel security: **private channel** (messages encrypted after handshake defines secret key) · **authenticated channel** (server always, client optional) · **reliable channel** (integrity check)
- Uses asymmetric + symmetric auth; public keys verify identities then symmetric keys enable communication; session IDs organize server/client states
- Handshake: ClientHello (SSL version, random data, encryption/key-exchange/compression/MAC algorithms, session ID) → server picks version + algorithms, sends ServerHello + Certificate → ServerHelloDone → client verifies cert, generates random **premaster secret** (encrypted with server's public key) → ClientKeyExchange → ChangeCipherSpec + Finished (hash of handshake) → server calculates hash, compares; match ⇒ key + cipher-suite negotiation succeeds; sends its own Finished

## IPsec
- Network-layer protocol for secure **IP-level** communication; encrypts + authenticates **each IP packet**; end-to-end security at the internet layer of the IP suite; supports **network-level peer authentication, data origin authentication, data integrity, confidentiality (encryption), replay protection**
- Applied in VPNs + remote user access; between hosts, security gateways, or gateway⇄host (side note: module body also contains one line saying it works at the application layer — see unresolved)
- Two services: **AH** (authentication of sender only) · **ESP** (sender authentication + data encryption)
- Deployment: LAN-internal IP ⇄ firewall (external IP) ⇄ Internet ⇄ firewall ⇄ LAN-internal IP (**IPsec tunnel**)

## Cards
Q:: RADIUS RFCs + transport?
A:: RFC 2865 (auth) / RFC 2866 (accounting); client-server on the application layer via UDP (or TCP) as transport; PAP/CHAP/EAP auth.
#flashcard
Q:: RADIUS vs TACACS+ encryption?
A:: RADIUS encrypts only the password (UDP); TACACS+ encrypts the whole session including username+password (TCP 49), AAA separated.
#flashcard
Q:: Kerberos main protection + identity proof?
A:: Protects against replay attacks and eavesdropping; proves identity on non-secure networks via tickets (TGT then service ticket).
#flashcard
Q:: PGP session key handling?
A:: One-time session key encrypts the message; the key itself is encrypted with the recipient's public key and sent alongside.
#flashcard
Q:: S/MIME cryptographic services?
A:: Authentication, message integrity, non-repudiation, privacy, data security (RSA-based, separate keys for signing and encryption).
#flashcard
Q:: SSL channel-security properties?
A:: Private (encrypted after handshake), authenticated (server always, client optional), reliable (integrity check).
#flashcard
Q:: IPsec services?
A:: AH = sender authentication only; ESP = sender authentication + data encryption; peer auth, data origin auth, integrity, confidentiality, replay protection.
#flashcard