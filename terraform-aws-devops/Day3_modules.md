# Modules


## modules\ec2_instance
### main.tf
```
provider "aws" {
    region = "ap-south-1"
  
}

module "ec2" {
    source = "./modules/ec2_instance"
    instance_type = "t2.micro"
    ami_id="ami-0287a05f0ef0e9d9a"
  
}
```

### output.tf

```
output "public-ip" {
   value= aws_instance.example_instance.public_ip
  
}
```

### variables.tf

```

variable "instance_type" {
  description = "EC2 instance type"

}

# Define an input variable for the EC2 instance AMI ID
variable "ami_id" {

}
```

## to use module

# main.tf
```
provider "aws" {
    region = "ap-south-1"
  
}

module "ec2" {
    source = "./modules/ec2_instance"
    instance_type = "t2.micro"
    ami_id="ami-0287a05f0ef0e9d9a"
  
}

```

###  terrafrorm apply
```
module.ec2.aws_instance.example_instance: Creating...
module.ec2.aws_instance.example_instance: Still creating... [10s elapsed]
module.ec2.aws_instance.example_instance: Still creating... [20s elapsed]
module.ec2.aws_instance.example_instance: Creation complete after 23s [id=i-0476bf6220e95cc44]

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.
```
  
