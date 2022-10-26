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


Define variable inside awk
--------------------------
```
[root@veena ~]# cat /etc/passwd | awk -v x=5 '{print $0, x}'
root:x:0:0:root:/root:/bin/bash 5
bin:x:1:1:bin:/bin:/sbin/nologin 5
```
Reading variable value from command:
-------------------------------------
```
[root@veena ~]# echo "2 6" | awk '{ print "a="$1 , "b="$2'}
a=2 b=6


```
Arithimatic operation in  variable for AWK
-----------------------------------------
```
[root@veena ~]# echo "2 6" | awk '{ x=$1 ;y=$2 ;print x+y}'
8

[root@veena ~]# a=6
[root@veena ~]# b=2
[root@veena ~]#  awk -v x=$a -v y=$b 'BEGIN {print x+y}'
8
[root@veena ~]#

```
![image](https://user-images.githubusercontent.com/53966749/197756578-19469859-1a13-42c3-b6e8-f330f0015fa2.png)
![image](https://user-images.githubusercontent.com/53966749/197756701-b1d3db8a-7eba-48d9-b297-9fc1df51531b.png)


SED command
===========

![image](https://user-images.githubusercontent.com/53966749/197760856-ffaf1d8d-59d4-486a-ab00-889de2f5cc1a.png)
![image](https://user-images.githubusercontent.com/53966749/197761051-6cb75fc9-7f23-4087-97c8-c90ec0fb4686.png)


![image](https://user-images.githubusercontent.com/53966749/197805419-967fe5e8-d13a-466c-910d-f826207155ad.png)

Practical
-----------
```
to view file with sed

[root@veena ~]# sed ' ' veena6leaders.config
or
sed -n 'p' veena6leaders.config

3rd line number will print
[root@veena rama]# sed -n '3p' veena6leaders.config
#temponame=mgmtsw0, mgmt_net_name=head, mgmt_net_macs="2c:23:3a:33:24:f9", mgmt_net_interfaces="eth0", transport=udpcast, redundant_mgmt_network=yes, net=head/head-bmc, type=spine, ice=no, console_device=ttyS1, architecture=x86_64
[root@veena rama]#

to print last line
[root@veena rama]# sed -n '$p' veena6leaders.config
image_types=default

to print 3rd line to 10th line
sed -n '3,10p' veena6leaders.config

to print from 3rd to till 10th line
[root@veena rama]# sed -n "3,+7p" veena6leaders.config

it will print from 1, then 4, then 7 ,then 10 so on
[root@veena rama]# sed -n "1~3p" veena6leaders.config

to delete line and display

[root@veena rama]# sed  '3,$d' veena6leaders.config
[discover]
#Switch

to delete from file
[root@veena rama]# sed  -i '3,$d' veena6leaders.config
[root@veena rama]# vi veena6leaders.config
[root@veena rama]# cat veena6leaders.config
[discover]
#Switch

delete file content with backup
[root@veena rama]# sed  -i.back '3,$d' veena6leaders.config
[root@veena rama]# cat veena6leaders.config
[discover]
#Switch

[root@veena rama]#ll 
veena6leaders.config.back
```


searching conntent with sed command
-----------------------------------

```

to search word in file
[root@veena rama]# sed -n '/admin_mgmt_interfaces/p' veena6leaders.config
admin_mgmt_interfaces="ens2f0,ens2f0"

multiple search in file
[root@veena rama]# sed -n -e '/admin_mgmt_interfaces/p' -e '/admin_house_interface/p' veena6leaders.config
admin_house_interface=eno1
admin_mgmt_interfaces="ens2f0,ens2f0"

[root@veena rama]# var="admin_mgmt_interfaces"
[root@veena rama]# sed -n "/$var/p" veena6leaders.config
admin_mgmt_interfaces="ens2f0,ens2f0"
[root@veena rama]# sed -n '/$var/p' veena6leaders.config
 no o/p with single quatation
 
 to delete 10th line to 15th line
 [root@veena rama]#  sed '10,15d' veena6leaders.config


to delete 10th to last line
[root@veena rama]#  sed '10,$d' veena6leaders.config

to delete search word line
[root@veena rama]#  sed '/service/d' veena6leaders.config

to delete others than search word line
[root@veena rama]#  sed '/service/!d' veena6leaders.config

to delete others than search word line in file
[root@veena rama]#  sed -i '/service/!d' veena6leaders.config

```
Find and Replace with SED command
-----------------------------------

![image](https://user-images.githubusercontent.com/53966749/197939196-c26cb018-eade-49ed-a846-610fc8892245.png)

practical
---------
```
cfhill:~/test # sed 's/root/udemy/g' passwd

to replace in file:
cfhill:~/test # sed  -i.back 's/root/udemy/g' passwd

replace 2nd same word in a line 

cfhill:~/test # sed  -i.back 's/root/udemy/2' passwd
cfhill:~/test # cat passwd | head -1
root:x:0:0:udemy:/root:/bin/bash

cfhill:~/test # cat passwd | head -1
root:x:0:0:root:/root:/bin/bash

search keyword  root and in that change shell from bash to ksh
cfhill:~/test # cat passwd | head -1
root:x:0:0:root:/root:/bin/bash

cfhill:~/test # sed   '/root/s/bash/ksh/' passwd | head -1
root:x:0:0:root:/root:/bin/ksh
```
