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

#### main.tf
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

# terraform registry

![image](https://github.com/rkrath123/devops/assets/53966749/cd2663aa-36db-4930-95a0-6168c888e956)

### EC2 instance create

```
provider "aws" {
    region = "ap-south-1"
  
}

module "ec2-instance" {
  source  = "terraform-aws-modules/ec2-instance/aws"
  version = "5.5.0"
  instance_type="t2.nano"
  monitoring = true
  ami="ami-0287a05f0ef0e9d9a"

}
```

### Multiple EC2 Instance
```
module "ec2_instance" {
  source  = "terraform-aws-modules/ec2-instance/aws"

  for_each = toset(["one", "two", "three"])

  name = "instance-${each.key}"

  instance_type          = "t2.micro"
  key_name               = "user1"
  monitoring             = true
  vpc_security_group_ids = ["sg-12345678"]
  subnet_id              = "subnet-eddcdzz4"

  tags = {
    Terraform   = "true"
    Environment = "dev"
  }
}
```

### EKS Modules

![image](https://github.com/rkrath123/devops/assets/53966749/e4938ef2-74fd-4f8c-a466-2a9e7badc947)

```
provider "aws" {
    region  = "us-east-1"
    version = "2.3.0"
  }
  
  module "eks_k8s1" {
    source  = "terraform-aws-modules/eks/aws"
    version = "2.3.1"
  
    cluster_version = "1.12"
  
    cluster_name = "k8s"
    Vpc_id = "vpc-00000000"
  
    subnets = ["subnet-00000001", "subnet-000000002", "subnet-000000003"]
  
    cluster_endpoint_private_access = "true"
    cluster_endpoint_public_access  = "true"
  
    write_kubeconfig      = true
    config_output_path    = "/.kube/"
    manage_aws_auth       = true
    write_aws_auth_config = true
  
    map_users = [
      {
        user_arn = "arn:aws:iam::12345678901:user/user1"
        username = "user1"
        group    = "system:masters"
      },
    ]
  
    worker_groups = [
      {
        name                 = "workers"
        instance_type        = "t2.large"
        asg_min_size         = 3
        asg_desired_capacity = 3
        asg_max_size         = 3
        root_volume_size     = 100
        root_volume_type     = "gp2"
        ami_id               = "ami-0000000000"
        ebs_optimized     = false
        key_name          = "all"
        enable_monitoring = false
      },
    ]
  
    tags = {
      Cluster = "k8s"
    }
  }
```
