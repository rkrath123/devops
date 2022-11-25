Introduction
================

![image](https://user-images.githubusercontent.com/53966749/203980533-c2730fca-9860-4098-ba03-9080c41c46f7.png)
![image](https://user-images.githubusercontent.com/53966749/203980881-570ccc6b-b0dd-429f-9685-4ad460b49a1e.png)
![image](https://user-images.githubusercontent.com/53966749/203980956-f9a1b437-179a-4806-be10-6024e58c358f.png)
![image](https://user-images.githubusercontent.com/53966749/203981068-59db224a-0fd3-49a1-acac-42c2903c11b7.png)


Installing on windows
---------------------
![image](https://user-images.githubusercontent.com/53966749/203981607-035d5276-4e9c-4de4-b2e4-1fca98e11503.png)
![image](https://user-images.githubusercontent.com/53966749/203981684-543951a4-509c-405d-b369-75750bd9ab82.png)
![image](https://user-images.githubusercontent.com/53966749/203981851-af178b42-61e7-4edd-8c58-9db36fadd49b.png)


Installing on linux
-------------------
![image](https://user-images.githubusercontent.com/53966749/203982857-bcae738b-d874-4dd3-8603-b736cc68331c.png)

![image](https://user-images.githubusercontent.com/53966749/203982081-01a04b13-9648-4c7d-9328-b10b318e4059.png)

```
[root@sudha ~]# wget https://www.python.org/ftp/python/3.11.0/Python-3.11.0.tgz
--2022-11-25 17:34:59--  https://www.python.org/ftp/python/3.11.0/Python-3.11.0.tgz
Resolving web-proxy.in.hpecorp.net (web-proxy.in.hpecorp.net)... 16.242.46.30
Connecting to web-proxy.in.hpecorp.net (web-proxy.in.hpecorp.net)|16.242.46.30|:8080... connected.
Proxy request sent, awaiting response... 200 OK
Length: 26333656 (25M) [application/octet-stream]
Saving to: ‘Python-3.11.0.tgz’

100%[==============================================================================================================================================================>] 26,333,656  3.12MB/s   in 8.8s

2022-11-25 17:35:09 (2.85 MB/s) - ‘Python-3.11.0.tgz’ saved [26333656/26333656]

[root@sudha ~]#
[root@sudha ~]# tar -xzf Python-3.11.0.tgz
[root@sudha ~]# cd Python-3.11.0/

[root@sudha Python-3.11.0]# ./configure
checking build system type... x86_64-pc-linux-gnu

[root@sudha Python-3.11.0]# make
gcc -pthread -c -Wsign-compare -DNDEBUG -g -fwrapv -O3 -Wall    -std=c11 -Wextra -Wno-unused-parameter -Wno-missing-field-initializers -Werror=implicit-function-declaration -fvisibility=hidden  -I./Include/internal  -I. -I./Include    -DPy_BUILD_CORE -o Programs/python.o ./Programs/python.c

[root@sudha Python-3.11.0]# make altinstall
if test "no-framework" = "no-framework" ; then \
        /usr/bin/install -c python /usr/local/bin/python3.11; \

[root@sudha Python-3.11.0]# cd /usr/local/bin/
[root@sudha bin]# ./python3.11 --version
Python 3.11.0
[root@sudha bin]#

[root@sudha bin]# python --version
Python 2.7.5


[root@sudha bin]# which python3.11
/usr/local/bin/python3.11
[root@sudha bin]#
[root@sudha bin]# echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/opt/cmu/bin:/root/bin


[root@sudha bin]# ln -s python3.11 python3
[root@sudha bin]# python3 --version
Python 3.11.0
[root@sudha bin]#

[root@sudha ~]# python3 --version
Python 3.11.0

[root@sudha bin]# pip3.11 --version
pip 22.3 from /usr/local/lib/python3.11/site-packages/pip (python 3.11)
[root@sudha bin]#

[root@sudha bin]# ln -s pip3.11 pip3

[root@sudha bin]# pip3 --version
pip 22.3 from /usr/local/lib/python3.11/site-packages/pip (python 3.11)
[root@sudha bin]#

```