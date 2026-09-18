# NetworkWalks Week 2 Cybersecurity Lab

**Student:** John Emmanuel Sani  
**Batch:** B083  
**Week:** 2

## Project scope

This repository contains the Week 2 practical work completed for the NetworkWalks cybersecurity program.

The Week 2 requirement is **one elective module + both essential projects**. This submission uses:

| Module | Status |
|---|---|
| **W2-PM1 — Footprinting with multiple Kali tools** | Completed |
| **W2-PM5 — Zenmap based Network Scanning** | Completed |
| **W2-PM-FINAL — Detailed Report** | Completed |

PM2 (GHDB), PM3 (Maltego), and PM4 (theHarvester) are elective alternatives and are therefore not required for this submission.

---

## W2-PM1 — Footprinting

Six Kali tools were used against the assigned NetworkWalks target:

1. WHOIS
2. WhatWeb
3. Nslookup
4. Curl
5. Wafw00f
6. DNSRecon

The exercise documented domain registration information, DNS resolution, web technologies, HTTP response headers, WAF detection, and DNS enumeration results.

### Key observations

- `networkwalks.com` resolved to `192.232.216.135`.
- WHOIS identified GoDaddy.com, LLC as registrar and recorded privacy-protected registrant information.
- WhatWeb identified Apache, WordPress 7.1, WordPress Download Manager 3.3.58, Bootstrap 7.1, jQuery 3.7.1, Google Tag Manager, and HTML5.
- Curl returned HTTP/2 200 and exposed WordPress REST API references in response headers.
- WAFW00F detected ModSecurity (SpiderLabs).
- DNSRecon recorded the A record and documented DNSSEC/SOA/SRV observations.

The complete command outputs and visual evidence are stored under `PM1-Footprinting/`.

---

## W2-PM5 — Zenmap Network Scanning

The active Windows Wi-Fi configuration was used to identify the local subnet.

- IPv4 address: `10.70.201.145`
- Subnet mask: `255.255.255.0`
- Default gateway: `10.70.201.139`
- Target subnet: `10.70.201.0/24`

Zenmap configuration:

- **Profile:** Ping scan
- **Command:** `nmap -sn 10.70.201.0/24`
- **Addresses scanned:** 256
- **Hosts reported up:** 3

Observed hosts:

| IP address | Observation |
|---|---|
| `10.70.201.30` | Host up; Intel Corporate MAC identified |
| `10.70.201.139` | Host up; MAC vendor unknown |
| `10.70.201.145` | Student's Windows host |

The Zenmap topology was successfully exported as a PDF.

---

## Evidence structure

```text
NETWORKWALKS-WK2-CYBERSECURITY-LAB/
├── README.md
├── PM1-Footprinting/
│   ├── 01-whois.txt
│   ├── 02-whatweb.txt
│   ├── 03-nslookup.txt
│   ├── 04-curl.txt
│   ├── 05-wafw00f.txt
│   ├── 06-dnsrecon.txt
│   └── screenshots/
├── PM5-Zenmap/
│   ├── README.md
│   ├── screenshots/
│   └── zenmap-topology.pdf
└── PM-FINAL/
    └── Week2-Cybersecurity-Report.md
```

---

## Security and evidence handling

This is an educational cybersecurity submission. Testing was limited to the assigned NetworkWalks target and the student's local network for the Zenmap exercise.

No exploitation, credential attacks, destructive testing, or unauthorized access was performed.

Sensitive transient values are deliberately excluded from the public repository. In particular, the actual `__wpdm_client` cookie value observed during the Curl test is **not** published.

---

## Final report

The consolidated report is located at `PM-FINAL/Week2-Cybersecurity-Report.md`.

Visual evidence and the Zenmap topology PDF will be placed in their corresponding directories as they are uploaded.