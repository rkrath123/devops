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

Types of Variables
===================
![image](https://user-images.githubusercontent.com/53966749/201667879-01ebf182-4d8c-455f-90bf-2087938aedce.png)

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


```
cat main.tf
-------------

resource local_file sample_res {
  filename = var.filename1
  content = var.content1
}



cat variables.tf
-----------------
variable filename1 {
  type      = string
  default   ="sample.txt"
}

variable content1 {
  type        = string
  default     = "I am loving Terraform"
}

```
Types of Variables
===================
![image](https://user-images.githubusercontent.com/53966749/201669153-6135fa86-f2e5-40a6-a3ee-c0c8ecffb34f.png)

```
cat main.tf
-----------

resource local_file sample_res {
  filename = var.filename1
 /* content = var.content1[0]
 */
  content = var.content1["name"]
  
}

variables.tf
------------
variable filename1 {
  type        = string
  default     = "sample1.txt"
}
/*
variable content1 {
  type        = number
  default     = 23
}
*/

/*
variable content1 {
  type        = bool
  default     = true
}
*/
/*
variable content1 {
  type        = list(string)
  default     = ["red", "green", "blue"]
}
*/

/*
variable content1 {
  type        = tuple([string,bool,number])
  default     = ["red", true, 23]
}
*/

variable content1 {
  type        = map
  default     = {name = "Ankit", age = 32}
}


```
Use variables
=============
![image](https://user-images.githubusercontent.com/53966749/201669970-6af72961-d444-4055-a92c-555baf1c6f9a.png)

![image](https://user-images.githubusercontent.com/53966749/201670549-e423c311-5922-4c61-9615-131e093f82b8.png)
![image](https://user-images.githubusercontent.com/53966749/201670687-635310ad-7191-4bd5-8465-9d9a661d4c36.png)


Multiple Providers
===================
![image](https://user-images.githubusercontent.com/53966749/201671391-4b76cd9f-fdcc-4da4-8578-ebc8ae267298.png)

multiple providers in same main.tf
----------------------------------

cat main.tf
-----------
```
resource local_file name {
  content = "This is HCL"
  filename = "sample.txt"
}

resource random_string name {
  length  = 10
}

```
Implicit dependancy
====================

![image](https://user-images.githubusercontent.com/53966749/201671710-e93c5cbd-9eb4-4fed-8303-833ac01cbfb7.png)

```
main.tf
-------
resource local_file name1 {
  filename = "implicit.txt"
  content = "This is random String from RP : ${random_string.name2.id}"

}

resource random_string name2 {
  length  = 10
}

implicit.txt
------------
This is random String from RP : eX0_?DM4VH
```

Explicit dependancy
===================
![image](https://user-images.githubusercontent.com/53966749/201673830-feb24784-26d8-44c3-846a-001dd4b5830c.png)

```
main.tf
---------
resource local_file name1 {
  filename = "explicit.txt"
  content = "This is random String from RP : ${random_string.name2.id}"
  depends_on =  [random_string.name2]
}

resource random_string name2 {
  length  = 10
}


explicit.txt
-----------
This is random String from RP : frctr]h=H2

```

output.tf
=========
![image](https://user-images.githubusercontent.com/53966749/201674646-1fe23c27-06c9-421a-a56b-ebd2d4f1c043.png)

Lifecycle Rules
==================

![image](https://user-images.githubusercontent.com/53966749/201675046-067aeb68-dd91-4b86-ba24-23efc78f31a6.png)

 main.tf
--------

```
resource random_integer name {
  min = 20
  max = 350

}
terraform apply
---------------
Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes
random_integer.name: Creating...
random_integer.name: Creation complete after 0s [id=82]
random_string.name2: Destroying... [id=eX0_?DM4VH]
random_string.name2: Destruction complete after 0s

```

create_before_destroy with main.tf
---------------------------------
```
main.tf
-------
resource random_integer name {
  min = 50
  max = 350
      lifecycle{
        create_before_destroy = true
  
    }

}

terraform apply
------------------
Terraform will perform the following actions: 

  # random_integer.name must be replaced      
+/- resource "random_integer" "name" {        
      ~ id     = "82" -> (known after apply)  
      ~ min    = 20 -> 50 # forces replacement
      ~ result = 82 -> (known after apply)    
        # (1 unchanged attribute hidden)      
    }

Plan: 1 to add, 0 to change, 1 to destroy.    

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

random_integer.name: Creating...
random_integer.name: Creation complete after 0s [id=179]
random_integer.name (deposed object b2edcb91): Destroying... [id=82]
random_integer.name: Destruction complete after 0s

Apply complete! Resources: 1 added, 0 changed, 1 destroyed.

```
prevent_destroy in main.tf
---------------------------
```
resource random_integer name {
  min = 50
  max = 350
      lifecycle{
        #create_before_destroy = true
        prevent_destroy = true
  
    }


}

PS C:\Users\rathram\OneDrive - Hewlett Packard Enterprise\terraform\first-tf-script> terraform  destroy
random_integer.name: Refreshing state... [id=179]
╷
│ Error: Instance cannot be destroyed
│
│   on main.tf line 1:
│    1: resource random_integer name {
│
│ Resource random_integer.name has lifecycle.prevent_destroy set, but the plan calls for this resource to be destroyed. To avoid this error and continue with the
│ plan, either disable lifecycle.prevent_destroy or reduce the scope of the plan using the -target flag.
╵
PS C:\Users\rathram\OneDrive - Hewlett Packard Enterprise\terraform\first-tf-script> 

```

ignore_changes in main.tf
-------------------------
```
main.tf
------
resource random_integer name {
  min = 67
  max = 97
      lifecycle{
        #create_before_destroy = true
        #prevent_destroy = true
        ignore_changes = [min]
  
    }


}

> terraform  apply
random_integer.name: Refreshing state... [id=71]

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the following symbols:
-/+ destroy and then create replacement

Terraform will perform the following actions:

  # random_integer.name must be replaced
-/+ resource "random_integer" "name" {
      ~ id     = "71" -> (known after apply)
      ~ max    = 84 -> 97 # forces replacement
      ~ min    = 60 -> 67
      ~ result = 71 -> (known after apply)
    }

Plan: 1 to add, 0 to change, 1 to destroy.

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

random_integer.name: Destroying... [id=71]
random_integer.name: Destruction complete after 0s
random_integer.name: Creating...
random_integer.name: Creation complete after 0s [id=76]

Apply complete! Resources: 1 added, 0 changed, 1 destroyed.

```

Provider Version
=================
![image](https://user-images.githubusercontent.com/53966749/201685010-2903b446-1917-4dd4-b045-ab37801545b5.png)

![image](https://user-images.githubusercontent.com/53966749/201685486-fe6769c8-6679-4c25-8c18-62d4c8578796.png)


```
terraform {
  required_providers {
    random = {
      source = "hashicorp/random"
      version = "2.3.1"
    }
  }
}

provider "random" {
  # Configuration options
}


resource random_integer name {
  min = 0
  max = 100
}

```

Data source -Read file
========================

![image](https://user-images.githubusercontent.com/53966749/201686121-b2375a6b-980a-4126-b866-48de87524ebf.png)

```
main.tf
--------
data local_file foo {
  filename = "sample1.txt"
}

output name1 {
  value       = data.local_file.foo.content
}


sample1.txt
----------
hello i am ramakant rath

terraform apply
--------------
Do you want to perform these actions?
  Terraform will perform the actions described above.    
  Only 'yes' will be accepted to approve.

  Enter a value: yes

random_integer.name: Destroying... [id=76]
random_integer.name: Destruction complete after 0s

Apply complete! Resources: 0 added, 0 changed, 1 destroyed.

Outputs:

name1 = "hello i am ramakant rath"

```
