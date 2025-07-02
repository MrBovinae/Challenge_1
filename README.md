# 🚀 Fullstack AWS CI/CD Pipeline with Jenkins, ECS, Docker & Terraform

This project demonstrates how to **build and deploy a React frontend and Express backend** in Docker containers using **AWS ECS**, orchestrated by **Jenkins CI/CD**, and fully provisioned with **Terraform**.

---

## 🧭 Architecture Overview

**Stack Includes:**

- **Frontend:** React (Dockerized)
- **Backend:** Express.js (Dockerized)
- **CI/CD:** Jenkins (on EC2) with AWS CLI & Docker
- **Infrastructure:** AWS ECS (Fargate), ECR, ALB, S3, IAM Roles, VPC
- **IaC Tool:** Terraform

***Build and deploy a React frontend and Express backend in Docker containers on AWS ECS, managed by Jenkins CI/CD, all provisioned with Terraform.***


✅ 1. Deploy a Jenkins Server (Manually)
What you need to do:
Launch an EC2 instance that will host Jenkins.


Install Jenkins and make it publicly accessible via a browser.


Manually create required IAM roles (e.g., for ECS deploy, pushing to ECR, etc.)


Configure Jenkins with needed plugins (e.g., Git, Docker, AWS CLI)


Helpful Tips:
Use an Amazon Linux 2 or Ubuntu EC2.


Install Jenkins with yum or apt and expose port 8080.


You might need to open the port in the EC2 Security Group.



✅ 2. Containerize the Frontend and Backend
What you need to do:
The repo already has a React frontend and an Express backend.


Write Dockerfiles for both frontend and backend.


Build and run the containers locally to test.


Helpful Tips:
Use multi-stage builds for React if needed.


Backend Dockerfile example:
✅ 3. Push Images to ECR
What you need to do:
Create 2 Elastic Container Registry (ECR) repositories (1 for frontend, 1 for backend).


Push the built images to ECR from Jenkins or your local machine.

✅ 4. Provision ECS Infrastructure with Terraform
What you need to do:


**✅Something to Consider:**
You can use **Terraform to automate steps 1 through 3**, including provisioning the EC2 instance for Jenkins and creating a key pair for secure access. Before launching any infrastructure, be sure to run:

* `terraform init` – to initialize your working directory and download required providers.
* `terraform plan` – to preview the resources Terraform will create, change, or destroy.

This gives you a clear view of what’s about to happen **before you actually apply anything**.

Once everything looks good, you can proceed with `terraform apply` to spin up your infrastructure.

After that, use the **AWS CLI (`aws configure`)** to set up your credentials, and then connect to your Jenkins EC2 instance to install and configure Jenkins manually or via a provisioning script. From this point forward, all deployments and CI/CD workflows can be managed right from your terminal or Jenkins dashboard.

---

✅ 5. Create a Jenkins CI/CD Pipeline
What you need to do:
Write a Jenkinsfile in the repo to:


Build Docker images for both apps.


Push images to ECR.


Update ECS task definitions to use new images.


Deploy via ECS (you can use aws ecs update-service or Terraform apply).

✅ 6. Documentation







