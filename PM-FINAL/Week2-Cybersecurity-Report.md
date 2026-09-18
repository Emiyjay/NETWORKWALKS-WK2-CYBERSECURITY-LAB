# NetworkWalks Week 2 Cybersecurity Project Report

**Student:** John Emmanuel Sani  
**Batch:** B083  
**Week:** 2  
**Completed:** W2-PM1, W2-PM5, W2-PM-FINAL

## 1. Introduction

This report documents the Week 2 practical cybersecurity activities completed for the NetworkWalks program. The work covered footprinting of the assigned NetworkWalks web target and Zenmap network discovery on the student's local network.

The project requires one elective plus both essential projects. W2-PM1 was selected as the elective, W2-PM5 was completed as the scanning project, and this document is the required final report.

## 2. W2-PM1 — Footprinting with Multiple Kali Tools

Six tools were used: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, and DNSRecon.

### WHOIS

The captured output recorded GoDaddy.com, LLC as registrar, a 2019 creation date, a 2025 update date, a 2027 registry expiration date, HostGator nameservers, unsigned DNSSEC status, and privacy-protected registrant information.

### WhatWeb

The captured output identified Apache, WordPress 7.1, WordPress Download Manager 3.3.58, Bootstrap 7.1, jQuery 3.7.1, Google Tag Manager, HTML5, and the Networkwalks Academy title. The observed address was 192.232.216.135.

### Nslookup

networkwalks.com resolved to 192.232.216.135 through resolver 10.70.201.139. A subsequent resolver timeout was also recorded. The successful A-record response shows that DNS resolution worked during the test; the timeout was treated as a resolver communication issue.

### Curl

The HTTPS response returned HTTP/2 200 and identified Apache. WordPress REST API references appeared in Link headers. A __wpdm_client cookie was observed with Secure and HttpOnly attributes. The actual cookie value is intentionally excluded from the public repository.

### WAFW00F

WAFW00F detected ModSecurity (SpiderLabs). This indicates that a WAF was detected; it does not by itself establish that the application is secure or vulnerable.

### DNSRecon

DNSRecon recorded the A record 192.232.216.135, no answer for its DNSSEC query, an SOA resolution timeout through 10.70.201.139, and no SRV records. The SOA timeout was treated as a resolver limitation rather than proof that no SOA record exists.

## 3. W2-PM5 — Zenmap Network Scanning

The active Wi-Fi adapter had IPv4 address 10.70.201.145, subnet mask 255.255.255.0, and default gateway 10.70.201.139. The resulting subnet was 10.70.201.0/24.

Zenmap was configured with the Ping scan profile and the command nmap -sn 10.70.201.0/24.

The scan covered 256 IP addresses and reported three hosts up.

| IP address | Result | Additional observation |
|---|---|---|
| 10.70.201.30 | Host up | MAC 04:ED:33:3C:74:4A; Intel Corporate |
| 10.70.201.139 | Host up | MAC 82:F9:E4:06:11:E8; vendor unknown |
| 10.70.201.145 | Host up | Student's Windows host |

The Windows Wi-Fi physical address was separately confirmed as 24-77-03-C6-69-C4.

The Zenmap topology was successfully exported as a PDF.

## 4. Findings and Security Relevance

The footprinting exercise demonstrated how publicly observable registration, DNS, HTTP, technology, and WAF information can be combined to establish a basic target profile.

The WhatWeb output showed application technologies and versions, Curl exposed HTTP response metadata and WordPress REST API references, and WAFW00F identified ModSecurity. These are reconnaissance observations and are not vulnerability claims.

The Zenmap exercise demonstrated practical host discovery within the student's local network and reinforced the relationship between IPv4 addressing, subnet masks, gateways, and host discovery.

## 5. Limitations

- DNS queries experienced resolver timeouts during parts of the assessment.
- Technology fingerprinting may not identify every component or may occasionally misidentify technologies.
- WAF detection does not prove the effectiveness of the WAF.
- A ping scan identifies responding hosts but is not a complete security assessment.
- No exploitation, credential attacks, or destructive testing were performed.

## 6. Evidence

The repository contains documented PM1 observations and PM5 documentation. The original visual evidence files and Zenmap topology PDF should be placed in their corresponding directories when uploaded.

## 7. Conclusion

Week 2 practical work was completed through W2-PM1, W2-PM5, and the required final report. The exercise provided practical experience with domain footprinting, web technology identification, DNS inspection, HTTP-header analysis, WAF identification, DNS enumeration, and local network host discovery using Zenmap.

All findings are based on the captured practical outputs and are presented as reconnaissance observations rather than vulnerability claims.
