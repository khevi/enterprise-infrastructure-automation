# Enterprise Infrastructure Automation

Enterprise Infrastructure Automation is a hands-on DevOps project that demonstrates how to automate the deployment and management of Linux infrastructure using **Ansible**, **Docker**, **PostgreSQL**, and **Jenkins**.

The objective of this project is to build an enterprise-style environment where infrastructure, applications, and CI/CD pipelines are managed through Infrastructure as Code (IaC) and automation.

---

# Project Goals

- Build an enterprise-style Linux environment
- Automate infrastructure using Ansible
- Deploy containerized applications with Docker
- Manage PostgreSQL automatically
- Implement a dedicated Jenkins CI/CD server
- Demonstrate Infrastructure as Code best practices
- Build a portfolio-quality DevOps project

---

# Current Architecture

```text
                               GitHub
                                  │
                                  │
                                  ▼
                        +----------------------+
                        |   Jenkins Server     |
                        |    jenkins-lab2      |
                        +----------+-----------+
                                   │
                                   │
                                   ▼
                        +----------------------+
                        |  Ansible Controller  |
                        |    ubuntu-lab2       |
                        +----------+-----------+
                                   │
          ------------------------------------------------------
          │                      │                      │
          │                      │                      │
          ▼                      ▼                      ▼
+------------------+   +------------------+   +------------------+
|  app-lab2        |   | pg-standby2      |   | db2-lab2         |
|------------------|   |------------------|   |------------------|
| Docker           |   | PostgreSQL 14    |   | IBM Db2          |
| Nginx            |   | Database Server  |   | Database Server  |
+------------------+   +------------------+   +------------------+
```

---

# Lab Environment

| Server | Purpose |
|---------|---------|
| ubuntu-lab2 | Ansible Control Node |
| app-lab2 | Docker & Nginx Application Server |
| pg-standby2 | PostgreSQL Database Server |
| db2-lab2 | IBM Db2 Server |
| jenkins-lab2 | Jenkins CI/CD Server |

---

# Technologies

- Ubuntu Server 22.04 LTS
- Ansible
- Docker
- Nginx
- PostgreSQL 14
- Jenkins LTS
- Git
- GitHub
- SSH

---

# Repository Structure

```text
enterprise-infrastructure-automation/
│
├── ansible.cfg
├── README.md
├── inventory/
│   └── hosts
│
├── playbooks/
│   ├── baseline.yml
│   ├── docker.yml
│   ├── nginx-container.yml
│   ├── postgresql.yml
│   └── jenkins.yml
│
├── roles/
│   ├── common/
│   ├── docker/
│   ├── nginx/
│   ├── postgresql/
│   └── jenkins/
│
├── group_vars/
├── host_vars/
├── files/
├── templates/
└── docs/
```

---

# Current Features

✅ Passwordless SSH authentication

✅ Centralized Ansible inventory

✅ Role-based Ansible architecture

✅ Baseline Linux configuration

✅ Docker installation and configuration

✅ Docker Python SDK installation

✅ Automated Nginx container deployment

✅ Custom web page deployment

✅ PostgreSQL installation and service management

✅ Dedicated Jenkins server deployment

✅ Idempotent playbooks

---

# Example Commands

Verify all managed servers

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

Deploy Jenkins

```bash
ansible-playbook playbooks/jenkins.yml --ask-become-pass
```

---

# Skills Demonstrated

- Infrastructure as Code (IaC)
- Configuration Management
- Linux Administration
- Docker Containerization
- CI/CD Infrastructure
- PostgreSQL Administration
- SSH Key Authentication
- Git Version Control
- GitHub
- Enterprise Infrastructure Automation
- Idempotent Deployments

---

# Project Roadmap

## Completed

- [x] Ubuntu infrastructure
- [x] SSH key authentication
- [x] Ansible inventory
- [x] Role-based automation
- [x] Docker deployment
- [x] Nginx deployment
- [x] PostgreSQL deployment
- [x] Jenkins server deployment

## In Progress

- [ ] Jenkins Pipeline
- [ ] GitHub Webhooks
- [ ] Automated Application Deployment

## Planned

- [ ] Prometheus
- [ ] Grafana
- [ ] IBM Db2 Automation
- [ ] Kubernetes (k3s)
- [ ] Helm
- [ ] Terraform
- [ ] AWS Infrastructure
- [ ] Azure Infrastructure
- [ ] GCP Infrastructure

---

# Future Enhancements

This project will continue evolving into a complete enterprise DevOps platform by integrating monitoring, container orchestration, cloud infrastructure, and automated CI/CD pipelines.

---

# Author

**Kossi Hevi-Doglan**

DevOps Engineer | Cloud Engineer | Infrastructure Automation

GitHub: https://github.com/khevi
