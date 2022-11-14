Terraform work flow
===================

![image](https://user-images.githubusercontent.com/53966749/201637822-8e47de8c-b8f8-48d2-ac35-74a486eb003e.png)
![image](https://user-images.githubusercontent.com/53966749/201638379-82129fc2-b8f3-4c42-8d64-0ede385a89b1.png)

![image](https://user-images.githubusercontent.com/53966749/201640426-180ecdd1-1b75-447b-a17f-6400348c8c3d.png)

terraform init

![image](https://user-images.githubusercontent.com/53966749/201641168-4c3a98d3-487e-4496-8981-6e8431fc2864.png)

terraform plan

![image](https://user-images.githubusercontent.com/53966749/201641333-add53fab-9857-43f5-8507-8814452dbe28.png)

terraform apply

![image](https://user-images.githubusercontent.com/53966749/201641770-a158bb8e-c3d3-4395-87d9-8dd4d00ad8a2.png)

```
main.tf
resource local_file sample_res {
  filename = "sample.txt"
  content="I love terraform"

}
terraform init
terraform paln
terraform apply
```
