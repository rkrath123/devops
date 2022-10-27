Ansible Architecure
===================
![image](https://user-images.githubusercontent.com/53966749/198248261-672ddc63-a025-4b0e-9c52-5b8bdfd586eb.png)
![image](https://user-images.githubusercontent.com/53966749/198255050-27ec1201-af6d-4132-a88e-42f0e487b15d.png)
![image](https://user-images.githubusercontent.com/53966749/198255411-7d83030c-cb50-4b5b-8884-6b6944f92c0e.png)


```
root@ubuntu-3:~# ansible --version
ansible 2.9.6
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.8.10 (default, Jun 22 2022, 20:18:18) [GCC 9.4.0
  
```
![image](https://user-images.githubusercontent.com/53966749/198254231-5e974162-680b-48d3-ac84-20f555a62caf.png)

![image](https://user-images.githubusercontent.com/53966749/198254044-b6d9407e-cf61-4770-8235-e2c5345b4e90.png)

Ansible Directory structure
==========================
![image](https://user-images.githubusercontent.com/53966749/198268989-be428be8-596b-4ea9-9b9d-e8efe441d575.png)
```
root@ubuntu-3:~# ansible all -m ping
[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match 'all'
root@ubuntu-3:~#

root@ubuntu-3:~# ansible all -m ping
[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match 'all'
root@ubuntu-3:~# vi /etc/ansible/ansible.cfg
root@ubuntu-3:~# cat /etc/ansible/ansible.cfg | head -20
# config file for ansible -- https://ansible.com/
# ===============================================

# nearly all parameters can be overridden in ansible-playbook
# or with command line flags. ansible will read ANSIBLE_CONFIG,
# ansible.cfg in the current working directory, .ansible.cfg in
# the home directory or /etc/ansible/ansible.cfg, whichever it
# finds first

[defaults]

# some basic default values...

#inventory      = /etc/ansible/hosts
#library        = /usr/share/my_modules/
#module_utils   = /usr/share/my_module_utils/
#remote_tmp     = ~/.ansible/tmp
#local_tmp      = ~/.ansible/tmp
#plugin_filters_cfg = /etc/ansible/plugin_filters.yml
#forks          = 5
root@ubuntu-3:~#

root@ubuntu-3:~# cat /etc/ansible/hosts
[ubuntu]
10.103.17.30
10.103.16.208

[rhel]
10.103.17.24
10.103.16.46

[sles]
10.103.16.112

root@ubuntu-3:~# ansible all -m ping
10.103.16.208 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
10.103.17.30 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
[WARNING]: Platform linux on host 10.103.16.112 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See
https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.
10.103.16.112 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.16.46 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.17.24 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}
root@ubuntu-3:~#


```
to change default ansible host file
===================================

 vi /etc/ansible/ansible.cfg
 
 ![image](https://user-images.githubusercontent.com/53966749/198271439-0813beb3-aef9-4d87-b163-867fc7f337f6.png)
 ![image](https://user-images.githubusercontent.com/53966749/198271519-aea7081d-056d-4dec-80bc-c2e6dcccbc50.png)

Change ansible directory
========================

![image](https://user-images.githubusercontent.com/53966749/198279452-4882518c-1bfe-4457-9c41-a1b2a3447e70.png)
![image](https://user-images.githubusercontent.com/53966749/198279646-b1df8b69-1256-4dfa-8542-fbaa775ca754.png)
![image](https://user-images.githubusercontent.com/53966749/198279820-26ce8abd-865c-4c75-bd75-451c1121ad8e.png)

Provide external hostfile path during runtime
============================================
![image](https://user-images.githubusercontent.com/53966749/198281283-1223ec43-1c15-41df-a2b9-323f457c208d.png)

Disable hostkey checking in ansible
===================================
```
[root@sudha testware-ansible]# cat /etc/ansible/ansible.cfg | grep host_key
#host_key_checking = False
#record_host_keys=False

[root@sudha testware-ansible]# vi /etc/ansible/ansible.cfg
[root@sudha testware-ansible]# cat /etc/ansible/ansible.cfg | grep host_key
host_key_checking = False
#record_host_keys=False

[root@sudha testware-ansible]# ansible all -m ping
[WARNING]: Platform linux on host 10.103.16.112 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See
https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.
10.103.16.112 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.16.46 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.17.24 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.17.30 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
10.103.16.208 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}

```

Ansible inventory files with groups
==================================
```
root@ubuntu-3:~# ansible 10.103.16.112 -m ping
[WARNING]: Platform linux on host 10.103.16.112 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See
https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.
10.103.16.112 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
root@ubuntu-3:~#

root@ubuntu-3:~# ansible all -m ping
[WARNING]: Platform linux on host 10.103.16.112 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See
https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.
10.103.16.112 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.16.46 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"

root@ubuntu-3:~# cat /etc/ansible/hosts

[ubuntu]
10.103.17.30
10.103.16.208

[rhel]
10.103.17.24
10.103.16.46

[sles]
10.103.16.112
root@ubuntu-3:~#

root@ubuntu-3:~# ansible rhel -m ping
10.103.16.46 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.17.24 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}


to work with rhel and sles server
---------------------------------

root@ubuntu-3:~# ansible rhel:sles -m ping
10.103.16.46 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.17.24 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}

10.103.16.112 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
root@ubuntu-3:~#

group of group :
/etc/ansible/hosts
[ubuntu]
10.103.17.30
10.103.16.208

[rhel]
10.103.17.24
10.103.16.46

[sles]
10.103.16.112

[db:children]
rhel
sles

root@ubuntu-3:~# ansible db -m ping
[WARNING]: Platform linux on host 10.103.16.112 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See
https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.
10.103.16.112 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.16.46 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}
10.103.17.24 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}

```

