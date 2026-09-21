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
```bash 
[Count]  [SID]             [Event Name]
532      [1:9000002:1] 	   SCAN Multiple Port Detected
87       [1:2024364:5]     ET SCAN Possible Nmap User-Agent Observed
30       [1:9000003:1]     ICMP Ping Detected
30       [1:2200025:2]     SURICATA ICMPv4 unknown code
10       [1:9000001:1]     NMAP Scan Detected
3        [1:2260002:1]     SURICATA Applayer Detect protocol only one direction
```

### Observations
- SYN scan (-sS) menghasilkan paling banyak alert karena
  kirim SYN ke ratusan port dalam hitungan detik
- Aggressive scan (-A) trigger lebih banyak rule karena
  kombinasi OS detection + service probe + script scan
- Ping sweep terdeteksi duluan sebelum actual port scan

### Traffic Pattern (dari tcpdump)
- Normal traffic: SYN → SYN-ACK → ACK (3-way handshake complete)
- SYN scan: SYN → SYN-ACK → RST (tidak complete handshake)
- Closed port: SYN → RST (langsung ditolak)
