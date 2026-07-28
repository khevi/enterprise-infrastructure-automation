# Enterprise Infrastructure Automation Platform

A production-inspired DevOps platform demonstrating Infrastructure as Code (IaC), CI/CD, monitoring, containerization, and enterprise infrastructure automation using multiple Linux virtual machines.

---

## Overview

This project simulates an enterprise environment where infrastructure, applications, monitoring, and CI/CD are fully automated.

The objective is to demonstrate real-world DevOps practices including:

- Infrastructure as Code (IaC)
- Configuration Management
- Continuous Integration / Continuous Deployment (CI/CD)
- Containerization
- Enterprise Monitoring
- Multi-server Administration
- GitHub Feature Branch Workflow

---

# Enterprise Architecture

The diagram below illustrates the complete platform architecture.

![Enterprise Architecture](docs/architecture.png)

---

# Monitoring Dashboard

The infrastructure is continuously monitored using Prometheus and Grafana.

The dashboard provides real-time visibility into:

- CPU Utilization
- Memory Usage
- Disk Usage
- Network Traffic
- System Load
- Filesystem Capacity
- Host Availability

![Grafana Dashboard](docs/screenshots/grafana-dashboard.png)

---

# Project Infrastructure

| Server | Role | IP Address |
|---------|------|------------|
| ubuntu-lab2 | Ansible Controller | 192.168.40.9 |
| app-lab2 | Docker Application Server | 192.168.40.10 |
| pg-standby2 | PostgreSQL Server | 192.168.40.11 |
| db2-lab2 | IBM Db2 Server | 192.168.40.12 |
| jenkins-lab2 | Jenkins CI/CD | 192.168.40.13 |
| monitoring-lab2 | Prometheus & Grafana | 192.168.40.14 |

---

# Technology Stack

| Category | Technology |
|-----------|------------|
| Source Control | Git |
| Repository | GitHub |
| Automation | Ansible |
| CI/CD | Jenkins |
| Containers | Docker |
| Web Server | Nginx |
| Monitoring | Prometheus |
| Visualization | Grafana |
| Database | PostgreSQL |
| Database | IBM Db2 |
| Operating System | Ubuntu Server 24.04 |
| Virtualization | VirtualBox |

---

# Repository Structure

```
enterprise-infrastructure-automation
│
├── docs
│   ├── architecture.drawio
│   ├── architecture.png
│   └── screenshots
│       ├── grafana-dashboard.png
│       ├── prometheus-targets.png
│       └── jenkins-pipeline-success.png
│
├── inventory
│
├── playbooks
│   ├── baseline.yml
│   ├── docker.yml
│   ├── nginx-container.yml
│   ├── monitoring.yml
│   ├── prometheus.yml
│   └── grafana.yml
│
├── roles
│   ├── common
│   ├── docker
│   ├── nginx
│   ├── monitoring
│   ├── prometheus
│   ├── grafana
│   └── postgresql
│
├── files
│
├── templates
│
└── Jenkinsfile
```

---

# Features

## Infrastructure Automation

- Multi-server Ansible automation
- Modular Ansible roles
- Idempotent playbooks
- SSH key authentication

---

## CI/CD Pipeline

- GitHub Feature Branch workflow
- Jenkins Pipeline
- Automated deployment
- Deployment validation
- Health checks

---

## Docker Deployment

- Automated Nginx deployment
- Container verification
- Application health checks

---

## Monitoring

- Prometheus Server
- Grafana Dashboard
- Node Exporter
- Infrastructure Metrics
- Real-time Monitoring

---

## Databases

- PostgreSQL Server
- IBM Db2 Server

---

# Deployment Workflow

```
Developer

     │

GitHub Feature Branch

     │

Pull Request

     │

Jenkins Pipeline

     │

Ansible

     │

Docker Deployment

     │

Application Validation

     │

Prometheus Monitoring

     │

Grafana Dashboard
```

---

# Monitoring Architecture

```
Node Exporter

    │

Prometheus

    │

Grafana

    │

Enterprise Dashboard
```

---

# Jenkins Pipeline

Current pipeline stages include:

- Checkout Source Code
- Verify Controller Access
- Synchronize Deployment Repository
- Ansible Syntax Validation
- Deploy Application
- Verify Docker Container
- Application Health Check

---

# Monitoring Components

The monitoring platform includes:

- Prometheus
- Grafana
- Node Exporter

Monitored systems:

- ubuntu-lab2
- app-lab2
- pg-standby2
- db2-lab2
- jenkins-lab2
- monitoring-lab2

---

# Current Status

| Component | Status |
|-----------|--------|
| GitHub | ✅ |
| Jenkins | ✅ |
| Ansible | ✅ |
| Docker | ✅ |
| PostgreSQL | ✅ |
| IBM Db2 | ✅ |
| Prometheus | ✅ |
| Grafana | ✅ |

---

# Roadmap

## Completed

- GitHub Repository
- Enterprise Ansible Roles
- Jenkins Pipeline
- Docker Deployment
- PostgreSQL
- IBM Db2
- Prometheus
- Grafana

---

## In Progress

- Repository Documentation
- Custom Grafana Dashboards

---

## Planned

- Kubernetes (k3s)
- Helm
- GitHub Actions
- ArgoCD
- Terraform
- AWS
- Azure
- Google Cloud Platform

---

# Skills Demonstrated

- Linux Administration
- Infrastructure Automation
- Configuration Management
- Continuous Integration
- Continuous Deployment
- Docker
- Monitoring
- Observability
- Git Workflow
- Enterprise Documentation

---

# Author

**Kossi Hevi-Doglan**

Enterprise DevOps Engineer

GitHub:
https://github.com/khevi

LinkedIn:
https://www.linkedin.com/in/philippe-hevi-94151660/

---

## License

This project is provided for educational and portfolio purposes.
