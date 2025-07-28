# 🛡️ Ransomware Blocking Lab (Windows VM)

This lab demonstrates how to detect and actively **disrupt ransomware behavior** using LimaCharlie’s Detection & Response (D&R) rules. Instead of just generating alerts, we take it a step further by **terminating malicious processes** before they cause real damage. The attack simulation is performed using a **Sliver C2 session** on a Windows virtual machine, targeting the deletion of Volume Shadow Copies — a common tactic in ransomware attacks.

---

## 🎯 Lab Objectives

- Understand how ransomware attempts to disable file recovery by deleting Volume Shadow Copies.
- Create and test a **blocking D&R rule** in LimaCharlie.
- Terminate the **parent process** responsible for suspicious commands.
- Observe how detections are logged, enriched, and acted upon in LimaCharlie.

---

## 🧰 Tools Used

- **Sliver C2** – to simulate a ransomware attack
- **Windows 10 VM** – as the target victim machine
- **LimaCharlie** – for endpoint telemetry and response

---

## 📁 Lab Structure

| File         | Description                                                             |
|--------------|-------------------------------------------------------------------------|
| `setup.md`   | Environment setup: configuring Sliver C2, Windows VM, and LimaCharlie   |
| `attack.md`  | Walkthrough of the simulated ransomware attack using `vssadmin`         |
| `detection.md`| Creating and testing the D&R rule to detect and block the attack       |

---

## 🔍 Overview

Ransomware often begins by deleting Volume Shadow Copies to prevent recovery:

```sh
vssadmin delete shadows /all
