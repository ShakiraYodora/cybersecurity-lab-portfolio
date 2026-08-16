# SOC Network Traffic Analysis Lab – Wireshark

## Project Overview

This project demonstrates hands-on network traffic analysis using Wireshark in a Windows environment. I captured and analyzed network traffic to better understand how common network protocols operate and how packet analysis can be used during a SOC investigation.

The lab focused on identifying normal network behavior, following network conversations, analyzing protocol activity, and making security conclusions based on packet evidence.

## Tools Used

- Wireshark 4.6.8
- Npcap
- Windows
- Command Prompt

## Protocols Analyzed

- TCP
- DNS
- TLS / HTTPS
- ARP
- ICMP
- IPv4 / IPv6

## Skills Demonstrated

- Packet capture and network traffic analysis
- Wireshark display filtering
- TCP three-way handshake analysis
- TCP stream analysis
- DNS query and response analysis
- A, AAAA, and CNAME record analysis
- TLS Client Hello and Server Hello analysis
- TLS 1.3 identification
- Server Name Indication (SNI) identification
- ARP address resolution
- ICMP Echo Request and Echo Reply analysis
- TCP FIN and RST analysis
- OSI model protocol identification
- Evidence-based SOC investigation

## Investigation Highlights

### DNS Analysis

I analyzed DNS queries and responses to understand how domain names are resolved to IP addresses. I examined A and AAAA records, CNAME chains, DNS response times, and traffic using port 53.

### TCP Analysis

I identified TCP three-way handshakes by analyzing:

SYN → SYN-ACK → ACK

I also used TCP streams to isolate individual conversations and examined both graceful connection termination using FIN/ACK and connection resets using RST.

### TLS / HTTPS Analysis

I analyzed TLS traffic following successful TCP connections to port 443. I examined Client Hello and Server Hello messages, TLS versions, cipher suite information, and Server Name Indication (SNI).

### ARP Analysis

I examined ARP requests and responses to understand how devices on a local network resolve IPv4 addresses to MAC addresses.

### ICMP Analysis

I generated ICMP traffic using the `ping` command and analyzed Echo Request and Echo Reply packets. I also examined TTL and its role in preventing packets from circulating indefinitely.

## Final SOC Investigation

For the final investigation, I analyzed an external HTTPS connection initiated by an internal workstation.

I identified:

- A successful TCP three-way handshake
- Communication over TCP port 443
- TLS 1.3 traffic
- Server Name Indication (SNI)
- Encrypted application traffic

Based on the packet evidence alone, there was not enough evidence to classify the connection as malicious.

This investigation reinforced an important SOC principle:

> Absence of malicious evidence does not automatically prove that network activity is safe.

Additional endpoint telemetry, SIEM logs, process information, or threat intelligence would be required to make a stronger security determination.

## Key Takeaways

This project strengthened my understanding of how network protocols appear in real packet captures and how Wireshark can be used to investigate network activity.

It also helped me practice separating what packet evidence proves from what would require additional investigation.

## Security & Privacy

Screenshots and documentation shared publicly have been sanitized to remove internal IP addresses, MAC addresses, and device identifiers. Raw packet capture files are not included in this public repository.
