# Lab 01 — Port Scan Detection dengan Suricata

## Objective
Mendeteksi berbagai teknik port scanning menggunakan Suricata IDS
dan menganalisis perbedaan traffic pattern tiap teknik.

## Tools
- Nmap (attacker — Kali)
- Suricata (monitor)  
- tcpdump (packet capture)

## Steps
### 1. Reconnaissance — Ping Sweep
```bash
ping -c 5 192.168.254.129
```

### 2. Basic TCP Connect Scan
```bash
nmap 192.168.254.129
```

### 3. Stealth SYN Scan
```bash
sudo nmap -sS 192.168.254.129
```

### 4. Service Version Detection
```bash
sudo nmap -sV 192.168.254.129
```

### 5. Aggressive Scan
```bash
sudo nmap -A 192.168.254.129
```

## Findings
3 09/21/2026-14:41:57.035138  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47586 -> 192.168.254.129:80
3 09/21/2026-14:41:57.006000  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47570 -> 192.168.254.129:80
3 09/21/2026-14:41:56.992682  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47566 -> 192.168.254.129:80
3 09/21/2026-14:41:56.980171  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47554 -> 192.168.254.129:80
3 09/21/2026-14:41:56.942485  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47542 -> 192.168.254.129:80
3 09/21/2026-14:41:56.939423  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47536 -> 192.168.254.129:80
3 09/21/2026-14:41:56.938130  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47500 -> 192.168.254.129:80
3 09/21/2026-14:41:56.938056  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47484 -> 192.168.254.129:80
3 09/21/2026-14:41:56.937945  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47526 -> 192.168.254.129:80
3 09/21/2026-14:41:56.919902  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47378 -> 192.168.254.129:80
3 09/21/2026-14:41:56.918761  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47394 -> 192.168.254.129:80
3 09/21/2026-14:41:56.918378  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47468 -> 192.168.254.129:80
3 09/21/2026-14:41:56.918046  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47458 -> 192.168.254.129:80
3 09/21/2026-14:41:56.917815  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47448 -> 192.168.254.129:80
3 09/21/2026-14:41:56.916808  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47390 -> 192.168.254.129:80
3 09/21/2026-14:41:56.916560  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47426 -> 192.168.254.129:80
3 09/21/2026-14:41:56.914948  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47418 -> 192.168.254.129:80
3 09/21/2026-14:41:46.331823  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.129:0 -> 192.168.254.128:9
3 09/21/2026-14:40:41.898701  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:35266 -> 192.168.254.129:80
3 09/21/2026-14:40:41.891051  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:35228 -> 192.168.254.129:80
2 09/21/2026-14:41:57.042276  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47588 -> 192.168.254.129:80
2 09/21/2026-14:41:57.021081  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47574 -> 192.168.254.129:80
2 09/21/2026-14:41:56.941023  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:47550 -> 192.168.254.129:80
2 09/21/2026-14:41:56.938616  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47516 -> 192.168.254.129:80
2 09/21/2026-14:41:56.937947  [**] [1:2260002:1] SURICATA Applayer Detect protocol only one direction [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.254.128:47530 -> 192.168.254.129:80
2 09/21/2026-14:41:56.937947  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47530 -> 192.168.254.129:80
2 09/21/2026-14:41:56.917627  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47440 -> 192.168.254.129:80
2 09/21/2026-14:41:56.914341  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47396 -> 192.168.254.129:80
2 09/21/2026-14:41:56.277929  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.129:0 -> 192.168.254.128:9
2 09/21/2026-14:41:56.277747  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
2 09/21/2026-14:41:54.166509  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.129:0 -> 192.168.254.128:9
2 09/21/2026-14:41:50.552220  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.129:0 -> 192.168.254.128:9
2 09/21/2026-14:41:50.552001  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
2 09/21/2026-14:41:50.552001  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
2 09/21/2026-14:41:48.443056  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.129:0 -> 192.168.254.128:9
2 09/21/2026-14:41:39.562330  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:49175
2 09/21/2026-14:41:39.552233  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:783
2 09/21/2026-14:41:39.551413  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:10621
2 09/21/2026-14:41:39.542880  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:9502
2 09/21/2026-14:40:41.897151  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:35256 -> 192.168.254.129:80
2 09/21/2026-14:40:41.887315  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:35242 -> 192.168.254.129:80
2 09/21/2026-14:40:35.678218  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:6004
2 09/21/2026-14:39:44.109176  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:6003
2 09/21/2026-14:39:44.105127  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:765
2 09/21/2026-14:39:44.047787  [**] [1:9000001:1] Nmap scan terdeteksi cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:993
2 09/21/2026-14:39:07.712802  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:161
2 09/21/2026-14:39:07.698418  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:7741
1 09/21/2026-14:41:57.042275  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47588 -> 192.168.254.129:80
1 09/21/2026-14:41:57.021080  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47574 -> 192.168.254.129:80
1 09/21/2026-14:41:56.954722  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47550 -> 192.168.254.129:80
1 09/21/2026-14:41:56.954720  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47550 -> 192.168.254.129:80
1 09/21/2026-14:41:56.954718  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47550 -> 192.168.254.129:80
1 09/21/2026-14:41:56.938617  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47516 -> 192.168.254.129:80
1 09/21/2026-14:41:56.937948  [**] [1:2260002:1] SURICATA Applayer Detect protocol only one direction [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {TCP} 192.168.254.128:47530 -> 192.168.254.129:80
1 09/21/2026-14:41:56.937948  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47530 -> 192.168.254.129:80
1 09/21/2026-14:41:56.934495  [**] [1:9000001:1] Nmap scan terdeteksi cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:47536 -> 192.168.254.129:80
1 09/21/2026-14:41:56.931836  [**] [1:9000001:1] Nmap scan terdeteksi cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:47526 -> 192.168.254.129:80
1 09/21/2026-14:41:56.917626  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47440 -> 192.168.254.129:80
1 09/21/2026-14:41:56.917117  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47438 -> 192.168.254.129:80
1 09/21/2026-14:41:56.917116  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47438 -> 192.168.254.129:80
1 09/21/2026-14:41:56.917115  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47438 -> 192.168.254.129:80
1 09/21/2026-14:41:56.914340  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:47396 -> 192.168.254.129:80
1 09/21/2026-14:41:56.907749  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:47426 -> 192.168.254.129:80
1 09/21/2026-14:41:56.903707  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57394 -> 192.168.254.129:22
1 09/21/2026-14:41:56.303077  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:56.303075  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:56.277928  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.129:0 -> 192.168.254.128:9
1 09/21/2026-14:41:56.277747  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:56.277745  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:56.277745  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:54.190758  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:54.190756  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:54.166508  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.129:0 -> 192.168.254.128:9
1 09/21/2026-14:41:54.166303  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:54.166302  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:54.166302  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:54.166300  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:54.166300  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:50.577033  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:50.577032  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:50.552221  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.129:0 -> 192.168.254.128:9
1 09/21/2026-14:41:50.552002  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:48.467787  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:48.467785  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:48.443055  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.129:0 -> 192.168.254.128:9
1 09/21/2026-14:41:48.442818  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:48.442817  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:48.442817  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:48.442768  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:48.442768  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:46.356454  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:46.356452  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:41:46.331585  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:46.331584  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:46.331584  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:46.331582  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:46.331582  [**] [1:2200025:2] SURICATA ICMPv4 unknown code [**] [Classification: Generic Protocol Command Decode] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:9
1 09/21/2026-14:41:39.565443  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1277
1 09/21/2026-14:41:39.565165  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:16113
1 09/21/2026-14:41:39.565088  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:54328
1 09/21/2026-14:41:39.565087  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:24800
1 09/21/2026-14:41:39.564602  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5915
1 09/21/2026-14:41:39.564490  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3404
1 09/21/2026-14:41:39.564206  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:30000
1 09/21/2026-14:41:39.563957  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3269
1 09/21/2026-14:41:39.563848  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:6788
1 09/21/2026-14:41:39.563444  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:49161
1 09/21/2026-14:41:39.563330  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:32
1 09/21/2026-14:41:39.563282  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2393
1 09/21/2026-14:41:39.563162  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:18101
1 09/21/2026-14:41:39.562932  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:9000
1 09/21/2026-14:41:39.562826  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1839
1 09/21/2026-14:41:39.562039  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:264
1 09/21/2026-14:41:39.562038  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:6004
1 09/21/2026-14:41:39.561714  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2010
1 09/21/2026-14:41:39.561435  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:7103
1 09/21/2026-14:41:39.561080  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:4003
1 09/21/2026-14:41:39.561080  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1074
1 09/21/2026-14:41:39.560912  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2366
1 09/21/2026-14:41:39.560910  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:10082
1 09/21/2026-14:41:39.560857  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:6005
1 09/21/2026-14:41:39.560689  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5800
1 09/21/2026-14:41:39.560641  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1900
1 09/21/2026-14:41:39.560397  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:8193
1 09/21/2026-14:41:39.560345  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1145
1 09/21/2026-14:41:39.557770  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5631
1 09/21/2026-14:41:39.557521  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:20828
1 09/21/2026-14:41:39.557224  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:49167
1 09/21/2026-14:41:39.557109  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1503
1 09/21/2026-14:41:39.557108  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2875
1 09/21/2026-14:41:39.557050  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:4001
1 09/21/2026-14:41:39.555860  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5120
1 09/21/2026-14:41:39.553915  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2045
1 09/21/2026-14:41:39.553742  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3766
1 09/21/2026-14:41:39.553741  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:52673
1 09/21/2026-14:41:39.553611  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1026
1 09/21/2026-14:41:39.553456  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1641
1 09/21/2026-14:41:39.553237  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:4279
1 09/21/2026-14:41:39.553120  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1085
1 09/21/2026-14:41:39.552609  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:119
1 09/21/2026-14:41:39.552557  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2160
1 09/21/2026-14:41:39.552396  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1062
1 09/21/2026-14:41:39.552128  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2557
1 09/21/2026-14:41:39.551910  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5009
1 09/21/2026-14:41:39.551413  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1087
1 09/21/2026-14:41:39.551091  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:61900
1 09/21/2026-14:41:39.550870  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3784
1 09/21/2026-14:41:39.550764  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:666
1 09/21/2026-14:41:39.550206  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3283
1 09/21/2026-14:41:39.549976  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1687
1 09/21/2026-14:41:39.549923  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5544
1 09/21/2026-14:41:39.549581  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:13456
1 09/21/2026-14:41:39.549331  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:4449
1 09/21/2026-14:41:39.549278  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:464
1 09/21/2026-14:41:39.549276  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:27355
1 09/21/2026-14:41:39.549219  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3221
1 09/21/2026-14:41:39.549218  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3493
1 09/21/2026-14:41:39.548662  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:555
1 09/21/2026-14:41:39.548648  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:35500
1 09/21/2026-14:41:39.548353  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:8200
1 09/21/2026-14:41:39.548139  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5989
1 09/21/2026-14:41:39.548009  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:6106
1 09/21/2026-14:41:39.547493  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1524
1 09/21/2026-14:41:39.547107  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2126
1 09/21/2026-14:41:39.547106  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2126
1 09/21/2026-14:41:39.546771  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3261
1 09/21/2026-14:41:39.546718  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:7938
1 09/21/2026-14:41:39.546664  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2008
1 09/21/2026-14:41:39.546468  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2190
1 09/21/2026-14:41:39.546221  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:10778
1 09/21/2026-14:41:39.545892  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:6567
1 09/21/2026-14:41:39.545770  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1533
1 09/21/2026-14:41:39.545547  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:7627
1 09/21/2026-14:41:39.545202  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:100
1 09/21/2026-14:41:39.544610  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5100
1 09/21/2026-14:41:39.544450  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:32776
1 09/21/2026-14:41:39.544346  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:61532
1 09/21/2026-14:41:39.544294  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:7000
1 09/21/2026-14:41:39.544136  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:548
1 09/21/2026-14:41:39.543921  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:44501
1 09/21/2026-14:41:39.543868  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1113
1 09/21/2026-14:41:39.543148  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:9001
1 09/21/2026-14:41:39.542611  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:407
1 09/21/2026-14:41:39.542554  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:65000
1 09/21/2026-14:41:39.542341  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:27353
1 09/21/2026-14:41:39.542289  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:20000
1 09/21/2026-14:41:39.541999  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1002
1 09/21/2026-14:41:39.541710  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:11110
1 09/21/2026-14:41:39.541664  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:6566
1 09/21/2026-14:41:39.541566  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:543
1 09/21/2026-14:41:39.541338  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1078
1 09/21/2026-14:41:39.541037  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:726
1 09/21/2026-14:41:39.541035  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1069
1 09/21/2026-14:41:39.540465  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:32768
1 09/21/2026-14:41:39.540078  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:31038
1 09/21/2026-14:41:39.539840  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2013
1 09/21/2026-14:41:39.539839  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1050
1 09/21/2026-14:41:39.539729  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1247
1 09/21/2026-14:41:39.539727  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1053
1 09/21/2026-14:41:39.539672  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:85
1 09/21/2026-14:41:39.539071  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1097
1 09/21/2026-14:41:39.538773  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5902
1 09/21/2026-14:41:39.538714  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:900
1 09/21/2026-14:41:39.538463  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:648
1 09/21/2026-14:41:39.538299  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3905
1 09/21/2026-14:41:39.537925  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1084
1 09/21/2026-14:41:39.537819  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:6547
1 09/21/2026-14:41:39.537604  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:6669
1 09/21/2026-14:41:39.537443  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1583
1 09/21/2026-14:41:39.537281  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:541
1 09/21/2026-14:41:39.537063  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:30951
1 09/21/2026-14:41:39.536954  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:6000
1 09/21/2026-14:41:39.536377  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:4998
1 09/21/2026-14:41:39.536273  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:146
1 09/21/2026-14:41:39.536271  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1066
1 09/21/2026-14:41:39.536110  [**] [1:9000001:1] Nmap scan terdeteksi cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:2103
1 09/21/2026-14:41:39.535934  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5280
1 09/21/2026-14:41:39.535932  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:79
1 09/21/2026-14:41:39.535683  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:5825
1 09/21/2026-14:41:39.535433  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1081
1 09/21/2026-14:41:39.534166  [**] [1:9000001:1] Nmap scan terdeteksi cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:1720
1 09/21/2026-14:41:39.534041  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:22
1 09/21/2026-14:41:39.533319  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:60914 -> 192.168.254.129:3306
1 09/21/2026-14:40:41.897150  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:35256 -> 192.168.254.129:80
1 09/21/2026-14:40:41.887313  [**] [1:2024364:5] ET SCAN Possible Nmap User-Agent Observed [**] [Classification: Web Application Attack] [Priority: 1] {TCP} 192.168.254.128:35242 -> 192.168.254.129:80
1 09/21/2026-14:40:35.678650  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2041
1 09/21/2026-14:40:35.678460  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:7938
1 09/21/2026-14:40:35.677678  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:6059
1 09/21/2026-14:40:35.677356  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:15000
1 09/21/2026-14:40:35.677355  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:50636
1 09/21/2026-14:40:35.677291  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:10617
1 09/21/2026-14:40:35.677000  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1201
1 09/21/2026-14:40:35.676278  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:27356
1 09/21/2026-14:40:35.676217  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:3260
1 09/21/2026-14:40:35.676162  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:20000
1 09/21/2026-14:40:35.676013  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:9011
1 09/21/2026-14:40:35.675952  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:10025
1 09/21/2026-14:40:35.675791  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:109
1 09/21/2026-14:40:35.675722  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:15004
1 09/21/2026-14:40:35.675519  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:15003
1 09/21/2026-14:40:35.675097  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1060
1 09/21/2026-14:40:35.674822  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:9220
1 09/21/2026-14:40:35.674556  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:6580
1 09/21/2026-14:40:35.674441  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:8082
1 09/21/2026-14:40:35.674259  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:3269
1 09/21/2026-14:40:35.674208  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:13722
1 09/21/2026-14:40:35.673923  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:50800
1 09/21/2026-14:40:35.673861  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:84
1 09/21/2026-14:40:35.673814  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:541
1 09/21/2026-14:40:35.673736  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:20005
1 09/21/2026-14:40:35.673450  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2608
1 09/21/2026-14:40:35.673165  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:8701
1 09/21/2026-14:40:35.670683  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2399
1 09/21/2026-14:40:35.670515  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:17988
1 09/21/2026-14:40:35.670512  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:3871
1 09/21/2026-14:40:35.670349  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:9575
1 09/21/2026-14:40:35.670349  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5988
1 09/21/2026-14:40:35.670113  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:8800
1 09/21/2026-14:40:35.670109  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:4045
1 09/21/2026-14:40:35.669914  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:10778
1 09/21/2026-14:40:35.668894  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:7625
1 09/21/2026-14:40:35.666999  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:50001
1 09/21/2026-14:40:35.666823  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1050
1 09/21/2026-14:40:35.666544  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:3261
1 09/21/2026-14:40:35.666523  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5631
1 09/21/2026-14:40:35.666385  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:33354
1 09/21/2026-14:40:35.666221  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2200
1 09/21/2026-14:40:35.663585  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:24800
1 09/21/2026-14:40:35.663533  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:49152
1 09/21/2026-14:40:35.663481  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:6156
1 09/21/2026-14:40:35.663089  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:407
1 09/21/2026-14:40:35.662648  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:3011
1 09/21/2026-14:40:35.662411  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:9502
1 09/21/2026-14:40:35.662128  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:13782
1 09/21/2026-14:40:35.662023  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:49160
1 09/21/2026-14:40:35.661744  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5987
1 09/21/2026-14:40:35.661196  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:9999
1 09/21/2026-14:40:35.661092  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1503
1 09/21/2026-14:40:35.661030  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:16080
1 09/21/2026-14:40:35.660425  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2013
1 09/21/2026-14:40:35.660258  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:6005
1 09/21/2026-14:40:35.660256  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:9001
1 09/21/2026-14:40:35.660131  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1110
1 09/21/2026-14:40:35.660040  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:6565
1 09/21/2026-14:40:35.659726  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1259
1 09/21/2026-14:40:35.659364  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1070
1 09/21/2026-14:40:35.658252  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:545
1 09/21/2026-14:40:35.658064  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5269
1 09/21/2026-14:40:35.657999  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:3
1 09/21/2026-14:40:35.657894  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5825
1 09/21/2026-14:40:35.657824  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2401
1 09/21/2026-14:40:35.657585  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:700
1 09/21/2026-14:40:35.657513  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2500
1 09/21/2026-14:40:35.657460  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2557
1 09/21/2026-14:40:35.656988  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2144
1 09/21/2026-14:40:35.656701  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5907
1 09/21/2026-14:40:35.656618  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:9003
1 09/21/2026-14:40:35.656326  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1071
1 09/21/2026-14:40:35.656042  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1132
1 09/21/2026-14:40:35.655710  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1296
1 09/21/2026-14:40:35.655574  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:119
1 09/21/2026-14:40:35.655375  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:8083
1 09/21/2026-14:40:35.655373  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:222
1 09/21/2026-14:40:35.655006  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:55056
1 09/21/2026-14:40:35.654809  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5800
1 09/21/2026-14:40:35.654697  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:340
1 09/21/2026-14:40:35.654696  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1117
1 09/21/2026-14:40:35.654128  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:6002
1 09/21/2026-14:40:35.654126  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:9000
1 09/21/2026-14:40:35.653793  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:593
1 09/21/2026-14:40:35.653671  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:212
1 09/21/2026-14:40:35.653474  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:6788
1 09/21/2026-14:40:35.652983  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1236
1 09/21/2026-14:40:35.652981  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:4224
1 09/21/2026-14:40:35.652644  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:10628
1 09/21/2026-14:40:35.652463  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:16001
1 09/21/2026-14:40:35.652289  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1083
1 09/21/2026-14:40:35.652238  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5989
1 09/21/2026-14:40:35.652174  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1583
1 09/21/2026-14:40:35.652111  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:7512
1 09/21/2026-14:40:35.651992  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:900
1 09/21/2026-14:40:35.651938  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1309
1 09/21/2026-14:40:35.651934  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:14238
1 09/21/2026-14:40:35.651161  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:27715
1 09/21/2026-14:40:35.651054  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:49175
1 09/21/2026-14:40:35.650735  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:8600
1 09/21/2026-14:40:35.650291  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:8100
1 09/21/2026-14:40:35.650290  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1455
1 09/21/2026-14:40:35.650129  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:32774
1 09/21/2026-14:40:35.649851  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:3268
1 09/21/2026-14:40:35.649797  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:89
1 09/21/2026-14:40:35.649560  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:3828
1 09/21/2026-14:40:35.649508  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5952
1 09/21/2026-14:40:35.648969  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:32780
1 09/21/2026-14:40:35.648911  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1036
1 09/21/2026-14:40:35.648721  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1812
1 09/21/2026-14:40:35.648614  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5298
1 09/21/2026-14:40:35.648310  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:90
1 09/21/2026-14:40:35.648155  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5009
1 09/21/2026-14:40:35.648155  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2046
1 09/21/2026-14:40:35.647707  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:61900
1 09/21/2026-14:40:35.647410  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:3324
1 09/21/2026-14:40:35.647348  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:722
1 09/21/2026-14:40:35.647296  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:1026
1 09/21/2026-14:40:35.646996  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:32769
1 09/21/2026-14:40:35.646474  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:7921
1 09/21/2026-14:40:35.646473  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:32770
1 09/21/2026-14:40:35.646410  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:32782
1 09/21/2026-14:40:35.645692  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:10010
1 09/21/2026-14:40:35.645572  [**] [1:9000001:1] Nmap scan terdeteksi cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:5960
1 09/21/2026-14:40:35.645495  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:8009
1 09/21/2026-14:40:35.645280  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:2001
1 09/21/2026-14:40:35.645013  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:100
1 09/21/2026-14:40:35.644730  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:6000
1 09/21/2026-14:40:35.644510  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:23
1 09/21/2026-14:40:35.644344  [**] [1:9000001:1] Nmap scan terdeteksi cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:53
1 09/21/2026-14:40:35.644230  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:48403 -> 192.168.254.129:135
1 09/21/2026-14:39:44.117419  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2383
1 09/21/2026-14:39:44.117305  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:14238
1 09/21/2026-14:39:44.116921  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:6566
1 09/21/2026-14:39:44.116710  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1072
1 09/21/2026-14:39:44.116439  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:62078
1 09/21/2026-14:39:44.115489  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2126
1 09/21/2026-14:39:44.114524  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:6646
1 09/21/2026-14:39:44.113582  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:9900
1 09/21/2026-14:39:44.113339  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:17
1 09/21/2026-14:39:44.112979  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1113
1 09/21/2026-14:39:44.112274  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:7512
1 09/21/2026-14:39:44.110759  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:9102
1 09/21/2026-14:39:44.110075  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:19283
1 09/21/2026-14:39:44.109942  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:17988
1 09/21/2026-14:39:44.109601  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1175
1 09/21/2026-14:39:44.109022  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5033
1 09/21/2026-14:39:44.108406  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:3527
1 09/21/2026-14:39:44.107837  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5999
1 09/21/2026-14:39:44.107473  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:56738
1 09/21/2026-14:39:44.106687  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:9999
1 09/21/2026-14:39:44.106271  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:50636
1 09/21/2026-14:39:44.106141  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:27715
1 09/21/2026-14:39:44.105788  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2065
1 09/21/2026-14:39:44.105402  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1104
1 09/21/2026-14:39:44.104705  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:711
1 09/21/2026-14:39:44.104705  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1054
1 09/21/2026-14:39:44.104367  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:8010
1 09/21/2026-14:39:44.104137  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1216
1 09/21/2026-14:39:44.103683  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:3333
1 09/21/2026-14:39:44.103419  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5051
1 09/21/2026-14:39:44.102513  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:7937
1 09/21/2026-14:39:44.101706  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:4900
1 09/21/2026-14:39:44.100464  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1075
1 09/21/2026-14:39:44.100174  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:6007
1 09/21/2026-14:39:44.100173  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1095
1 09/21/2026-14:39:44.099650  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:24800
1 09/21/2026-14:39:44.099531  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2160
1 09/21/2026-14:39:44.097892  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:3011
1 09/21/2026-14:39:44.097744  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:25735
1 09/21/2026-14:39:44.096947  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1068
1 09/21/2026-14:39:44.096828  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5925
1 09/21/2026-14:39:44.096402  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:9535
1 09/21/2026-14:39:44.095833  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:10009
1 09/21/2026-14:39:44.094356  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:843
1 09/21/2026-14:39:44.093741  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5298
1 09/21/2026-14:39:44.093279  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:10024
1 09/21/2026-14:39:44.092946  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5101
1 09/21/2026-14:39:44.092590  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:4445
1 09/21/2026-14:39:44.091948  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:26214
1 09/21/2026-14:39:44.091133  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:32768
1 09/21/2026-14:39:44.090249  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5100
1 09/21/2026-14:39:44.089660  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1047
1 09/21/2026-14:39:44.089179  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:50000
1 09/21/2026-14:39:44.088967  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:3871
1 09/21/2026-14:39:44.088086  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:50800
1 09/21/2026-14:39:44.087971  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:18988
1 09/21/2026-14:39:44.087863  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2121
1 09/21/2026-14:39:44.087361  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5862
1 09/21/2026-14:39:44.087170  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:7000
1 09/21/2026-14:39:44.085995  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:9943
1 09/21/2026-14:39:44.084662  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1124
1 09/21/2026-14:39:44.083959  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5200
1 09/21/2026-14:39:44.083514  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:19101
1 09/21/2026-14:39:44.082783  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1164
1 09/21/2026-14:39:44.082021  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:8899
1 09/21/2026-14:39:44.082021  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5002
1 09/21/2026-14:39:44.081926  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:3168
1 09/21/2026-14:39:44.081817  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:32775
1 09/21/2026-14:39:44.081098  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:50389
1 09/21/2026-14:39:44.080904  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1023
1 09/21/2026-14:39:44.080801  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:6788
1 09/21/2026-14:39:44.080132  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1000
1 09/21/2026-14:39:44.079238  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:30951
1 09/21/2026-14:39:44.078425  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1032
1 09/21/2026-14:39:44.078333  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:7002
1 09/21/2026-14:39:44.077932  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5560
1 09/21/2026-14:39:44.077211  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:8333
1 09/21/2026-14:39:44.077008  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:6100
1 09/21/2026-14:39:44.076207  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:9220
1 09/21/2026-14:39:44.076020  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1046
1 09/21/2026-14:39:44.075008  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2251
1 09/21/2026-14:39:44.074270  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2725
1 09/21/2026-14:39:44.074089  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:648
1 09/21/2026-14:39:44.073899  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:543
1 09/21/2026-14:39:44.073565  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5960
1 09/21/2026-14:39:44.072871  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1137
1 09/21/2026-14:39:44.072697  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:3551
1 09/21/2026-14:39:44.072243  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:311
1 09/21/2026-14:39:44.072241  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:4443
1 09/21/2026-14:39:44.071637  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5963
1 09/21/2026-14:39:44.071334  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:88
1 09/21/2026-14:39:44.071169  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2021
1 09/21/2026-14:39:44.070236  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:7200
1 09/21/2026-14:39:44.069853  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:40911
1 09/21/2026-14:39:44.069725  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1040
1 09/21/2026-14:39:44.069568  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:99
1 09/21/2026-14:39:44.068698  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:49156
1 09/21/2026-14:39:44.067494  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:3005
1 09/21/2026-14:39:44.067493  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:6123
1 09/21/2026-14:39:44.067344  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5901
1 09/21/2026-14:39:44.067344  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:51493
1 09/21/2026-14:39:44.066674  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1097
1 09/21/2026-14:39:44.065898  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5226
1 09/21/2026-14:39:44.065053  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2103
1 09/21/2026-14:39:44.064406  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5718
1 09/21/2026-14:39:44.063422  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2033
1 09/21/2026-14:39:44.062816  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:19
1 09/21/2026-14:39:44.061641  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:544
1 09/21/2026-14:39:44.060130  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5950
1 09/21/2026-14:39:44.059778  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:13722
1 09/21/2026-14:39:44.059577  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:43
1 09/21/2026-14:39:44.059324  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1971
1 09/21/2026-14:39:44.058564  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:3878
1 09/21/2026-14:39:44.056669  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:50500
1 09/21/2026-14:39:44.056440  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:16113
1 09/21/2026-14:39:44.056271  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:15003
1 09/21/2026-14:39:44.055715  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5810
1 09/21/2026-14:39:44.054744  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:2718
1 09/21/2026-14:39:44.053350  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:777
1 09/21/2026-14:39:44.051892  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:9003
1 09/21/2026-14:39:44.051726  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:9101
1 09/21/2026-14:39:44.051534  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:13782
1 09/21/2026-14:39:44.050728  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:1718
1 09/21/2026-14:39:44.050496  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:49158
1 09/21/2026-14:39:44.050342  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:5988
1 09/21/2026-14:39:44.049323  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:7921
1 09/21/2026-14:39:44.047301  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:22
1 09/21/2026-14:39:44.045816  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:43860 -> 192.168.254.129:8888
1 09/21/2026-14:39:07.718488  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:8300
1 09/21/2026-14:39:07.718366  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5555
1 09/21/2026-14:39:07.718253  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:912
1 09/21/2026-14:39:07.718252  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3168
1 09/21/2026-14:39:07.717778  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3322
1 09/21/2026-14:39:07.717475  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3826
1 09/21/2026-14:39:07.717298  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:33899
1 09/21/2026-14:39:07.717179  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:8000
1 09/21/2026-14:39:07.717178  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1090
1 09/21/2026-14:39:07.716904  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5902
1 09/21/2026-14:39:07.716690  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:481
1 09/21/2026-14:39:07.716539  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:10012
1 09/21/2026-14:39:07.716486  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:8090
1 09/21/2026-14:39:07.716360  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2967
1 09/21/2026-14:39:07.716249  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1121
1 09/21/2026-14:39:07.716060  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3703
1 09/21/2026-14:39:07.715511  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2190
1 09/21/2026-14:39:07.715447  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5432
1 09/21/2026-14:39:07.715445  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3998
1 09/21/2026-14:39:07.715135  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:50002
1 09/21/2026-14:39:07.714782  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2179
1 09/21/2026-14:39:07.714512  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:9009
1 09/21/2026-14:39:07.714442  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2383
1 09/21/2026-14:39:07.714034  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:163
1 09/21/2026-14:39:07.713970  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:49176
1 09/21/2026-14:39:07.713719  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:55555
1 09/21/2026-14:39:07.713507  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1201
1 09/21/2026-14:39:07.713436  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1080
1 09/21/2026-14:39:07.713379  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:41511
1 09/21/2026-14:39:07.712900  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1076
1 09/21/2026-14:39:07.712537  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:7625
1 09/21/2026-14:39:07.712455  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:8222
1 09/21/2026-14:39:07.712087  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5633
1 09/21/2026-14:39:07.711918  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:777
1 09/21/2026-14:39:07.711552  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:37
1 09/21/2026-14:39:07.711317  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:999
1 09/21/2026-14:39:07.710919  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1666
1 09/21/2026-14:39:07.710918  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3828
1 09/21/2026-14:39:07.710871  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2251
1 09/21/2026-14:39:07.710815  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:425
1 09/21/2026-14:39:07.710559  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:6669
1 09/21/2026-14:39:07.710501  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1199
1 09/21/2026-14:39:07.710016  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:32777
1 09/21/2026-14:39:07.709959  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:9220
1 09/21/2026-14:39:07.709958  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:32784
1 09/21/2026-14:39:07.709655  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:9878
1 09/21/2026-14:39:07.709349  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5030
1 09/21/2026-14:39:07.709282  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:7435
1 09/21/2026-14:39:07.708816  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1117
1 09/21/2026-14:39:07.708680  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2105
1 09/21/2026-14:39:07.708516  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:32778
1 09/21/2026-14:39:07.708515  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:6839
1 09/21/2026-14:39:07.708230  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:6005
1 09/21/2026-14:39:07.708038  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:49165
1 09/21/2026-14:39:07.707985  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:90
1 09/21/2026-14:39:07.707571  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:33
1 09/21/2026-14:39:07.707219  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:50003
1 09/21/2026-14:39:07.706933  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:9100
1 09/21/2026-14:39:07.706868  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:7938
1 09/21/2026-14:39:07.706706  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:7496
1 09/21/2026-14:39:07.706571  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:6566
1 09/21/2026-14:39:07.706570  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:6566
1 09/21/2026-14:39:07.706222  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1300
1 09/21/2026-14:39:07.705995  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3324
1 09/21/2026-14:39:07.705994  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1935
1 09/21/2026-14:39:07.705658  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1801
1 09/21/2026-14:39:07.705594  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1119
1 09/21/2026-14:39:07.705540  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:8083
1 09/21/2026-14:39:07.705307  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:50300
1 09/21/2026-14:39:07.704635  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:7001
1 09/21/2026-14:39:07.704338  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5952
1 09/21/2026-14:39:07.704177  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1126
1 09/21/2026-14:39:07.703997  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:749
1 09/21/2026-14:39:07.703837  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:6689
1 09/21/2026-14:39:07.703726  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2033
1 09/21/2026-14:39:07.703386  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2001
1 09/21/2026-14:39:07.703094  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:6580
1 09/21/2026-14:39:07.702760  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:49153
1 09/21/2026-14:39:07.702706  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:10003
1 09/21/2026-14:39:07.702646  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:8443
1 09/21/2026-14:39:07.702408  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:646
1 09/21/2026-14:39:07.702353  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2196
1 09/21/2026-14:39:07.701725  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:7777
1 09/21/2026-14:39:07.701724  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:24800
1 09/21/2026-14:39:07.701642  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:15003
1 09/21/2026-14:39:07.701611  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:51493
1 09/21/2026-14:39:07.701301  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:625
1 09/21/2026-14:39:07.701047  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:6543
1 09/21/2026-14:39:07.700446  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:280
1 09/21/2026-14:39:07.700444  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:52848
1 09/21/2026-14:39:07.700390  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1073
1 09/21/2026-14:39:07.700323  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:10001
1 09/21/2026-14:39:07.700162  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5679
1 09/21/2026-14:39:07.700112  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1052
1 09/21/2026-14:39:07.700050  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:11110
1 09/21/2026-14:39:07.699209  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1024
1 09/21/2026-14:39:07.698847  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:9000
1 09/21/2026-14:39:07.698650  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:9917
1 09/21/2026-14:39:07.698262  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2126
1 09/21/2026-14:39:07.697975  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3689
1 09/21/2026-14:39:07.697213  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:4125
1 09/21/2026-14:39:07.697159  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2135
1 09/21/2026-14:39:07.696769  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2869
1 09/21/2026-14:39:07.696712  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:9943
1 09/21/2026-14:39:07.696557  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1092
1 09/21/2026-14:39:07.696315  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5911
1 09/21/2026-14:39:07.696196  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:19315
1 09/21/2026-14:39:07.695327  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:8873
1 09/21/2026-14:39:07.694801  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2006
1 09/21/2026-14:39:07.694462  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3945
1 09/21/2026-14:39:07.694269  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5962
1 09/21/2026-14:39:07.694035  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1053
1 09/21/2026-14:39:07.693548  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1070
1 09/21/2026-14:39:07.693106  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:57797
1 09/21/2026-14:39:07.692892  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3827
1 09/21/2026-14:39:07.692891  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:1086
1 09/21/2026-14:39:07.692637  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:34571
1 09/21/2026-14:39:07.692558  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:8009
1 09/21/2026-14:39:07.692318  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5120
1 09/21/2026-14:39:07.692156  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:254
1 09/21/2026-14:39:07.691425  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:4001
1 09/21/2026-14:39:07.691219  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:406
1 09/21/2026-14:39:07.690903  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:5200
1 09/21/2026-14:39:07.690689  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:2020
1 09/21/2026-14:39:07.690313  [**] [1:9000001:1] Nmap scan terdeteksi cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:3801
1 09/21/2026-14:39:07.689937  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:7920
1 09/21/2026-14:39:07.689857  [**] [1:9000001:1] Nmap scan terdeteksi cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:53
1 09/21/2026-14:39:07.689856  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:111
1 09/21/2026-14:39:07.689235  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:23
1 09/21/2026-14:39:07.688344  [**] [1:9000002:1] SCAN multiple ports detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {TCP} 192.168.254.128:57099 -> 192.168.254.129:22
1 09/21/2026-14:38:40.635117  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:38:40.635115  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:38:39.611022  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:38:39.611021  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:38:38.591156  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:38:38.591145  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:38:37.563000  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:38:37.562997  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:38:36.554566  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0
1 09/21/2026-14:38:36.554564  [**] [1:9000003:1] ICMP ping detected, cuy [**] [Classification: Detection of a Network Scan] [Priority: 3] {ICMP} 192.168.254.128:8 -> 192.168.254.129:0



## Key Takeaways
- SYN scan (-sS) lebih stealthy karena tidak complete 3-way handshake
- Suricata mendeteksi scan pattern dari frekuensi SYN packets
- Service detection (-sV) menghasilkan lebih banyak alert karena
  aktif probe setiap port
