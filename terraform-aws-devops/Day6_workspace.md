# Terraform workspace


### modules/ec2_instance

```
provider "aws" {
    region = "us-east-1"
}

variable "ami" {
  description = "This is AMI for the instance"
}

variable "instance_type" {
  description = "This is the instance type, for example: t2.micro"
}

resource "aws_instance" "example" {
    ami = var.ami
    instance_type = var.instance_type
}

```
### main.tf
```
provider "aws" {
  region = "us-east-1"
}

variable "ami" {
  description = "value"
}

variable "instance_type" {
  description = "value"
  type = map(string)

  default = {
    "dev" = "t2.micro"
    "stage" = "t2.medium"
    "prod" = "t2.xlarge"
  }
}

module "ec2_instance" {
  source = "./modules/ec2_instance"
  ami = var.ami
  instance_type = lookup(var.instance_type, terraform.workspace, "t2.micro")
}
```

### terraform.tfvars

```
ami = "ami-053b0d53c279acc90"
```

