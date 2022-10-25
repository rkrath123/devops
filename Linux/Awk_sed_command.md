AWK Command
===========
![image](https://user-images.githubusercontent.com/53966749/197740802-0977dcb1-33c5-4db5-afd4-e3c7165bea56.png)
![image](https://user-images.githubusercontent.com/53966749/197740931-d22a29bf-5442-41a8-80c6-7e6ec028933b.png)


[root@veena ~]# systemctl status httpd | awk 'NR==5 {print $2}'
active

[root@veena rama]# awk 'NR==5 {print $2}' 1.txt
active

[root@veena rama]# cat /etc/passwd | awk -F ':' '{print $1}'
root
bin
daemon
adm
lp
