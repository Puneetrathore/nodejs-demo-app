\# Task 3: Infrastructure as Code (IaC) with Terraform



\## Project Overview



This project demonstrates Infrastructure as Code (IaC) by using Terraform to provision and manage a local Docker container.



Terraform uses the Docker provider to pull an Nginx image, create a container, inspect its state, and destroy the resources when they are no longer required.



\## Objectives



\- Provision a Docker container using Terraform.

\- Use `terraform init` to initialize the project.

\- Use `terraform plan` to preview infrastructure changes.

\- Use `terraform apply` to create resources.

\- Inspect infrastructure using Terraform state commands.

\- Use `terraform destroy` to remove managed resources.



\## Tools and Technologies



\- Terraform

\- Docker Desktop

\- Docker provider for Terraform

\- Nginx Alpine image

\- Git and GitHub



\## Project Structure



```text

Task-3-Terraform-Docker/

├── main.tf

├── README.md

├── .gitignore

├── .terraform.lock.hcl

├── logs/

└── screenshots/

```



The `.terraform/` directory and Terraform state files are generated locally and should not be committed.



\## Terraform Configuration



The `main.tf` file defines two resources:



\- `docker\_image.nginx`: manages the Nginx Alpine Docker image.

\- `docker\_container.web`: creates the container named `terraform-nginx-task3`.



The container maps port `8080` on the host to port `80` in the container.



\## Execution Steps



\### 1. Initialize Terraform



```bash

terraform init

```



Downloads the required provider and initializes the Terraform working directory.



\### 2. Preview Changes



```bash

terraform plan

```



Shows the infrastructure changes Terraform intends to make before applying them.



\### 3. Create Infrastructure



```bash

terraform apply

```



Review the plan and enter `yes` when prompted.



\### 4. Verify the Container



```bash

docker ps

terraform state list

terraform state show docker\_container.web

terraform show

```



Open http://localhost:8080 in a browser to verify the Nginx welcome page.



\### 5. Destroy Infrastructure



```bash

terraform destroy

```



Review the plan and enter `yes` when prompted. Verify that the container has been removed:



```bash

docker ps -a

```



\## Execution Logs



The `logs/` directory contains execution output collected during the practical, including initialization, planning, resource inspection, and destruction.



\## Key Outcomes



\- Provisioned a local Docker container using Terraform.

\- Practiced Terraform initialization, planning, and applying changes.

\- Inspected resources tracked in Terraform state.

\- Destroyed the infrastructure using Terraform.

\- Learned how declarative infrastructure configuration supports repeatable resource management.



\## Interview Questions and Answers



\### 1. What is Infrastructure as Code (IaC)?



IaC is the practice of managing and provisioning infrastructure through machine-readable configuration files instead of manually creating resources through graphical interfaces.



\### 2. How does Terraform work?



Terraform reads configuration files, identifies the desired infrastructure, compares it with the current state and real infrastructure, and creates an execution plan. When approved, Terraform calls providers to create, update, or destroy resources.



\### 3. What is a Terraform state file?



Terraform state records information about resources Terraform manages and maps configuration resources to real infrastructure. It helps Terraform determine what changes are required.



\### 4. What is the difference between `terraform plan` and `terraform apply`?



\- `terraform plan` previews proposed infrastructure changes.

\- `terraform apply` executes the changes after approval, unless configured for automatic approval.



\### 5. What are Terraform providers?



Providers are plugins that allow Terraform to interact with platforms and services such as Docker, AWS, Azure, and Google Cloud.



\### 6. What is a resource dependency?



A resource dependency determines the order in which Terraform manages resources. For example, the Docker container references the image resource's `image\_id`, so Terraform creates the image before the container.



\### 7. How do you handle secret variables in Terraform?



Use sensitive input variables and supply secrets through environment variables or a secure secret-management system. Avoid hardcoding credentials or committing secrets and sensitive state files to Git.



\### 8. What are the benefits of Terraform?



\- Repeatable and consistent infrastructure provisioning.

\- Version-controlled infrastructure configuration.

\- Previewing changes before applying them.

\- Resource dependency management.

\- Reusable and maintainable configurations.

\- State tracking for infrastructure management.



\## Author



Puneet Rathore



GitHub: https://github.com/Puneetrathore



