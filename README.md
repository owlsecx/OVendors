# 🦉 OVendors

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Requires-Root-red?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-2.0-cyan?style=flat-square"/>
</p>

> **OVendors** is an ARP-based network discovery tool with MAC vendor fingerprinting,
> device type detection, IP conflict detection, and real-time ARP monitoring — all from a clean terminal interface.

---

## 📌 Overview

OVendors sends raw ARP packets across your network and analyzes every response to:

- Identify connected devices by **MAC address and vendor**
- Classify **device types** (router, switch, IoT, camera, printer, VM, etc.)
- Detect **IP conflicts and ARP spoofing**
- Monitor **live ARP traffic** in real-time
- Export results as **JSON or CSV**

No external libraries required — built entirely on Python's standard library using raw sockets.

---

## 🖥️ Interface

| Option | Description |
|--------|-------------|
| **[1] List Interfaces** | Show all available network interfaces with MAC, IP, and state |
| **[2] Quick Scan** | Auto-detect interface and scan current network |
| **[3] Custom Scan** | Specify interface, target IP or CIDR, threads, and timeout |
| **[4] MAC Lookup** | Identify vendor and device type from any MAC address |
| **[5] ARP Monitor** | Watch live ARP requests and replies in real-time |
| **[6] Export Results** | Save last scan results as JSON or CSV |
| **[H] Help** | Display usage guide and feature list |
| **[0] Exit** | Quit OVendors |

---

## 🔍 Scan Features

- **Multi-threaded** — scans a full `/24` network in ~3 seconds (30 threads default)
- **Vendor Database** — 200+ OUI entries covering Cisco, Apple, Samsung, Ubiquiti, MikroTik, and more
- **Device Type Detection** — classifies router, switch, server, workstation, laptop, smartphone, tablet, printer, camera, IoT, virtual machine, and gateway
- **Conflict Detection** — flags duplicate IPs and potential ARP spoofing
- **RTT Measurement** — response time per host in milliseconds
- **Live Output** — devices appear as they respond, no waiting for scan to finish

---

## 📋 Device Types

| Icon | Type | Examples |
|------|------|---------|
| 🖧 | Router | Cisco, TP-Link, MikroTik |
| 🔀 | Switch | Cisco, Juniper, Ubiquiti |
| 🖥 | Server | Dell, HP, Microsoft |
| 💻 | Workstation / Laptop | Apple, Intel, Dell |
| 📱 | Smartphone | Samsung, Apple, Huawei |
| 🔌 | IoT | Raspberry Pi, Philips Hue, Ring |
| 📹 | Camera | Axis, Hikvision, Dahua |
| 🖨 | Printer | HP, Canon, Epson, Brother |
| ☁ | Virtual Machine | VMware, Hyper-V |
| 🌐 | Gateway / Firewall | Palo Alto, Fortinet |

---

## ⚙️ Requirements

- **Linux only** — uses `AF_PACKET` raw sockets
- **Root privileges** — required for raw socket access
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
sudo ./OVendors
```

### Quick Scan example

```
[2] Quick Scan → auto-detects interface → scans 192.168.1.0/24

  │  💻 192.168.1.1    aa:bb:cc:dd:ee:ff   Cisco                    1.3ms
  │  📱 192.168.1.10   11:22:33:44:55:66   Samsung                  2.1ms
  │  🔌 192.168.1.42   b8:27:eb:xx:xx:xx   Raspberry Pi             4.7ms
```

### Custom Scan example

```
Interface  : eth0
Target     : 10.0.0.0/24
Threads    : 50
Timeout    : 2.0s
```

---

## 📤 Export

After any scan, use **[6] Export Results** to save:

| Format | Contents |
|--------|----------|
| **JSON** | Full structured report with metadata, all device fields, conflicts, and timestamps |
| **CSV** | Spreadsheet-friendly: IP, MAC, OUI, Vendor, Device Type, RTT, Packets, Duplicate flag |

---

## 🛡️ Conflict Detection

OVendors automatically detects when two different MAC addresses claim the same IP:

```
  [!]  IP CONFLICT: 192.168.1.1
  │    MAC-1: aa:bb:cc:dd:ee:ff  vs  MAC-2: 11:22:33:44:55:66
```

This can indicate ARP spoofing, misconfigured devices, or DHCP issues.

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
