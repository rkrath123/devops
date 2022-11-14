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


main.tf
-------
```
resource local_file sample_res {
  filename = "sample.txt"
  content="I love terraform"

}

terraform init
terraform paln
terraform apply
```

local_file argument
====================
![image](https://user-images.githubusercontent.com/53966749/201647638-0324de53-88c8-4ee5-9f55-31a3a394f438.png)

```
mani.tf
-------
resource local_file sample_res {
  filename = "sample_args.txt"
  sensitive_content = "I Love Terraform"
  file_permission = "0700"
}

```
Multiple resourcse
=====================
![image](https://user-images.githubusercontent.com/53966749/201648018-408d91c8-5a3e-487c-b748-386f0bd5bfeb.png)
```
main.tf
--------
resource local_file cat_res {
  filename = "cat.txt"
  content = "I Love Cats"
}

resource local_file dog_res {
  filename = "dog.txt"
  content = "I Love Dogs"
}


```

Random Provider
===============

![image](https://user-images.githubusercontent.com/53966749/201648770-e9c88817-8369-407a-98b2-2b57e21ba876.png)
![image](https://user-images.githubusercontent.com/53966749/201649260-bf4a1bd9-c21c-4c2b-b0d7-bc46d09d08ea.png)
![image](https://user-images.githubusercontent.com/53966749/201650011-fbbcce15-1420-4cf6-9388-b7c4a43cf2c6.png)

```
main.tf
-------
resource random_integer rint{
    min = 80
    max = 200
}

resource random_string rstring {
  length  = 15
}


output name1 {
  value       = random_integer.rint.result
}

output name2 {
  value       = random_string.rstring.result
}


PS C:\Users\rathram\OneDrive - Hewlett Packard Enterprise\terraform\first-tf-script> terraform  apply
random_integer.rint: Refreshing state... [id=58]

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
  + create
-/+ destroy and then create replacement

Terraform will perform the following actions:

  # random_integer.rint must be replaced
-/+ resource "random_integer" "rint" {
      ~ id     = "58" -> (known after apply)
      ~ max    = 70 -> 200 # forces replacement
      ~ min    = 50 -> 80 # forces replacement
      ~ result = 58 -> (known after apply)
    }

  # random_string.rstring will be created
  + resource "random_string" "rstring" {
      + id          = (known after apply)
      + length      = 15
      + lower       = true
      + min_lower   = 0
      + min_numeric = 0
      + min_special = 0
      + min_upper   = 0
      + number      = true
      + numeric     = true
      + result      = (known after apply)
      + special     = true
      + upper       = true
    }

Plan: 2 to add, 0 to change, 1 to destroy.

Changes to Outputs:
  ~ name1 = 58 -> (known after apply)
  + name2 = (known after apply)

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

random_integer.rint: Destroying... [id=58]
random_integer.rint: Destruction complete after 0s
random_string.rstring: Creating...
random_string.rstring: Creation complete after 0s [id=D8ydnc]&{Mp%cj0]
random_integer.rint: Creating...
random_integer.rint: Creation complete after 0s [id=184]

Apply complete! Resources: 2 added, 0 changed, 1 destroyed.

Outputs:

name1 = 184
name2 = "D8ydnc]&{Mp%cj0"
PS C:\Users\rathram\OneDrive - Hewlett Packard Enterprise\terraform\first-tf-script> 

```

Variables
==========
![image](https://user-images.githubusercontent.com/53966749/201652367-19faaba4-80c7-4ae5-a773-adaa81b1f544.png)


