# Ansible Apache Automation 🚀

This project demonstrates how to automate the installation and management of **Apache Web Server** on **AWS EC2** instances using **Ansible**.

## 📌 Project Overview
The goal is to provide a modular and reusable way to:
* Install Apache on Ubuntu servers.
* Manage Apache services (Start, Stop, Enable).
* Remove Apache completely from target hosts.

## 🛠️ Tech Stack
* **Infrastructure:** AWS (EC2 Instances).
* **Configuration Management:** Ansible.
* **OS:** Ubuntu 24.04 LTS (Targets) & Fedora (Control Node).

## 📂 Project Structure
* `Install.yaml`: Playbook to install and start Apache.
* `Remove.yaml`: Playbook to stop and uninstall Apache.
* `.gitignore`: Ensures sensitive data like `.pem` keys and `hosts.ini` are not uploaded.

## 🚀 How to Run
1. **Clone the repo:**
   ```bash
   git clone [https://github.com/YWKihar/ansible-apache-automation.git](https://github.com/YWKihar/ansible-apache-automation.git)
