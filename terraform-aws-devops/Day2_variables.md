
# Variables Demo

```hcl
provider "aws" {
    region = "ap-south-1"  # Set your desired AWS region

}


variable "instance_type" {
  description = "EC2 instance type"
  type        = string
  default     = "t2.micro"
}

# Define an input variable for the EC2 instance AMI ID
variable "ami_id" {
  description = "ami-0287a05f0ef0e9d9a"
  type        = string
}



# Create an EC2 instance using the input variables
resource "aws_instance" "example_instance" {
  ami           = var.ami_id
  instance_type = var.instance_type
}

# Define an output variable to expose the public IP address of the EC2 instance
output "public_ip" {
  description = "Public IP address of the EC2 instance"
  value       = aws_instance.example_instance.public_ip
}

```
###output
```
Apply complete! Resources: 1 added, 0 changed, 0 destroyed.

Outputs:

public_ip = "13.232.45.185"
```

## Summary

Here's how you typically use `.tfvars` files

1. Define your input variables in your Terraform code (e.g., in a `variables.tf` file).

2. Create one or more `.tfvars` files, each containing specific values for those input variables.

3. When running Terraform commands (e.g., terraform apply, terraform plan), you can specify which .tfvars file(s) to use with the -var-file option:

```
terraform apply -var-file=dev.tfvars
```

By using `.tfvars` files, you can keep your Terraform code more generic and flexible while tailoring configurations to different scenarios and environments.


## Conditional Variable Assignment Example

```hcl
variable "environment" {
  description = "Environment type"
  type        = string
  default     = "development"
}

variable "production_subnet_cidr" {
  description = "CIDR block for production subnet"
  type        = string
  default     = "10.0.1.0/24"
}

variable "development_subnet_cidr" {
  description = "CIDR block for development subnet"
  type        = string
  default     = "10.0.2.0/24"
}

resource "aws_security_group" "example" {
  name        = "example-sg"
  description = "Example security group"

  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = var.environment == "production" ? [var.production_subnet_cidr] : [var.development_subnet_cidr]
  }
}

```

In this example, the `locals` block uses a conditional expression to assign a value to the `subnet_cidr` local variable based on the value of the `environment` variable. If `environment` is set to `"production"`, it uses the `production_subnet_cidr` variable; otherwise, it uses the `development_subnet_cidr` variable.

## Conditional Resource Configuration 

```hcl
resource "aws_security_group" "example" {
  name = "example-sg"
  description = "Example security group"

  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = var.enable_ssh ? ["0.0.0.0/0"] : []
  }
}
```

In this example, the `ingress` block within the `aws_security_group` resource uses a conditional expression to control whether SSH access is allowed. If `enable_ssh` is `true`, it allows SSH traffic from any source (`"0.0.0.0/0"`); otherwise, it allows no inbound traffic.

Conditional expressions in Terraform provide a powerful way to make decisions and customize your infrastructure deployments based on various conditions and variables. They enhance the flexibility and reusability of your Terraform configurations.
