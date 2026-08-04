# Copper Code IT Lab

> A practical infrastructure engineering portfolio documenting the design, deployment and operation of my homelab.

![Portfolio](https://img.shields.io/badge/Portfolio-IT%20Infrastructure-blue)
![Location](https://img.shields.io/badge/Location-Australia-green)
![Current%20Focus](https://img.shields.io/badge/Current%20Focus-Active%20Directory-orange)
![Status](https://img.shields.io/badge/Status-Actively%20Learning-brightgreen)

## About Me

Hi, I’m Sandy Brendish, an aspiring infrastructure and systems engineer based in Australia.

I learn by building real systems. This repository documents my progression through networking, Windows Server, Linux, virtualisation, storage, automation and infrastructure troubleshooting.

The goal is not only to install software. Each project records the planning, design decisions, implementation, testing, failures, troubleshooting, recovery and lessons learned.

## Current Focus

I am currently building an enterprise-style Active Directory lab on an HP EliteDesk G2 using Proxmox VE.

The lab will include:

- Windows Server
- Active Directory Domain Services
- DNS
- DHCP
- Group Policy
- Windows client virtual machines
- File shares and NTFS permissions
- PowerShell automation
- Backup and recovery testing

[View the HP G2 Active Directory Lab](projects/hp-g2-active-directory-lab/README.md)

## Infrastructure Dashboard

| System | Purpose | Status |
|---|---|---|
| HP Z440 | AI workstation and Docker host | Operational |
| [TrueNAS Storage Server](projects/truenas-storage-server/README.md) | HP EliteDesk 800 G1 SFF | 🟢 Operational |
| HP EliteDesk G2 | Active Directory and Windows Server lab | Hardware validation |
| Cottage network | Managed switching, Wi-Fi and remote access | Operational and expanding |
| Home Assistant | Smart-home infrastructure | Planned |

## Lab Architecture

```mermaid
flowchart LR
    Internet --> Router[Router and Firewall]
    Router --> Switch[Managed Switch]
    Switch --> NAS[TrueNAS Server]
    Switch --> Z440[HP Z440 AI Workstation]
    Switch --> G2[HP G2 Active Directory Lab]
    Switch --> AP[Wireless Access Points]
    AP --> Clients[Clients and IoT Devices]

## ⭐ Featured Projects

These are the major infrastructure projects that make up my homelab. Each project includes planning, implementation, testing, troubleshooting and lessons learned.

---

### 🖥️ HP EliteDesk G2 Active Directory Lab

**Status:** 🟡 Hardware Validation

**Purpose**

Build an enterprise-style Windows Server environment to learn:

- Proxmox VE
- Windows Server
- Active Directory
- DNS
- DHCP
- Group Policy
- PowerShell
- Backup and Recovery

📖 **Documentation**

[View Project](projects/hp-g2-active-directory-lab/README.md)

---

### 💾 TrueNAS Storage Server

**Status:** 🟢 Operational

**Purpose**

Central storage server providing:

- ZFS storage
- SMB shares
- Jellyfin
- Immich
- Snapshots
- Backups
- Tailscale Remote Access

📖 **Documentation**

[View Project](projects/truenas-storage-server/README.md)

---

### 🤖 HP Z440 AI Workstation

**Status:** 🟢 Operational

**Purpose**

Local AI development workstation used for:

- Ubuntu Linux
- Docker
- Ollama
- Open WebUI
- CUDA
- Local LLMs
- Monitoring

🚧 Documentation currently being written.

---

### 🌐 Cottage Network

**Status:** 🟢 Operational

**Purpose**

Business-style network built using:

- Managed Switching
- Aruba Access Points
- VLAN Planning
- Tailscale
- Remote Management

🚧 Documentation currently being written.

---

### 🏠 Home Assistant

**Status:** ⚪ Planned

Future smart-home automation platform integrating:

- ESP32
- Smart plugs
- Sensors
- Dashboards
- Automations
- Voice assistants

---
