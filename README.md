# Ansible Apache Automation 🚀

Production-style Ansible automation to manage an **Apache Web Server** on **AWS EC2 (Ubuntu 24.04 LTS)**.

This project demonstrates real Infrastructure-as-Code (IaC) practices, including secure inventory handling, idempotent configuration, and clean service lifecycle management using Ansible playbooks.

---

## 📌 What This Project Demonstrates

This repository is designed to showcase practical DevOps skills:

- Automated software provisioning with Ansible
- Idempotent server configuration
- Service lifecycle management (install, start, stop, remove)
- Secure handling of sensitive files using `.gitignore`
- Clean, reproducible infrastructure setup on AWS EC2

---

## 🧱 Infrastructure Context

| Component        | Details                          |
|------------------|----------------------------------|
| Control Node     | Fedora / Ubuntu with Ansible     |
| Target Nodes     | AWS EC2 - Ubuntu 24.04 LTS       |
| Access Method    | SSH using `.pem` key             |
| Inventory Style  | Local `hosts.ini` (ignored for security) |

---

## 📂 Repository Structure

```
ansible-apache-automation/
│
├── Install.yaml      # Install and start Apache
├── Remove.yaml       # Stop and remove Apache
├── .gitignore        # Prevents upload of keys and inventory
└── README.md
```

---

## 🔐 Security First

This project follows DevOps security best practices:

- **No public IP addresses** are stored in the repo
- **No SSH keys** are uploaded
- The inventory file `hosts.ini` is intentionally ignored

You must create your own local inventory file.

---

## ⚙️ Prerequisites

Before running the playbooks, ensure:

- Ansible is installed on your control node
- You have an AWS EC2 instance running Ubuntu
- You have the `.pem` SSH key for access

---

## 📝 Step 1 — Clone the Repository

```bash
git clone https://github.com/YWKihar/ansible-apache-automation.git
cd ansible-apache-automation
```

---

## 📝 Step 2 — Create Your Inventory File

Create a file named `hosts.ini` in the project root:

```ini
[WEB]
YOUR_EC2_PUBLIC_IP ansible_user=ubuntu
```

---

## 📝 Step 3 — Secure Your SSH Key

Place your `.pem` file inside the project folder and run:

```bash
chmod 400 your-key.pem
```

---

## 🚀 Usage

### ▶️ Install and Start Apache

```bash
ansible-playbook -i hosts.ini Install.yaml --key-file your-key.pem
```

### ⛔ Stop and Remove Apache

```bash
ansible-playbook -i hosts.ini Remove.yaml --key-file your-key.pem
```

---

## ✅ Expected Outcome

After running the install playbook:

- Apache will be installed
- The service will be started
- Apache will be enabled to start on boot
- You can access the default Apache page via your EC2 public IP

---

## 🧠 Why This Project Matters

This repository is not just about installing Apache.

It shows understanding of:

- Infrastructure as Code principles
- Secure DevOps practices
- Ansible playbook structure
- Real-world cloud server management

---

## 👤 Maintainer

**Yousef Kihar**  
DevOps | Automation | Cloud Engineering

GitHub: https://github.com/YWKihar
