# WIRESHARK-ANALYSIS

## Objective
To analyze packet capture (PCAP) file for suspicious network traffic, anomalies, and potential security threats.

## PCAP Information
- **File Name:** capture.pcapng
- **Duration:** 30 minutes
- **Total Packets:** 12,847
- **Capture Method:** Wireshark on Wi-Fi interface

## Summary of Findings

| Finding | Severity | Count |
|---------|----------|-------|
| ARP spoofing detected | High | 3 events |
| HTTP login attempts | Medium | 12 attempts |
| DNS queries to unknown domain | Low | 8 queries |
| Outbound connection on port 4444 | High | 1 connection |

## Key Observations

### 1. ARP Spoofing Detection
Two devices claimed same IP address (192.168.1.1), indicating possible ARP poisoning.

### 2. Cleartext CredentialsCaptured HTTP POST containing username and password in plaintext.

### 3. Suspicious Outbound ConnectionInternal host 192.168.1.105 connected to external IP 45.155.205.33 on port 4444 (commonly used by Metasploit).

## Indicators of Compromise (IOCs)

| Type | Value |
|------|-------|
| Source IP | 192.168.1.105 |
| Destination IP | 45.155.205.33 |
| Destination Port | 4444 |
| Suspicious Domain | update-check[.]xyz |

## Wireshark Filters Used
```bash
# ARP spoofing
arp.duplicate-address-frame

# HTTP traffic
http.request

# DNS to unknown domain
dns.qry.name contains "update-check"

# Suspicious ports
tcp.port == 4444 or tcp.port == 1337
Recommendations:

>Shows you are not just finding problems, but solving them

>Employers want to see remediation skills

>Makes the report actionable (not just theoretical)

Conclusion

>Provides professional closure to the report

>Summarizes key takeaways for executives

>Demonstrates communication skills
