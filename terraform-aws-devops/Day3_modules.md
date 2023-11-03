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
module "eks" {
  source  = "terraform-aws-modules/eks/aws"
  version = "~> 19.0"

  cluster_name    = "my-cluster"
  cluster_version = "1.27"

  cluster_endpoint_public_access  = true

  cluster_addons = {
    coredns = {
      most_recent = true
    }
    kube-proxy = {
      most_recent = true
    }
    vpc-cni = {
      most_recent = true
    }
  }

  vpc_id                   = "vpc-1234556abcdef"
  subnet_ids               = ["subnet-abcde012", "subnet-bcde012a", "subnet-fghi345a"]
  control_plane_subnet_ids = ["subnet-xyzde987", "subnet-slkjf456", "subnet-qeiru789"]

  # Self Managed Node Group(s)
  self_managed_node_group_defaults = {
    instance_type                          = "m6i.large"
    update_launch_template_default_version = true
    iam_role_additional_policies = {
      AmazonSSMManagedInstanceCore = "arn:aws:iam::aws:policy/AmazonSSMManagedInstanceCore"
    }
  }

  self_managed_node_groups = {
    one = {
      name         = "mixed-1"
      max_size     = 5
      desired_size = 2

      use_mixed_instances_policy = true
      mixed_instances_policy = {
        instances_distribution = {
          on_demand_base_capacity                  = 0
          on_demand_percentage_above_base_capacity = 10
          spot_allocation_strategy                 = "capacity-optimized"
        }

        override = [
          {
            instance_type     = "m5.large"
            weighted_capacity = "1"
          },
          {
            instance_type     = "m6i.large"
            weighted_capacity = "2"
          },
        ]
      }
    }
  }

  # EKS Managed Node Group(s)
  eks_managed_node_group_defaults = {
    instance_types = ["m6i.large", "m5.large", "m5n.large", "m5zn.large"]
  }

  eks_managed_node_groups = {
    blue = {}
    green = {
      min_size     = 1
      max_size     = 10
      desired_size = 1

      instance_types = ["t3.large"]
      capacity_type  = "SPOT"
    }
  }

  # Fargate Profile(s)
  fargate_profiles = {
    default = {
      name = "default"
      selectors = [
        {
          namespace = "default"
        }
      ]
    }
  }

  # aws-auth configmap
  manage_aws_auth_configmap = true

  aws_auth_roles = [
    {
      rolearn  = "arn:aws:iam::66666666666:role/role1"
      username = "role1"
      groups   = ["system:masters"]
    },
  ]

  aws_auth_users = [
    {
      userarn  = "arn:aws:iam::66666666666:user/user1"
      username = "user1"
      groups   = ["system:masters"]
    },
    {
      userarn  = "arn:aws:iam::66666666666:user/user2"
      username = "user2"
      groups   = ["system:masters"]
    },
  ]

  aws_auth_accounts = [
    "777777777777",
    "888888888888",
  ]

  tags = {
    Environment = "dev"
    Terraform   = "true"
  }
}

```
