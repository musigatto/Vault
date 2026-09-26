---
type: note
module: "01"
lo: "08"
tags: [threat, mod/01]
topic: "Wireless Network-specific Attack Techniques"
exam_weight: unknown
status: done
unresolved: []
---
[[MOC-Module-01]]

# Wireless Network Attacks (§1.8)

## Access-control / association attacks
- **Wardriving**: detect WLANs via probe requests or listening to web beacons; tools **KisMAC · NetStumbler · WaveStumbler**
- **Client misassociation**: client associates with a rogue AP outside legitimate network (signals travel through walls); enables access-control attacks
- **Unauthorized association**: attacker connects to network without authorization (prevention depends on association technique)
- **Honeypot AP**: attacker spoofs SSID of legit AP, places fake AP with high-gain antennas; harvests client + network info for MITM / wireless DoS
- **Rogue AP**: insecure/fake AP inside firewall to create backdoor; types — wireless router on "trusted" interface · wireless router on "untrusted" interface · wireless card installed in a device on trusted LAN · enabling wireless on a trusted-LAN device
- **Misconfigured AP**: misconfigured networking device = open gateway; unnoticed when devices are centrally managed
- **Ad Hoc connection**: attacker connects host to insecure client (USB adapter/wireless card) to attack client or impair AP security

## Identity / crypto attacks
- **AP MAC spoofing**: reconfigure MAC to appear as authorized AP; tools **changemac.sh · SMAC · Wicontrol**
- **WEP cracking**: capture traffic + brute force or **FMS (Fluhrer-Mantin-Shamir)** cryptanalysis → recover WEP key
- **WPA-PSK cracking**: sniff auth packets (packet analyzers) → brute force the pre-shared key
- **RADIUS replay**: capture **RADIUS Access-Accept/Reject** and replay — authenticate to client without valid credentials
- **MAC spoofing (client)**: spoof victim laptop's MAC; tool **Cain & Abel** (ARP poisoning) → AP forwards victim's traffic to attacker

## Availability / integrity attacks
- **DoS**: flood victim with nonlegitimate requests/traffic
- **MITM with evil twin AP**: fraud AP that appears legitimate for intercepting TCP sessions / SSL-SSH tunnels
- **Fragmentation attack**: split one packet into very small fragments; delivery via **Ping of Death** (fragmented ICMP exceeding IP datagram size) · **Tiny Fragment** (small fragments reveal TCP header, defeats filtering rules)
- **Jamming signal**: overwhelm spectrum w/ malicious traffic → DoS; specialized hardware; not easily noticeable; some jam by holding devices' transmissions until signal subsides

## Mnemonic
> [!tip] Mnemonic
> Rogue AP 4 ways: trusted iface · untrusted iface · wireless card add · enable wireless on already-trusted device.

## Cards
Q:: Wardriving tools?
A:: KisMAC, NetStumbler, WaveStumbler.
#flashcard

Q:: What is an evil twin AP?
A:: A fraudulent access point that appears legitimate, used for MITM to intercept TCP sessions or SSL/SSH tunnels.
#flashcard

Q:: Two fragmentation attack forms?
A:: Ping of Death (oversized fragmented ICMP) and Tiny Fragment (small fragments leak TCP header, evade filtering).
#flashcard