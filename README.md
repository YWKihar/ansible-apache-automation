# Ansible Apache Automation using Roles 🚀

A production-style Ansible project that manages the full lifecycle of an **Apache Web Server** on **AWS EC2 Ubuntu 24.04 LTS** using a clean **Ansible Roles (Galaxy structure)** approach.

This repository demonstrates real DevOps engineering practices: modular design, reusable roles, secure inventory handling, and idempotent infrastructure configuration.

---

## 📌 Project Purpose

This project is built to demonstrate:

- Infrastructure as Code (IaC) with Ansible
- Proper use of **Ansible Roles**
- Service lifecycle management (install, start, stop, remove)
- Secure DevOps practices
- Clean, modular, reusable automation design

---

## 🧱 Infrastructure Context

| Component      | Details                          |
|----------------|----------------------------------|
| Control Node   | Fedora / Ubuntu with Ansible     |
| Target Nodes   | AWS EC2 – Ubuntu 24.04 LTS      |
| Access Method  | SSH using `.pem` key            |
| Inventory      | Local `hosts.ini` (ignored)     |

---

## 📂 Project Structure (Galaxy Standard)

```
ansible-apache-automation/
│
├── Install.yaml
├── Remove.yaml
├── hosts.ini              # ignored for security
├── .gitignore
│
└── roles/
    ├── Install/
    │   ├── tasks/main.yml
    │   ├── handlers/
    │   ├── defaults/
    │   ├── vars/
    │   ├── templates/
    │   └── meta/
    │
    └── Remove/
        ├── tasks/main.yml
        ├── handlers/
        ├── defaults/
        ├── vars/
        ├── templates/
        └── meta/
```

---

## 🧠 Roles Overview

### 🔹 Install Role
Responsible for:

- Installing Apache package
- Updating apt cache
- Starting Apache service
- Enabling service on boot

### 🔹 Remove Role
Responsible for:

- Stopping Apache service
- Disabling it from boot
- Removing the Apache package completely

---

## 🔐 Security Best Practices

Sensitive data is never uploaded:

- No public IP addresses
- No SSH private keys
- No real inventory file

You must create your own local `hosts.ini`.

---

## ⚙️ Prerequisites

- Ansible installed on control node
- AWS EC2 Ubuntu instance
- SSH `.pem` key

---

## 📝 Step 1 — Clone the Repository

```bash
git clone https://github.com/YWKihar/ansible-apache-automation.git
cd ansible-apache-automation
```

---

## 📝 Step 2 — Create Your Inventory

Create `hosts.ini`:

```ini
[WEB]
YOUR_EC2_PUBLIC_IP ansible_user=ubuntu
```

---

## 📝 Step 3 — Secure Your Key

```bash
chmod 400 your-key.pem
```

---

## 🚀 Usage

### ▶️ Install & Start Apache (Using Install Role)

```bash
ansible-playbook -i hosts.ini Install.yaml --key-file your-key.pem
```

### ⛔ Stop & Remove Apache (Using Remove Role)

```bash
ansible-playbook -i hosts.ini Remove.yaml --key-file your-key.pem
```

---

## ✅ Expected Result

After running the install playbook:

- Apache is installed
- Service is running
- Service enabled at boot
- Default Apache page accessible via EC2 public IP

---

## 🎯 What This Proves

This project proves understanding of:

- Ansible Roles (Galaxy structure)
- Modular automation design
- Infrastructure as Code principles
- Secure DevOps repository practices
- Real-world cloud server automation

---

## 👤 Maintainer

**Yousef Kihar**  
DevOps Engineer | Automation | Cloud

GitHub: https://github.com/YWKihar
