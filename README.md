# SWYNEX-Network-Security-Analysis

**Task 2: Network Security Analysis (SWYNEX Internship)**
 
A defensive analysis of network traffic captured from my own Kali Linux lab using Wireshark.
 
## Objective
 
Analyze network traffic in a controlled environment to identify protocols, suspicious patterns, and potential security concerns, then document the results in a defensive analysis report.
 
## Environment
 
| Item | Details |
|---|---|
| Tool | Wireshark |
| Operating system | Kali Linux (virtual machine) |
| Network mode | NAT |
| Interface | eth0 |
| Capture duration | about 3 minutes |
 
> All traffic was captured from my own lab. No traffic was captured from networks I don't own or have permission to monitor.
 
## Methodology
 
1. Captured traffic on `eth0` with Wireshark.
2. Generated traffic with `ping`, `nslookup`, `curl`, and browsing to `neverssl.com` and `wikipedia.org`.
3. Reviewed **Statistics → Protocol Hierarchy** to identify protocols.
4. Applied display filters (`icmp`, `dns`, `tcp`, `http`, `tls`) to inspect each protocol.
5. Used **Follow → HTTP Stream** to inspect unencrypted traffic.
6. Reviewed **Analyze → Expert Information** for errors and warnings.
## Protocols Identified
 
| Protocol | Purpose |
|---|---|
| ICMP | Connectivity testing (ping) |
| DNS | Translating domain names to IP addresses |
| TCP | Reliable connections between devices |
| HTTP | Unencrypted web traffic |
| TLS | Encrypted web traffic (HTTPS) |
 
## Key Findings
 
- **Unencrypted HTTP traffic (Medium risk):** HTTP content was readable in plain text, so anyone on the same network could read it.
- **Encrypted HTTPS traffic (Low risk):** TLS traffic was properly encrypted and its content was not readable.
- **Visible DNS queries (Low risk):** Standard DNS reveals which domains a device looks up.
- **Expert Information (Low risk):** Only minor, normal warnings such as TCP retransmissions.
- No malicious activity, port scans, or ARP spoofing were found in this capture.
  
## Recommendations
 
- Use HTTPS everywhere and avoid sending data over HTTP.
- Never enter credentials on HTTP pages.
- Use encrypted DNS.
- Use a firewall to block unnecessary ports.
- Monitor traffic with an IDS such as Snort or Suricata.
- Segment the network and use a VPN on untrusted networks.

## What I Learned
 
- How to capture and filter traffic in Wireshark.
- How to tell encrypted traffic (TLS) apart from unencrypted traffic (HTTP).
- How to read the Info column and packet details to understand what a packet does.
- How to turn raw packet data into a clear defensive report with recommendations.
  
## Author
Fathima Hannah
https://www.linkedin.com/in/fathima-hannah-b88930372/

 
