# Terraform State Drift Recovery Lab

This project simulates a real-world Terraform state drift issue and demonstrates how to recover from it safely and cleanly using `terraform state rm`.

##  Tools Used

- Terraform
- AWS EC2 t2.micro 
- AWS Console
- Git + GitHub

##  What It Does

- Provisions an EC2 instance using Terraform
- Manually deletes the instance in the AWS Console (simulating state drift)
- Uses `terraform state rm` to remove the broken reference from Terraform state
- Redeploys the instance cleanly with `terraform apply`

##  Terraform Workflow

```bash
terraform init
terraform apply
# Manual deletion of EC2 in AWS Console
terraform plan              # shows drift
terraform state list
terraform state rm aws_instance.example
terraform apply             # redeploys instance
