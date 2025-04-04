# Terraform State Drift Recovery Lab

This project simulates a real-world Terraform state drift issue and demonstrates how to recover from it safely and cleanly using `terraform state rm`.

##  Tools Used

- **Terraform** (Infrastructure as Code)
- **AWS EC2** (`t2.micro')
- **AWS CLI** and Web Console
- **Git & GitHub**

##  Objective

Provision an EC2 instance using Terraform, simulate state drift by manually deleting the instance via the AWS Console, and recover the infrastructure using Terraform’s state management workflow.

##  Key Concepts Demonstrated

- Provider configuration and modular `.tf` structure (`main.tf`, `variables.tf`, `outputs.tf`)
- Understanding and handling Terraform state drift
- Usage of `terraform state list` and `terraform state rm`
- Clean re-deployment of drifted infrastructure using `terraform apply`
- Git best practices and `.gitignore` to prevent large binary files (e.g., `.terraform/`) from polluting the repository

##  Workflow Summary

```bash
# Initialize Terraform
terraform init

# Apply infrastructure (provisions EC2 instance)
terraform apply

# Simulate state drift by manually deleting the EC2 instance in the AWS Console

# Identify drift
terraform plan

# Inspect Terraform state
terraform state list

# Remove orphaned resource from state
terraform state rm aws_instance.example

# Re-deploy the EC2 instance
terraform apply

## Project Structure 

terraform-state-recovery-lab/
├── main.tf
├── variables.tf
├── outputs.tf
├── .gitignore
└── README.md
