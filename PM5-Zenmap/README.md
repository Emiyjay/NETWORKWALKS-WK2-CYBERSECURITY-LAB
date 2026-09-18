# W2-PM5 — Zenmap Network Scanning

The active Windows Wi-Fi adapter was identified as:

- IPv4: 10.70.201.145
- Subnet mask: 255.255.255.0
- Gateway: 10.70.201.139

Therefore the local subnet used for the practical was 10.70.201.0/24.

Zenmap configuration:
- Target: 10.70.201.0/24
- Profile: Ping scan
- Command: nmap -sn 10.70.201.0/24

Result:
- 256 addresses scanned
- 3 hosts up

Hosts observed:
- 10.70.201.30 — MAC 04:ED:33:3C:74:4A — Intel Corporate
- 10.70.201.139 — MAC 82:F9:E4:06:11:E8 — vendor unknown
- 10.70.201.145 — student's Windows host

The topology PDF and screenshots should be placed in this directory when uploading the visual evidence.
