# System Administration & Deployment Automation with Ansible 🤖⚙️

This project showcases the power of **Infrastructure as Code (IaC)** using **Ansible**. It automates complex system administration tasks, including user provisioning, security configurations, and application deployments, ensuring environment consistency across multiple servers.

## 🛠️ Tech Stack
* **Automation Engine:** Ansible
* **Configuration Language:** YAML
* **Target Environments:** macOS, Linux (Ubuntu/CentOS)
* **Key Modules:** `user`, `file`, `copy`, `docker_compose`, `become` (Privilege Escalation)

## ✨ Key Features & Capabilities

### 1. Automated User Provisioning
The playbook automatically creates a dedicated system user (`devops_hiru`) with customized shell environments and group permissions. This eliminates manual errors in user management.

### 2. Secure Privilege Escalation
Utilizes the `become` (sudo) method to perform administrative tasks securely, demonstrating a clear understanding of system security and access control.

### 3. Automated Application Deployment
- Creates standardized directory structures with strict permission sets (`0755`).
- Deploys application configuration files automatically.
- Orchestrates Docker-based services (Prometheus/Grafana) using Ansible's Docker modules.

### 4. Idempotency & Reliability
Ansible ensures that the system state is only modified if it deviates from the desired configuration. If the user or app already exists, Ansible skips the task to maintain system stability.

## 🏗️ Project Structure

```plaintext
.
├── hosts                 # Inventory file defining target servers
├── setup-system.yml      # Playbook for user & app setup
├── deploy-monitor.yml    # Playbook for Docker monitoring stack
└── README.md             # Project documentation

🚀 How to Use
1. Prerequisites

Ensure Ansible is installed on your control node:

Bash
brew install ansible
2. Run the System Setup Playbook

To create the user and deploy the app with administrative privileges:

Bash
ansible-playbook -i hosts setup-system.yml --ask-become-pass
3. Deploy the Monitoring Stack

To automatically launch the Docker-based monitoring services:

Bash
ansible-playbook -i hosts deploy-monitor.yml

## 📸 Automation preview

Here is the successful execution of the system setup playbook:

![Ansible Playbook Output](ansible-output.jpg)


Developed by Hiruka Warnakula - Final-year IT Student