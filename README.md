# Homelab Network Security & Monitoring

## Architecture
- **Attacker**: Kali Linux (192.168.254.128)
- **Target**: Ubuntu Server (192.168.254.129) — Apache, SSH
- **Monitor**: Ubuntu Server (192.168.254.130) — Suricata IDS

## Environment
- VMware Workstation Pro 26H2
- Host-Only Network: 192.168.254.0/24

## Labs
| # | Lab | Tools | Status |
|---|-----|-------|--------|
| 01 | Port Scan Detection | Nmap, Suricata, tcpdump | ✅ |

## Tools Used
- Suricata 8.0.3 (IDS/IPS)
- Nmap (reconnaissance)
- tcpdump / Wireshark (packet analysis)
