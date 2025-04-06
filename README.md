# 🚀 Monitoring Server Provisioning with Terraform + Jenkins + SonarQube

This project provisions a fully configured EC2 instance using **Terraform** on AWS, then bootstraps it with **Jenkins**, **SonarQube**, **Docker**, **Trivy**, **Terraform CLI**, **kubectl**, **AWS CLI**, and **eksctl**.

---

## 📦 Stack Used

- Terraform
- AWS EC2
- Bash (for provisioning via `user_data`)
- Jenkins (CI/CD)
- SonarQube (Code Quality)
- Docker (Container Runtime)
- Trivy (Security Scanner)
- kubectl (Kubernetes CLI)
- AWS CLI
- eksctl (EKS Manager)

---

## 📁 Files & Purpose

| File            | Description |
|-----------------|-------------|
| `main.tf`       | Terraform config for EC2 instance and Security Group |
| `variables.tf`  | Variables for customization (key name, instance name, etc.) |
| `output.tf`     | Prints EC2 Public IP after deployment |
| `installation.sh` | User data script for setting up all required tools on EC2 |

---

## 🔧 Pre-requisites

- [AWS Account](https://aws.amazon.com/)
- An existing **key pair** (EC2 > Key Pairs)
- [Terraform Installed](https://developer.hashicorp.com/terraform/downloads)
- IAM User with EC2 permissions (or set access via AWS CLI/profile)

---

## 🚀 How to Use

1. **Clone this repository:**

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

2. **Configure your AWS credentials (optional)**

Update `variables.tf`:

```hcl
variable "access_key" {
  default = "YOUR_AWS_ACCESS_KEY"
}

variable "secret_key" {
  default = "YOUR_AWS_SECRET_KEY"
}
```

**Or** use an AWS CLI Profile.

3. **Initialize Terraform:**

```bash
terraform init
```

4. **Review the plan:**

```bash
terraform plan
```

5. **Apply the configuration:**

```bash
terraform apply
```

Type `yes` to confirm.

---

## 🖥️ What It Does

- Launches an EC2 instance (`t2.medium`) using the specified AMI  
- Creates a Security Group for:
  - SSH (22)  
  - Jenkins (8080)  
  - SonarQube (9000)  
- Installs:
  - Jenkins  
  - SonarQube  
  - Docker  
  - Trivy  
  - Terraform  
  - kubectl  
  - AWS CLI  
  - eksctl  
- Outputs the public IP of the instance
