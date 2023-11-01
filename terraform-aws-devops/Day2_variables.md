
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
