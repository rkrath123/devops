Ansible reusable concepts with import_tasks,include_tasks
==========================================================

![image](https://user-images.githubusercontent.com/53966749/200117095-2cec8623-42ef-40b5-9d65-ec033e747dd7.png)

```

---
  - name: Simple play to install multiple pkgs
    hosts: web_servers
    gather_facts: true
    become: yes
    tasks:
      - import_tasks: install_webserver_RedHat.yml
        when: ansible_os_family=="RedHat"
      - import_tasks: install_webserver_Debian.yml
        when: ansible_os_family=="Debian"
      - include_tasks: install_java_RedHat.yml
        when: ansible_os_family=="RedHat"
      - include_tasks: install_java_Debian.yml
        when: ansible_os_family=="Debian"
        
   cat install_webserver_RedHat.yml
   --------------------------------
   ---
     - name: Installing webserver on RedHat family
       yum:
        name: httpd
        state: present
    
    cat install_webserver_Debian.yml
    --------------------------------
    ---
     - name: Installing webserver on Debian family
       apt:
        name: apache2
        state: present
    
   cat  install_java_RedHat.yml
    -------------------------
    ---
     - name: Installing java on RedHat family
       yum:
        name: java-1.8.0-openjdk
        state: present
        
 cat install_java_Debian.yml
 ---------------------------
     ---
      - name: Installing java on Debian family
        apt:
          name: openjdk-8-jdk
          state: present
 