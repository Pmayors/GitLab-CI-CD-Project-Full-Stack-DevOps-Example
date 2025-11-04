# 🚀 GitLab CI/CD Project: Full-Stack DevOps Example

This project demonstrates a **comprehensive DevOps workflow** built around **GitLab CI/CD** for a **multi-component full-stack application**.  
It integrates **build automation**, **containerization**, **security scanning**, and **configuration management** — showcasing a real-world DevOps pipeline.

---

## 🌟 Project Overview

This repository contains:
- Application source code  
- Configuration files  
- Automation scripts  

Together, they enable you to **build, test, secure, and deploy** the application using a robust CI/CD pipeline.

---

## 🧩 Key Components

| Component | Files / Directories | Description |
|------------|--------------------|--------------|
| **CI/CD Pipeline** | `.gitlab-ci.yml` | Defines the 5-stage GitLab pipeline (`build`, `test`, `security`, `notify`, `docker`) for automated delivery. |
| **Source Code** | `src/` & `pom.xml` | Java source code and Maven Project Object Model for building the application. |
| **Containerization** | `Docker-files/` | Contains the multi-stage Dockerfile used to build the optimized application image. |
| **Local Environment** | `docker-compose.yml` | Defines the multi-container local development environment. |
| **Configuration Management** | `ansible/` | Contains Ansible playbooks for infrastructure and application setup. |

---

## ⚙️ GitLab CI/CD Pipeline Stages

The `.gitlab-ci.yml` defines a **5-stage pipeline** executed by **GitLab Runners**:

### 🏗️ 1. Build
Compiles the Java code using Maven and produces a `.war` artifact.

🧪 2. Test

Runs unit and integration tests using Maven.

mvn test

🛡️ 3. Security

Executes a vulnerability scan with Trivy
 to detect security issues in dependencies and the file system.

trivy fs --format json --output trivy-report.json .

🐳 4. Docker

Performs a multi-stage Docker build and pushes the tagged image to the GitLab Container Registry.

docker login registry.gitlab.com
docker build -t registry.gitlab.com/namespace/project:latest .
docker push registry.gitlab.com/namespace/project:latest

📢 5. Notify

A notification job that triggers on failure to alert the DevOps team when any critical stage fails.

🧰 Tools & Technologies

GitLab CI/CD

Docker & Docker Compose

Maven

Trivy (Security Scanner)

Ansible

Java (Spring / Maven project)

🧑‍💻 How to Use

Clone the repository:

git clone https://github.com/Pmayors/GitLab-CI-CD-Project-Full-Stack-DevOps-Example.git


Build the project locally:

mvn clean package


Spin up the local environment:

docker-compose up -d


Run the CI/CD pipeline automatically on GitLab after pushing your changes.

📈 Future Improvements

Integrate Kubernetes (K8s) for container orchestration

Add Slack / Email notifications for deployment success

Include SonarQube for code quality analysis

🏁 Author

Pmayors

DevOps Engineer | Full-Stack Developer | Cloud Enthusiast 🌐

```bash
mvn clean package
