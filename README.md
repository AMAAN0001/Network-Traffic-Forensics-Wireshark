# Network Traffic Analysis & Forensics Using Wireshark

**Timeline:** Apr 2024 – May 2024  
**Author:** Sayyed Amaan  

## 📌 Overview
This project focuses on **network traffic analysis & forensics** by capturing, inspecting, and analyzing traffic using **Wireshark** and **tcpdump**.  
Attack scenarios were simulated in a controlled test lab and analyzed for forensic evidence.

## 🚀 Key Features
- Real-time packet capture & inspection  
- Detection of:
  - Man-in-the-Middle (MITM)
  - ARP poisoning
  - IP spoofing
  - DNS hijacking
  - Session hijacking  
- Deep Packet Inspection (DPI) of suspicious traffic  
- Forensic anomaly detection  

## 🛠️ Tools & Technologies
- **Wireshark** (analysis)  
- **tcpdump** (packet capture)  
- **Linux (Ubuntu/Kali)**  
- **Virtual test lab** (VMs for attacker + victim)

## ⚡ Quick Start
### Capture Packets
```bash
# Capture all packets
sudo tcpdump -i eth0 -w captures/all_traffic.pcap

# Capture only DNS traffic
sudo tcpdump -i eth0 port 53 -w captures/dns_traffic.pcap
