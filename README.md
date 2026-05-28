# Dockerized Apache Airflow Setup

## Overview

This project provides a production-style local Apache Airflow environment using Docker Compose and PostgreSQL. It is designed for workflow orchestration, ETL pipeline development, and local platform engineering practice.

The setup includes:

* Apache Airflow Webserver
* Airflow Scheduler
* PostgreSQL Metadata Database
* Dockerized local deployment
* Automated local environment setup
* Python virtual environment management using pyenv and venv

This repository is intended for learning, development, testing, and showcasing platform engineering and DevOps concepts.

---

# Architecture

```text
+-----------------------+
|       Browser         |
|  http://localhost     |
+-----------+-----------+
            |
            v
+-----------------------+
| Airflow Webserver     |
+-----------+-----------+
            |
            v
+-----------------------+
| Airflow Scheduler     |
+-----------+-----------+
            |
            v
+-----------------------+
| PostgreSQL Metadata DB|
+-----------------------+
```

---

# Tech Stack

| Technology           | Purpose                       |
| -------------------- | ----------------------------- |
| Apache Airflow 2.8.1 | Workflow orchestration        |
| Docker               | Containerization              |
| Docker Compose       | Multi-container orchestration |
| PostgreSQL 13        | Airflow metadata database     |
| Python 3.11          | Local development environment |
| pyenv                | Python version management     |
| venv                 | Dependency isolation          |
| VS Code              | Development environment       |

---

# Features

* Dockerized Airflow deployment
* PostgreSQL metadata backend
* Automated local setup workflow
* Python virtual environment support
* Sample ETL DAG implementation
* Structured project organization
* Git branch protection workflow
* Local development isolation
* Production-style architecture layout

---

# Project Structure

```text
dockerized-airflow-setup/
│
├── dags/
│   └── sample_etl_dag.py
│
├── configs/
│
├── scripts/
│   └── start_local_env.py
│
├── plugins/
│
├── logs/
│
├── screenshots/
│
├── .env
├── .gitignore
├── .python-version
├── docker-compose.yml
├── requirements.txt
└── README.md
```

---

# Prerequisites

Ensure the following tools are installed before running the project.

## Required Tools

* Git
* Docker Desktop
* Python 3.11
* pyenv
* VS Code (recommended)

---

# Docker Installation

Install Docker Desktop:

https://www.docker.com/products/docker-desktop/

Verify installation:

```bash
docker --version
docker compose version
```

---

# Python Setup

## Install Python 3.11 using pyenv

```bash
pyenv install 3.11
```

## Set local Python version

Inside project folder:

```bash
pyenv local 3.11
```

Verify:

```bash
python --version
```

Expected output:

```text
Python 3.11.x
```

---

# Local Setup Instructions

## 1. Clone Repository

```bash
git clone https://github.com/<your-github-username>/dockerized-airflow-setup.git
```

Move into project directory:

```bash
cd dockerized-airflow-setup
```

---

## 2. Create Virtual Environment

```bash
python -m venv venv
```

---

## 3. Activate Virtual Environment

### Windows PowerShell

```powershell
.\venv\Scripts\Activate.ps1
```

### Windows CMD

```cmd
venv\Scripts\activate.bat
```

---

## 4. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# Run Airflow Environment

## Start All Services

```bash
docker compose up -d
```

This starts:

* PostgreSQL
* Airflow initialization service
* Airflow webserver
* Airflow scheduler

---

## Verify Running Containers

```bash
docker ps -a
```

Expected containers:

* airflow-postgres
* airflow-init
* airflow-webserver
* airflow-scheduler

---

# Access Airflow UI

Open browser:

```text
http://localhost:8080
```

## Default Credentials

| Username | Password |
| -------- | -------- |
| admin    | admin    |

---

# Sample DAG

The repository includes a sample ETL workflow DAG.

File:

```text
dags/sample_etl_dag.py
```

Workflow:

```text
Extract → Transform → Load
```

Features demonstrated:

* DAG scheduling
* PythonOperator
* Task dependencies
* ETL orchestration

---

# Useful Commands

## Stop Services

```bash
docker compose down
```

---

## Remove Containers and Volumes

```bash
docker compose down -v
```

---

## Restart Services

```bash
docker compose restart
```

---

## View Logs

```bash
docker compose logs
```

---

## View Specific Service Logs

```bash
docker logs airflow-webserver
```

---

# Git Workflow

This repository follows a protected branch workflow.

## Branches

| Branch    | Purpose                      |
| --------- | ---------------------------- |
| main      | Stable production-ready code |
| dev       | Active development           |
| feature/* | Feature development          |

## Main Branch Protection

* Pull request required
* Linear history enabled
* Force pushes blocked

---

# Future Improvements

Planned enhancements include:

* CI/CD integration
* GitHub Actions pipelines
* Airflow monitoring and alerting
* CeleryExecutor setup
* NGINX reverse proxy
* Kubernetes deployment
* Terraform integration
* Secrets management
* Prometheus/Grafana monitoring

---

# Learning Objectives

This project demonstrates:

* Docker container orchestration
* Airflow architecture setup
* Platform engineering workflow
* Local environment automation
* Python dependency isolation
* Infrastructure troubleshooting
* Git branch protection strategy
* DevOps development practices

---

# Author

Chinmay Karnekar

Databricks Platform Engineer | AWS Cloud & Data Platform Engineering
