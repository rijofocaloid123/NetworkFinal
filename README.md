Overview

This project demonstrates an automated deployment pipeline for a containerized web application hosted on an Azure Virtual Machine. The deployment process leverages Terraform for infrastructure provisioning, Ansible for configuration management, and GitHub Actions for continuous deployment.

Architecture

The deployment pipeline consists of:

Terraform: Used to provision the Azure infrastructure, including virtual machines, networking, and security configurations.

Ansible: Automates the configuration of the VM, ensuring all necessary dependencies such as Docker are installed.

GitHub Actions: Handles continuous deployment by building, testing, and deploying the application whenever changes are pushed to the repository.

Prerequisites

Before running this project, ensure you have the following installed:

Terraform

Ansible

Docker

An Azure account with necessary permissions

A GitHub repository with Actions enabled

Setup Instructions

1. Clone the Repository

 git clone https://github.com/your-repo.git
 cd your-repo

2. Configure Terraform

Update the terraform.tfvars file with your Azure credentials and desired configuration.

 terraform init
 terraform apply

3. Run Ansible Playbook

After Terraform provisions the VM, use Ansible to configure it:

 ansible-playbook -i inventory.ini setup.yml

4. Configure GitHub Actions

Ensure your GitHub repository has the following secrets set:

AZURE_CREDENTIALS (for authentication with Azure)

DOCKER_USERNAME and DOCKER_PASSWORD (for container registry access)

Push changes to trigger the CI/CD pipeline:

git add .
git commit -m "Initial commit"
git push origin main

Workflow

Terraform provisions the required Azure infrastructure.

Ansible configures the VM, installing necessary dependencies.

GitHub Actions automates the build, test, and deployment of the application.

The application is deployed and accessible via the configured domain or IP.

Contributing

Feel free to submit issues and pull requests to improve the project.# NetworkFinal
