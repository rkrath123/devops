Arithimatic Operations
=========================
```
root@ubuntu-3:~/test# cat arithi.yaml
---
 - name: Play for Arithmetic OPerators
   hosts: localhost
   gather_facts: false
   vars:
    x: 56
    y: 34
   tasks:
   - name: Displaying values
     debug:
       msg:
       - "The value of x is: {{x}}"
       - "The value of y is: {{y}}"
       - "{{x}} + {{y}} = {{x+y}}"
       - "{{x}} - {{y}} = {{y-x}}"
       - "{{x}} * {{y}} = {{y*x}}"
       - "{{x}} / {{y}} = {{x/y}}"
       - "{{x}} % {{y}} = {{x%y}}"

root@ubuntu-3:~/test# ansible-playbook arithi.yaml

PLAY [Play for Arithmetic OPerators] *********************************************************************************************************************************************************************

TASK [Displaying values] *********************************************************************************************************************************************************************************
ok: [localhost] => {
    "msg": [
        "The value of x is: 56",
        "The value of y is: 34",
        "56 + 34 = 90",
        "56 - 34 = -22",
        "56 * 34 = 1904",
        "56 / 34 = 1.6470588235294117",
        "56 % 34 = 22"
    ]
}

PLAY RECAP ***********************************************************************************************************************************************************************************************
localhost                  : ok=1    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0




===================================================
---
 - name: Practice on Arithmetic Operators
   hosts: localhost
   gather_facts: false
   vars_prompt:
    - name: x
      prompt: Please enter x value
      private: no
    - name: y
      prompt: Enter y value
      private: no
   vars:
     a: 56
   tasks:
   - debug:
       msg:
       - "The value of x is: {{x}}"
       - "The value of y is: {{y}}"
       - "THe additon of {{x}} and {{y}} is {{x|int +y|int}}"
       - "The {{a}} - {{y}} = {{a-y|int}}"

=========================================

root@ubuntu-3:~/test# cat my_vars.yml
---
x:50
y:90


---
 - name: Practice on Arithmetic Operators
   hosts: localhost
   gather_facts: false
   vars_files:
    - my_vars.yml
   tasks:
   - debug:
       msg:
       - "The value of x is: {{x | type_debug}}"
       - "The value of x is: {{x}}"
       - "The value of y is: {{y}}"
       
=========================================

---
 - name: Practice on Arithmetic Operators
   hosts: localhost
   gather_facts: false
   #vars_files:
   # - my_vars.yml
   tasks:
   - debug:
       msg:
       - "The value of x is: {{x | type_debug}}"
       - "The value of x is: {{x}}"
       - "The value of y is: {{y}}"
ansible-playbook -e "x=45 y=78"

==========================================

```
