# Network Security Assessment Report

## 1. Introduction

This report presents the findings of a network security assessment conducted using Nmap and Wireshark. The objective of this assessment was to identify active hosts, open ports, running services, and potential vulnerabilities in the local network.

---

## 2. Tools Used

- Nmap (Network scanning and service detection)
- Wireshark (Packet capturing and traffic analysis)

---

## 3. Methodology

### Step 1: Network Discovery
Used Nmap to identify active devices in the local network.

Command used:
nmap -sn 192.168.1.0/24

### Step 2: Detailed Port and Service Scan
Command used:
nmap -sV -O 192.168.1.0/24 -oN nmap_results.txt

This helped detect:
- Open ports
- Running services
- Service versions
- Operating system details

### Step 3: Traffic Capture
Used Wireshark to capture live network traffic and analyze protocols.

Filters used:
http
dns
arp
tcp.port == 23

---

## 4. Nmap Scan Results

### Active Hosts Detected
Multiple devices were identified within the network.

### Open Ports Identified
- Port 80 (HTTP)
- Port 443 (HTTPS)
- Port 445 (SMB)
- Port 135 (MSRPC)

---

## 5. Wireshark Traffic Analysis

Observed protocols:
- HTTP
- DNS
- ARP
- TCP
- ICMP

Findings:
- Plain HTTP traffic detected
- ARP broadcast traffic observed
- DNS queries visible
- No encrypted traffic inspection issues

---

## 6. Identified Vulnerabilities

### 1. Open SMB Port (Port 445) – HIGH Risk
- May allow remote exploitation
- Often targeted in ransomware attacks
- Could enable lateral movement within network

### 2. Open HTTP Port (Port 80) – MEDIUM Risk
- Unencrypted communication
- Vulnerable to packet sniffing
- Risk of Man-in-the-Middle attacks

### 3. Service Version Exposure – MEDIUM Risk
- Attackers can identify vulnerable software versions
- Enables targeted exploitation

### 4. Weak Firewall Filtering – MEDIUM Risk
- Multiple open ports increase attack surface
- Lack of strict inbound/outbound rules

---

## 7. Risk Assessment Summary

| Vulnerability | Risk Level | Impact |
|--------------|------------|--------|
| SMB Exposure | High | Remote exploitation |
| HTTP Traffic | Medium | Data interception |
| Version Disclosure | Medium | Targeted attacks |
| Weak Firewall Rules | Medium | Increased attack surface |

---

## 8. Recommendations

- Disable SMBv1
- Close unused ports
- Replace HTTP with HTTPS
- Enable strict firewall rules
- Keep systems updated with latest security patches
- Use intrusion detection systems (IDS)

---

## 9. Conclusion

The network security assessment identified several potential vulnerabilities that could be exploited by attackers. Implementing recommended security measures will significantly improve the overall security posture of the network.
