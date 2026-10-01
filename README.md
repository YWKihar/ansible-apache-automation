# Ansible Apache Automation

An Ansible project that automates the Apache HTTP Server lifecycle on Linux hosts using reusable Ansible roles.

## What It Does

The repository contains two playbooks:

- `Install.yaml` — applies the `Install` role to the `WEB` inventory group, updates the APT cache, installs Apache2, and starts/enables the service.
- `Remove.yaml` — applies the `Remove` role to the `WEB` inventory group, stops/disables Apache2, and removes the package.

## Repository Structure

```text
ansible-apache-automation/
├── Install.yaml
├── Remove.yaml
├── Install/
│   ├── defaults/
│   ├── handlers/
│   ├── meta/
│   ├── tasks/
│   ├── tests/
│   └── vars/
├── Remove/
│   ├── defaults/
│   ├── handlers/
│   ├── meta/
│   ├── tasks/
│   ├── tests/
│   └── vars/
└── .gitignore
```

## Requirements

- Ansible
- A Debian/Ubuntu target host with APT
- SSH access to the target host
- Privilege escalation (`become`) access

## Inventory

Create a local inventory such as:

```ini
[WEB]
YOUR_SERVER_IP ansible_user=ubuntu
```

The playbooks expect the inventory group name `WEB`.

## Run

Install Apache:

```bash
ansible-playbook -i hosts.ini Install.yaml --key-file your-key.pem
```

Remove Apache:

```bash
ansible-playbook -i hosts.ini Remove.yaml --key-file your-key.pem
```

## Automation Flow

```text
Inventory (WEB)
      │
      ├── Install.yaml ──> Install role ──> APT install ──> start + enable Apache
      │
      └── Remove.yaml ──> Remove role ──> stop + disable ──> remove Apache
```

## What I Practiced

- Ansible playbooks
- Ansible roles and role-based organization
- Package management with APT
- Linux service management
- SSH-based remote automation
- Privilege escalation with `become`

## Notes

The automation targets Debian/Ubuntu-style systems because the roles use the APT package manager and the `apache2` service name.

## Author

Yousef Kihar — [GitHub](https://github.com/YWKihar)
