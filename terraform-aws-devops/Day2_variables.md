
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

#####################################
## main.tf
```
provider "aws" {
    region = "ap-south-1"  # Set your desired AWS region

}


# Create an EC2 instance using the input variables
resource "aws_instance" "example_instance" {
  ami           = var.ami_id
  instance_type = var.instance_type
}

```
## ouput.tf

```
output "public-ip" {
   value= aws_instance.example_instance.public_ip
  
}
```

## variables.tf
```

variable "instance_type" {
  description = "EC2 instance type"

}

# Define an input variable for the EC2 instance AMI ID
variable "ami_id" {

}
```
## terraform.tfvars
```
instance_type="t2.micro"
ami_id="ami-0287a05f0ef0e9d9a"
```
## terraform apply

```

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.

Outputs:

public-ip = "3.108.44.100"
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

# Built-in Functions

Terraform is an infrastructure as code (IaC) tool that allows you to define and provision infrastructure resources in a declarative manner. Terraform provides a wide range of built-in functions that you can use within your configuration files (usually written in HashiCorp Configuration Language, or HCL) to manipulate and transform data. These functions help you perform various tasks when defining your infrastructure. Here are some commonly used built-in functions in Terraform:

1. `concat(list1, list2, ...)`: Combines multiple lists into a single list.

```hcl
variable "list1" {
  type    = list
  default = ["a", "b"]
}

variable "list2" {
  type    = list
  default = ["c", "d"]
}

output "combined_list" {
  value = concat(var.list1, var.list2)
}
```

2. `element(list, index)`: Returns the element at the specified index in a list.

```hcl
variable "my_list" {
  type    = list
  default = ["apple", "banana", "cherry"]
}

output "selected_element" {
  value = element(var.my_list, 1) # Returns "banana"
}
```

3. `length(list)`: Returns the number of elements in a list.

```hcl
variable "my_list" {
  type    = list
  default = ["apple", "banana", "cherry"]
}

output "list_length" {
  value = length(var.my_list) # Returns 3
}
```

4. `map(key, value)`: Creates a map from a list of keys and a list of values.

```hcl
variable "keys" {
  type    = list
  default = ["name", "age"]
}

variable "values" {
  type    = list
  default = ["Alice", 30]
}

output "my_map" {
  value = map(var.keys, var.values) # Returns {"name" = "Alice", "age" = 30}
}
```

5. `lookup(map, key)`: Retrieves the value associated with a specific key in a map.

```hcl
variable "my_map" {
  type    = map(string)
  default = {"name" = "Alice", "age" = "30"}
}

output "value" {
  value = lookup(var.my_map, "name") # Returns "Alice"
}
```

6. `join(separator, list)`: Joins the elements of a list into a single string using the specified separator.

```hcl
variable "my_list" {
  type    = list
  default = ["apple", "banana", "cherry"]
}

output "joined_string" {
  value = join(", ", var.my_list) # Returns "apple, banana, cherry"
}
```

These are just a few examples of the built-in functions available in Terraform. You can find more functions and detailed documentation in the official Terraform documentation, which is regularly updated to include new features and improvements



# PROJECT-vpc-with-ec2

## provider.tf
```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "5.11.0"
    }
  }
}

provider "aws" {
  # Configuration options
  region = "us-east-1"
}
```

## userdata.sh

```
#!/bin/bash
apt update
apt install -y apache2

# Get the instance ID using the instance metadata
INSTANCE_ID=$(curl -s http://169.254.169.254/latest/meta-data/instance-id)

# Install the AWS CLI
apt install -y awscli

# Download the images from S3 bucket
#aws s3 cp s3://myterraformprojectbucket2023/project.webp /var/www/html/project.png --acl public-read

# Create a simple HTML file with the portfolio content and display the images
cat <<EOF > /var/www/html/index.html
<!DOCTYPE html>
<html>
```

## variables.tf
```
variable "cidr" {
  default = "10.0.0.0/16"
}
```

## main.tf
```
resource "aws_vpc" "myvpc" {
  cidr_block = var.cidr
}

resource "aws_subnet" "sub1" {
  vpc_id                  = aws_vpc.myvpc.id
  cidr_block              = "10.0.0.0/24"
  availability_zone       = "us-east-1a"
  map_public_ip_on_launch = true
}

resource "aws_subnet" "sub2" {
  vpc_id                  = aws_vpc.myvpc.id
  cidr_block              = "10.0.1.0/24"
  availability_zone       = "us-east-1b"
  map_public_ip_on_launch = true
}

resource "aws_internet_gateway" "igw" {
  vpc_id = aws_vpc.myvpc.id
}

resource "aws_route_table" "RT" {
  vpc_id = aws_vpc.myvpc.id

  route {
    cidr_block = "0.0.0.0/0"
    gateway_id = aws_internet_gateway.igw.id
  }
}

resource "aws_route_table_association" "rta1" {
  subnet_id      = aws_subnet.sub1.id
  route_table_id = aws_route_table.RT.id
}

resource "aws_route_table_association" "rta2" {
  subnet_id      = aws_subnet.sub2.id
  route_table_id = aws_route_table.RT.id
}

resource "aws_security_group" "webSg" {
  name   = "web"
  vpc_id = aws_vpc.myvpc.id

  ingress {
    description = "HTTP from VPC"
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
  ingress {
    description = "SSH"
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }

  tags = {
    Name = "Web-sg"
  }
}

resource "aws_s3_bucket" "example" {
  bucket = "abhisheksterraform2023project"
}


resource "aws_instance" "webserver1" {
  ami                    = "ami-0261755bbcb8c4a84"
  instance_type          = "t2.micro"
  vpc_security_group_ids = [aws_security_group.webSg.id]
  subnet_id              = aws_subnet.sub1.id
  user_data              = base64encode(file("userdata.sh"))
}

resource "aws_instance" "webserver2" {
  ami                    = "ami-0261755bbcb8c4a84"
  instance_type          = "t2.micro"
  vpc_security_group_ids = [aws_security_group.webSg.id]
  subnet_id              = aws_subnet.sub2.id
  user_data              = base64encode(file("userdata1.sh"))
}

#create alb
resource "aws_lb" "myalb" {
  name               = "myalb"
  internal           = false
  load_balancer_type = "application"

  security_groups = [aws_security_group.webSg.id]
  subnets         = [aws_subnet.sub1.id, aws_subnet.sub2.id]

  tags = {
    Name = "web"
  }
}

resource "aws_lb_target_group" "tg" {
  name     = "myTG"
  port     = 80
  protocol = "HTTP"
  vpc_id   = aws_vpc.myvpc.id

  health_check {
    path = "/"
    port = "traffic-port"
  }
}

resource "aws_lb_target_group_attachment" "attach1" {
  target_group_arn = aws_lb_target_group.tg.arn
  target_id        = aws_instance.webserver1.id
  port             = 80
}

resource "aws_lb_target_group_attachment" "attach2" {
  target_group_arn = aws_lb_target_group.tg.arn
  target_id        = aws_instance.webserver2.id
  port             = 80
}

resource "aws_lb_listener" "listener" {
  load_balancer_arn = aws_lb.myalb.arn
  port              = 80
  protocol          = "HTTP"

  default_action {
    target_group_arn = aws_lb_target_group.tg.arn
    type             = "forward"
  }
}

output "loadbalancerdns" {
  value = aws_lb.myalb.dns_name
}

```


