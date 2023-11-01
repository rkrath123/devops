## create instance
```
provider "aws" {
    region = "ap-south-1"  # Set your desired AWS region
    access_key = ""
     secret_key = "uW6p0GzBPhH1Wa0vuxRY+"
}

resource "aws_instance" "example" {
    ami           = "ami-0287a05f0ef0e9d9a"  # Specify an appropriate AMI ID
    instance_type = "t2.micro"
    key_name = "mobaxtreme"
}
```

## Multiple Providers

You can use multiple providers in one single terraform project. For example,


1. Create a providers.tf file in the root directory of your Terraform project.
2. In the providers.tf file, define the AWS and Azure providers. For example:


```
provider "aws" {
  region = "us-east-1"
}

provider "azurerm" {
  subscription_id = "your-azure-subscription-id"
  client_id = "your-azure-client-id"
  client_secret = "your-azure-client-secret"
  tenant_id = "your-azure-tenant-id"
}
```

3. In your other Terraform configuration files, you can then use the aws and azurerm providers to create resources in AWS and Azure, respectively,

```
resource "aws_instance" "example" {
  ami = "ami-0123456789abcdef0"
  instance_type = "t2.micro"
}

resource "azurerm_virtual_machine" "example" {
  name = "example-vm"
  location = "eastus"
  size = "Standard_A1"
}
```

## Multiple Region Implementation in Terraform
```
provider "aws" {
    region = "ap-south-1"  # Set your desired AWS region
    alias = "ap-south-1"
}

provider "aws" {
  alias = "us-east-1"
  region = "us-east-1"
}

resource "aws_instance" "example1" {
    ami = "ami-0fc5d935ebf8bc3bc"
    instance_type = "t2.micro"
    provider = aws.us-east-1
}

resource "aws_instance" "example2" {
    ami = "ami-0287a05f0ef0e9d9a"  # Specify an appropriate AMI ID
    instance_type = "t2.micro"
    key_name = "mobaxtreme"
    provider = aws.ap-south-1
}
```

## Provider Configuration

The required_providers block in Terraform is used to declare and specify the required provider configurations for your Terraform module or configuration. It allows you to specify the provider name, source, and version constraints.

```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 3.0"
    }
    azurerm = {
      source  = "hashicorp/azurerm"
      version = ">= 2.0, < 3.0"
    }
  }
}
```
