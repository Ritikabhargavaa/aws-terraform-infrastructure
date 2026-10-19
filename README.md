# ☁️ AWS Infrastructure Automation with Terraform

<p align="center">
  <b>Building scalable, highly available AWS infrastructure — one Terraform configuration at a time.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Cloud-AWS-orange?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/IaC-Terraform-7B42BC?logo=terraform&logoColor=white" />
  <img src="https://img.shields.io/badge/Compute-EC2-orange?logo=amazonec2&logoColor=white" />
  <img src="https://img.shields.io/badge/Networking-VPC-blue" />
  <img src="https://img.shields.io/badge/Architecture-High%20Availability-success" />
</p>

---

## 🚀 Project Overview

What if you could build an entire AWS infrastructure without manually creating every resource through the AWS Console?

This project demonstrates **Infrastructure as Code (IaC)** using Terraform to provision AWS resources and deploy two application instances across different Availability Zones. An Application Load Balancer distributes incoming traffic between the instances, helping improve availability and scalability.

The goal is to create a repeatable, organized, and easier-to-manage cloud infrastructure using real-world DevOps practices.

## 🏗️ Architecture

The infrastructure is designed around an Amazon VPC containing two application instances distributed across separate Availability Zones.

**Architecture flow:**

`User → Application Load Balancer → EC2 Instance 1 / EC2 Instance 2`

Supporting infrastructure includes VPC networking, public subnets, routing, security groups, and an optional Amazon S3 bucket for storing Terraform state remotely.

<!-- Add your architecture diagram below -->
<!-- Save your image in the repository as architecture.png -->

<p align="center">
  <img src="AWS Terraform Infra.jpg" alt="AWS infrastructure provisioned using Terraform" width="850"/>
</p>

## 🎯 Project Objectives

- Automate AWS infrastructure provisioning with Terraform.
- Create a custom Virtual Private Cloud (VPC).
- Deploy two EC2 instances across different Availability Zones.
- Configure an Application Load Balancer (ALB) to distribute application traffic.
- Configure security groups and networking components.
- Explore remote Terraform state management using Amazon S3.
- Practice reusable, version-controlled Infrastructure as Code.

## 🧰 Technology Stack

| Technology | Purpose |
|---|---|
| AWS VPC | Isolated cloud networking |
| Amazon EC2 | Hosts application instances |
| Application Load Balancer | Distributes incoming HTTP/HTTPS traffic |
| Availability Zones | Improves infrastructure resilience |
| Security Groups | Controls inbound and outbound traffic |
| Terraform | Automates infrastructure provisioning |
| Amazon S3 | Optional remote Terraform state storage |
| Git & GitHub | Version control and project documentation |

## 📁 Suggested Project Structure

```text
aws-terraform-infrastructure/
├── main.tf
├── variables.tf
├── outputs.tf
├── providers.tf
├── terraform.tfvars.example
├── .gitignore
├── README.md
└── architecture.png
```

*The structure above is a suggested layout; adjust it to match your actual repository.*

## ⚙️ How It Works

**1. Configure the AWS provider**

Set up the AWS provider and region for Terraform.

**2. Build the VPC**

Create the network environment, subnets, and required routing resources.

**3. Deploy EC2 instances**

Provision two instances in separate Availability Zones and configure the application on each instance.

**4. Configure the load balancer**

Create the ALB, target group, health checks, and listener to distribute incoming requests.

**5. Provision the infrastructure**

Use Terraform to initialize, validate, plan, and apply the configuration.

**6. Verify the deployment**

Access the load balancer DNS endpoint and verify that the application responds successfully.

## 💻 Deployment Guide

### Prerequisites

- An AWS account with appropriate IAM permissions.
- AWS CLI installed and configured.
- Terraform installed.
- Git installed.

### Step 1: Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd aws-terraform-infrastructure
```

### Step 2: Configure AWS credentials

```bash
aws configure
```

Use an IAM identity with the permissions required for the resources being created. Avoid hardcoding credentials in Terraform files.

### Step 3: Initialize Terraform

```bash
terraform init
```

### Step 4: Validate the configuration

```bash
terraform fmt -recursive
terraform validate
```

### Step 5: Review the execution plan

```bash
terraform plan
```

### Step 6: Create the infrastructure

```bash
terraform apply
```

Review the proposed changes and confirm when prompted.

### Step 7: Clean up resources

When finished testing, remove the resources managed by this configuration:

```bash
terraform destroy
```

Review the destruction plan carefully before confirming.

## 🔐 Security Best Practices

- Use IAM roles and least-privilege permissions.
- Never commit AWS access keys, secrets, or sensitive `.tfvars` files.
- Restrict security group rules to the required ports and trusted sources.
- Prefer HTTPS for production-facing applications.
- Enable appropriate Terraform state access controls and encryption when using S3.
- Use remote state locking supported by your Terraform backend configuration.

## 📈 Learning Outcomes

By completing this project, you can practice:

- AWS networking and compute fundamentals.
- Terraform configuration and resource dependencies.
- Multi-AZ deployment concepts.
- Load balancing and health checks.
- Infrastructure lifecycle management.
- Cloud security and DevOps automation.

## 🧹 Cost Management

AWS resources such as EC2 instances, load balancers, public IPv4 addresses, and NAT Gateways may incur charges. Check the pricing for your selected region and remove unused resources after testing.

## 👩‍💻 Author

**Ritika Bhargava**

Aspiring Cloud & DevOps Engineer

Exploring AWS, Terraform, containerization, automation, and cloud infrastructure.

---

⭐ If you find this project useful, consider starring the repository.

*Built to learn, automate, and understand cloud infrastructure through hands-on practice.*
