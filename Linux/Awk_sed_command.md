AWK Command
===========
![image](https://user-images.githubusercontent.com/53966749/197740802-0977dcb1-33c5-4db5-afd4-e3c7165bea56.png)
![image](https://user-images.githubusercontent.com/53966749/197740931-d22a29bf-5442-41a8-80c6-7e6ec028933b.png)

Practical
----------
```
[root@veena ~]# systemctl status httpd | awk 'NR==5 {print $2}'
active

[root@veena rama]# awk 'NR==5 {print $2}' 1.txt
active

```
![image](https://user-images.githubusercontent.com/53966749/197746395-64b83ba9-1620-4ad8-8303-159e334264fc.png)
```

[root@veena rama]# cat /etc/passwd | awk -F ':' '{print $1}'
root
bin
daemon
adm
lp

[root@veena rama]# cat /etc/passwd | awk '{print NR $1}'
1root:x:0:0:root:/root:/bin/bash
2bin:x:1:1:bin:/bin:/sbin/nologin
3daemon:x:2:2:daemon:/sbin:/sbin/nologin
4adm:x:3:4:adm:/var/adm:/sbin/nologin

[root@veena rama]# cat /etc/passwd | awk '{print NR }'
1
2
3
4
..
..
72

NF means number of fileld
[root@veena rama]# cat /etc/passwd | awk -F ':' '{print NR,NF}'
1 7
2 7
3 7
4 7
5 7
6 7

[root@veena rama]# cat /etc/passwd | awk -F ':' '{print  "Number of line:"NR,"Number of field:",NF}'
Number of line:1 Number of field: 7
Number of line:2 Number of field: 7
Number of line:3 Number of field: 7
Number of line:4 Number of field: 7

[root@veena rama]# cat /etc/passwd | awk -F ':' '{print $NF}'
/bin/bash
/sbin/nologin
/sbin/nologin
/sbin/nologin
/sbin/nologin
/bin/sync
/sbin/shutdown
/sbin/halt

[root@veena rama]# cat /etc/passwd | awk -F ':' ' /root/ {print $0}'
root:x:0:0:root:/root:/bin/bash
operator:x:11:0:operator:/root:/sbin/nologin

```
![image](https://user-images.githubusercontent.com/53966749/197750120-236312fa-fcc9-4e8d-bde0-6630218444c5.png)

![image](https://user-images.githubusercontent.com/53966749/197749780-e2c922be-1bd3-4724-a8e9-688c7f635cca.png)
![image](https://user-images.githubusercontent.com/53966749/197749922-36872e43-3c41-4e59-8e79-80021d52f4c7.png)



