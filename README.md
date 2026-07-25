# Enterprise Infrastructure Automation

An enterprise-style Infrastructure as Code (IaC) project built with **Ansible** to automate the deployment and configuration of Linux servers, Docker containers, and database services.

The objective of this project is to demonstrate production-style DevOps practices including configuration management, infrastructure automation, containerization, and service deployment.

---

# Architecture

```
                    +----------------------+
                    | ubuntu-lab2          |
                    |----------------------|
                    | Ansible Controller   |
                    | Git                  |
                    | Playbooks            |
                    +----------+-----------+
                               |
        --------------------------------------------
        |                    |                     |
        |                    |                     |
+---------------+    +----------------+    +----------------+
| app-lab2      |    | pg-standby2    |    | db2-lab2       |
|---------------|    |----------------|    |----------------|
| Docker        |    | PostgreSQL 14  |    | IBM Db2        |
| Nginx         |    |                |    | (Coming Soon)  |
+---------------+    +----------------+    +----------------+
```

---

# Environment

| Host | IP Address | Purpose |
|------|------------|---------|
| ubuntu-lab2 | 100.100.10.9 | Ansible Control Node |
| app-lab2 | 100.100.10.10 | Docker & Nginx |
| pg-standby2 | 100.100.10.11 | PostgreSQL |
| db2-lab2 | 100.100.10.12 | IBM Db2 |

---

# Technologies

- Ubuntu Server 22.04
- Ansible
- Docker
- Nginx
- PostgreSQL 14
- Git
- Linux
- SSH

---

# Current Features

- Passwordless SSH automation
- Inventory-based Ansible deployment
- Role-based Ansible project
- Docker installation
- Docker Python SDK installation
- Nginx container deployment
- Custom web page deployment
- PostgreSQL installation
- PostgreSQL service management
- Idempotent Ansible playbooks

---

# Project Structure

```text
enterprise-infrastructure-automation/
├── ansible.cfg
├── inventory/
├── playbooks/
├── roles/
│   ├── common/
│   ├── docker/
│   ├── nginx/
│   └── postgresql/
├── files/
├── templates/
├── docs/
└── README.md
```

---

# Example Commands

Verify connectivity

```bash
ansible linux -m ping
```

Deploy baseline configuration

```bash
ansible-playbook playbooks/baseline.yml --ask-become-pass
```

Deploy Docker

```bash
ansible-playbook playbooks/docker.yml --ask-become-pass
```

Deploy Nginx

```bash
ansible-playbook playbooks/nginx-container.yml --ask-become-pass
```

Deploy PostgreSQL

```bash
ansible-playbook playbooks/postgresql.yml --ask-become-pass
```

---

# Skills Demonstrated

- Infrastructure as Code (IaC)
- Configuration Management
- Linux Administration
- Docker Containerization
- PostgreSQL Administration
- Automation with Ansible
- SSH Key Management
- Git Version Control
- Idempotent Deployments

---

# Roadmap

- [x] Configure Ansible Control Node
- [x] Deploy Docker
- [x] Deploy Nginx Container
- [x] Install PostgreSQL
- [ ] Configure PostgreSQL Database Automation
- [ ] Install IBM Db2
- [ ] Deploy Jenkins
- [ ] Configure Prometheus
- [ ] Configure Grafana
- [ ] Deploy Kubernetes (k3s)
- [ ] Infrastructure Provisioning with Terraform
- [ ] CI/CD Pipeline

---

# Author

**Kossi Hevi-Doglan**

DevOps Engineer | Cloud Engineer | Infrastructure Automation
