# 🏦 Financial Grade Infrastructure: Local Micro-Bank Sub-Branch & Vault Security

[![Cisco Packet Tracer](https://img.shields.io/badge/Cisco_Packet_Tracer-v8.x-blue?logo=cisco)](https://www.netacad.com/)
[![Network Security](https://img.shields.io/badge/Security-Zero--Trust_L2-red)](#)
[![Compliance](https://img.shields.io/badge/Compliance-Financial_Audit_Ready-green)](#)

A secure, hardened network implementation for a financial micro-bank branch designed in **Cisco Packet Tracer**. This project focuses on **Central Bank regulatory compliance**, 
strictly enforcing **Layer 2 Switchport Port Security**,
**Isolated ATM transaction pipelines**, and **Extended Outbound/Inbound Access Control Lists (ACLs)**.

---

## 📋 Executive Overview & Threat Model

In micro-banking operations, financial fraud and data exfiltration occur most frequently via rogue hardware insertion at cashier counters or lateral pivot attacks from branch workstations into automated transaction machines (ATMs). 

### Compliance & Security Mandates:
1. **Physical Port Tampering Prevention:** Counter ports must automatically trip to `err-disable` (shutdown) immediately if an unauthorized device is plugged in.
2. **ATM Network Isolation:** The ATM terminal must only communicate with the HQ Core Banking Host on banking ports (`TCP 443 / 8443`). Inter-VLAN reconnaissance and lateral movement from branch workstations must be blocked.
3. **CCTV / Vault Data Confidentiality:** Video feeds from the Vault NVR are restricted strictly within local operations and cannot traverse the WAN edge.

---

## 🗺️ Network Topology & Architecture

- **Security Edge Router:** Cisco 2911 (`Bank-Gateway`)
- **Hardened Access/Distribution Switch:** Cisco 2960-24TT (`Branch-Core-SW`)
- **End-Devices:**
  - Cashier Workstations: `Teller-01`, `Teller-02`
  - Operations Management: `Branch-Manager`
  - Financial Kiosk: `ATM-Kiosk-01`
  - Surveillance Host: `Vault-NVR-Recorder`
  - Remote HQ Core System: `HQ-Core-Banking` (`10.100.100.10/24`)
 

