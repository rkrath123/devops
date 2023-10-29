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
