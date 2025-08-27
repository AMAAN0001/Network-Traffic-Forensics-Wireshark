# Network Forensics Report

**Case Study:** Detecting Cyber Threats in Lab Network  
**Date:** Apr – May 2024  
**Analyst:** Sayyed Amaan  

---

## 1. Objective
Analyze captured network traffic for anomalies and cyber threats using **Wireshark** and **tcpdump**.

---

## 2. Attack Scenarios
- **MITM Attack (Ettercap simulation)**  
- **ARP Poisoning**  
- **DNS Hijacking**  
- **Session Hijacking**  

---

## 3. Findings

### A) ARP Poisoning
- **Observation:** Multiple ARP replies from one MAC claiming multiple IPs.  
- **Wireshark Filter Used:** `arp`  
- **Evidence:** `192.168.1.100 is at 08:00:27:5a:b3:9f` (repeated with different IPs)  
- **Conclusion:** Confirms ARP poisoning attempt.

---

### B) DNS Hijacking
- **Observation:** DNS response gave fake IP for `www.example.com`.  
- **Wireshark Filter Used:** `dns`  
- **Evidence:** Query: `www.example.com` → Answer: `10.0.0.66` (attacker IP)  
- **Conclusion:** DNS hijacking attack detected.

---

### C) Man-in-the-Middle (MITM)
- **Observation:** Duplicate TCP sessions with abnormal sequence numbers.  
- **Wireshark Filter Used:** `ip.src == attacker_ip`  
- **Evidence:** Extra HTTP GET requests relayed by attacker.  
- **Conclusion:** MITM attack successful.

---

### D) Session Hijacking
- **Observation:** Suspicious TCP Reset packets breaking sessions.  
- **Wireshark Filter Used:** `tcp.flags.reset == 1`  
- **Evidence:** Abrupt session termination without user action.  
- **Conclusion:** Possible TCP session hijacking attempt.

---

## 4. Recommendations
- Use **static ARP entries** to prevent ARP spoofing.  
- Deploy **DNSSEC** to mitigate DNS hijacking.  
- Use encrypted protocols (**HTTPS, SSH**) to avoid MITM.  
- Implement IDS/IPS with Snort/Suricata.  

---
