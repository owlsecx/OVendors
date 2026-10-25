# 🦉 OVendors

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OAttack%20/%20Offensive-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.1-cyan?style=flat-square"/>
</p>

> **OVendors** — ARP Analysis & MAC Fingerprinting

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OVendors is a MAC-address and hardware-vendor intelligence tool that resolves OUI prefixes to manufacturer names using an embedded vendor database. It identifies device makers from MAC addresses, supports bulk lookups and can enrich network inventories with vendor context. It runs offline for fast, authorized asset analysis.

---

## ✨ Features


- OUI-to-vendor resolution from an embedded manufacturer database
- Single and bulk MAC-address lookups
- Vendor enrichment for network inventories and scan results
- Offline operation with no external API dependency
- Clear, colour-coded terminal output
- Structured export of lookup results

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OVendors
./OVendors --self-test
./OVendors --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
