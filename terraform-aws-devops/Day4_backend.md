# S3 backend with dynamodb

## main.tf

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

resource "aws_dynamodb_table" "terraform_lock" {
  name           = "terraform-lock"
  billing_mode   = "PAY_PER_REQUEST"
  hash_key       = "LockID"

  attribute {
    name = "LockID"
    type = "S"

  }
}
resource "aws_s3_bucket" "s3_bucket" {
  bucket = "ramaknt-s3-demo-xyz" # change this
}
```

##  backend.tf

```

terraform {
  backend "s3" {
    bucket         = "ramaknt-s3-demo-xyz" # change this
    key            = "rama/terraform.tfstate"
    region         = "ap-south-1"
    encrypt        = true
    dynamodb_table = "terraform-lock"
  }
}

```
