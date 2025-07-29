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
# 2. Elevate to root user
```bash
sudo su
```

# 3. Confirm root access
```bash
whoami
```
