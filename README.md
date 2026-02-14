# Network-Security-Assessment
Network Security Assessment using Nmap and Wireshark.


## 📌 Project Overview

This project demonstrates a network security assessment performed using Nmap and Wireshark. The objective was to identify active hosts, open ports, running services, and potential security vulnerabilities within a local network.

---

## 🎯 Objective

- Perform network discovery
- Identify open ports and services
- Capture and analyze network traffic
- Detect potential security vulnerabilities
- Provide security recommendations

---

## 🛠 Tools Used

- Nmap – Network scanning and service detection
- Wireshark – Packet capture and traffic analysis
- Kali Linux – Testing environment
- VirtualBox – Virtualization platform

---

## 🔎 Methodology

### 1️⃣ Network Discovery
Used:
nmap -sn 192.168.1.0/24

To identify active devices in the network.

### 2️⃣ Service & Version Detection
Used:
nmap -sV -O 192.168.1.0/24

To detect:
- Open ports
- Running services
- Service versions
- Operating system details

### 3️⃣ Traffic Analysis
Captured live network traffic using Wireshark and applied filters:
- http
- dns
- arp
- tcp.port == 23

---

## 🚨 Key Findings

| Vulnerability | Risk Level | Description |
|--------------|------------|------------|
| SMB (Port 445) | High | Possible remote exploitation |
| HTTP (Port 80) | Medium | Unencrypted traffic |
| Service Version Exposure | Medium | Enables targeted attacks |
| Weak Firewall Filtering | Medium | Increased attack surface |

---

## 🛡 Recommendations

- Disable SMBv1
- Close unused ports
- Replace HTTP with HTTPS
- Apply strict firewall rules
- Regularly update systems
- Implement intrusion detection systems (IDS)

---

## 📂 Project Files

- network_security_assessment.md – Detailed security report
- nmap_results.txt – Nmap scan results
- wireshark_capture.pcapng – Captured network traffic file

---

## 📊 Conclusion

The assessment identified multiple potential vulnerabilities that could expose the network to security risks. Implementing recommended mitigation strategies can significantly improve network security posture.

---

## 👩‍💻 Author

Vishista Muthoju  
B.Tech – Computer Science & Engineering (Cybersecurity)
