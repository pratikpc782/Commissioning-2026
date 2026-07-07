# Day 03 – Linux for Security Analysts

## Objective

Learn Linux administration required for Cyber Security and SOC operations.

---

## Learning Objectives

- Navigate Linux filesystem
- Manage users and groups
- Manage permissions
- View running processes
- Control services
- Analyze logs

---

## Linux Concepts

### /etc/passwd

Stores user account information.

### /etc/shadow

Stores hashed passwords.

### systemd

Linux service manager.

### Logs

Location

```
/var/log/
```

Common logs

- auth.log
- syslog
- kern.log

---

# User Management

View users

```bash
cat /etc/passwd | grep bash
```

Create user

```bash
sudo useradd -m -s /bin/bash alice
```

Set password

```bash
sudo passwd alice
```

Create group

```bash
sudo groupadd security_team
```

Add user to group

```bash
sudo usermod -aG security_team alice
```

Verify

```bash
id alice
```

---

# Process Management

View processes

```bash
ps aux
```

Search Apache

```bash
ps aux | grep apache
```

Top Processes

```bash
top -n 1 -b
```

---

# Service Management

Check SSH

```bash
sudo systemctl status ssh
```

Stop SSH

```bash
sudo systemctl stop ssh
```

Start SSH

```bash
sudo systemctl start ssh
```

---

# Log Analysis

Monitor authentication logs

```bash
sudo tail -f /var/log/auth.log
```

Failed logins

```bash
sudo grep "Failed password" /var/log/auth.log | tail -10
```

SSH logs

```bash
journalctl -u ssh
```

---

# Daily Tasks

## Create Bob

```bash
sudo useradd -m bob
sudo passwd bob
sudo usermod -aG sudo bob
```

---

## Root Processes

```bash
ps -U root -u root u
```

---

## SSH Logs

```bash
journalctl -u ssh
```

---

## Cron Job

Edit cron

```bash
crontab -e
```

Add

```cron
* * * * * date >> ~/date_log.txt
```

Verify

```bash
cat ~/date_log.txt
```

---

# Important Commands

```bash
cat
grep
useradd
passwd
groupadd
usermod
id
ps
top
systemctl
tail
journalctl
crontab
```

---

## Summary

Completed:

- Linux user management
- Groups
- Process management
- Service management
- Log analysis
- SSH monitoring
- Cron jobs
