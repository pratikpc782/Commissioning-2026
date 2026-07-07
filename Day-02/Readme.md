# Day 02 – Building Your Cyber Lab (Kali + Windows Networking)

## Objective

Build a cybersecurity lab using VirtualBox consisting of:

- Kali Linux (Attacker)
- Windows 10/11 (Target)
- NAT and Host-Only Networking
- Clean Snapshots

---

## Learning Objectives

- Create a Kali Linux Virtual Machine.
- Create a Windows 10/11 Virtual Machine.
- Configure networking between host and VMs.
- Take snapshots for recovery.

---

## Theory

### Virtual Machine (VM)
A Virtual Machine is software that emulates a physical computer.

### NAT (Network Address Translation)
- Internet access available
- Outbound connections allowed
- Inbound connections restricted

### Host-Only Network
- Communication between Host and VMs
- No Internet

### Bridged Network
VM acts as a separate device on the physical network.

---

# Lab Setup

## Step 1 – Kali Linux VM

- Name: Kali
- Type: Linux
- Version: Debian (64-bit)
- RAM: 4096 MB
- Disk: 40 GB

Update Kali:

```bash
sudo apt update
sudo apt full-upgrade -y
sudo apt install -y open-vm-tools-desktop fuse
```

Enable:

- Bidirectional Clipboard
- Drag and Drop

Snapshot:

```
Kali_Clean
```

---

## Step 2 – Windows VM

Configuration

- Windows 10/11
- RAM: 4096 MB
- Disk: 60 GB

User

```
Username: student
Password: Password123
```

Tasks

- Install Windows
- Install VirtualBox Guest Additions
- Disable Defender temporarily
- Take Snapshot

```
Windows_Clean
```

---

## Step 3 – Networking

Adapter 1

```
NAT
```

Adapter 2

```
Host-Only (vboxnet0)
```

### Kali

```bash
ip a
```

### Windows

```cmd
ipconfig
```

Ping Test

```bash
ping <Windows-IP>
```

```cmd
ping <Kali-IP>
```

---

## Step 4 – Baseline Reports

Windows

```cmd
systeminfo > C:\baseline_systeminfo.txt
```

Kali

```bash
uname -a > ~/baseline_kernel.txt
```

---

## Advanced Tasks

- Create Ubuntu Server VM
- Take snapshots after major changes
- Create a Baseline System Report

---

## Summary

Successfully configured:

- Kali Linux VM
- Windows VM
- NAT Networking
- Host-Only Networking
- Baseline Reports
- VM Snapshots

---

## Commands Used

```bash
sudo apt update
sudo apt full-upgrade -y
sudo apt install -y open-vm-tools-desktop fuse
ip a
ping
uname -a
```
