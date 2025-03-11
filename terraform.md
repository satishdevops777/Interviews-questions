# TERRAFORM

1. What is Terraform, and how does it work?
```
Answer: Terraform is an Infrastructure as Code (IaC) tool that allows you to provision, manage, and automate infrastructure using declarative configuration files.
```
2. What are Terraform Providers?
```
Answer: Providers are plugins that interact with cloud platforms (AWS, GCP, Azure). Example: provider "aws" { region = "us-east-1" }.
```
3. What is the Terraform state file, and why is it important?
```
Answer: The state file (terraform.tfstate) tracks resources managed by Terraform, preventing conflicts when applying changes.
```
4. Explain the difference between terraform plan and terraform apply.
```
Answer:
terraform plan: Shows the execution plan without making changes.
terraform apply: Applies the configuration to create/update resources.
```
5. How do you define variables in Terraform?
```
Answer:
variable "instance_type" {
  default = "t2.micro"
}
```
6. What is the difference between Terraform modules and workspaces?
```
Answer:
Modules: Reusable Terraform configurations.
Workspaces: Isolated environments (e.g., dev, prod).
```
7. How do you manage secrets in Terraform?
```
Answer: Using HashiCorp Vault, AWS Secrets Manager, or .tfvars (never commit secrets to Git).
```
8. What is Terraform backend?
```
Answer: The backend stores Terraform state remotely (e.g., S3, Azure Blob Storage).
```
9. How do you destroy Terraform-managed infrastructure?
```
Answer: terraform destroy
```
10. How do you handle dependencies between resources in Terraform?
```
Answer: Use depends_on to define explicit dependencies.
```
11. Coding Task Write a Terraform script to create an AWS EC2 instance.
```
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "web" {
  ami           = "ami-12345678"
  instance_type = "t2.micro"
  tags = {
    Name = "Terraform-Instance"
  }
}
```
