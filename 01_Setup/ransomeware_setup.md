# ⚙️ Setup

This document outlines the initial environment preparation steps for the ransomware blocking lab.

> **Note:** The initial setup of the Windows and Linux virtual machines, installation of Sliver C2, and deployment of LimaCharlie sensors were completed in previous labs and are not included here.

---

## Environment Overview

| Component       | Description                            |
|----------------|-----------------------------------------|
| Attacker       | Ubuntu Server (accessed via SSH)        |
| Victim Machine | Windows 11 VM (VmWare)                  |
| EDR Platform   | LimaCharlie console with active sensor  |
---

## Setup Steps


# 1. SSH into the attacker machine
```bash
ssh <user>@<attacker-ip>
```
[SSH from host CMD](./screenshots/Ubuntu%20ssh.png)

# 2. Elevate to root user
```bash
sudo su
```
[Root User](./screenshots/sudo%20su.png)

# 3. Confirm root access
```bash
whoami
```
[Confirm Root](./screenshots/whoami.pmg)
